# 03-TURN-TAKING-LATENCY-REPAIR: Cơ Chế Chuyển Lượt, Độ Trễ và Sửa Lỗi

> Đặc tả kỹ thuật và tiêu chuẩn sư phạm cho chu kỳ Turn-taking, Barge-in ngắt lời, ngân sách độ trễ và văn hóa sửa lỗi hội thoại.

---

## 1. Chu Kỳ Chuyển Lượt (Turn-Taking Cadence)

- **[FACT]:** Khoảng lặng tự nhiên giữa hai lượt nói của con người (Transition-relevance Place - TRP) dao động trong khoảng 200–250ms trên hầu hết các ngôn ngữ trên thế giới (Sacks, Schegloff, & Jefferson, 1974).
- **[RULE] Ngân Sách Phản Hồi:**
  - *Mục tiêu tối ưu:* 200–400ms.
  - *Ngưỡng cảnh báo:* >600ms.
  - *Ngưỡng thất bại:* >800ms (Người dùng bắt đầu nói bồi gây va chạm âm).
- **[RULE] Acoustic Fillers:** Nếu xử lý backend/LLM vượt quá 700ms, hệ thống bắt buộc phải phát tín hiệu âm thanh hoặc Acoustic Filler (*"Để mình xem...", "Đợi chút nhé..."*) trong vòng 400ms đầu tiên để chiếm giữ kênh âm thanh.

---

## 2. Sub-100ms Barge-In & Context Truncation

- **[FACT]:** Để người dùng không có cảm giác máy cãi nhau với người, thời gian từ khi mic phát hiện tiếng người đến khi loa ngắt hoàn toàn (Barge-in Cut-off Latency) phải dưới **80–100ms**.
- **[RULE] Audible Boundary Truncation (OpenAI Realtime & LiveKit Standard):**
  - Ngay khi phát hiện ngắt lời, client phải gửi lệnh `conversation.item.truncate` kèm mốc thời gian `audio_end_ms` chính xác mà người dùng đã nghe.
  - Cấm giữ lại phần text chưa phát vào bộ nhớ ngữ cảnh LLM để triệt tiêu hiện tượng ảo giác và lạc đề (context drift).

---

## 3. Conversational Repair: Văn Hóa Sửa Lỗi Không Đổ Lỗi

- **[FACT]:** Thông báo lỗi kỹ thuật ("Không nhận dạng được giọng nói", "Dữ liệu không hợp lệ") kích hoạt phản xạ phòng vệ và tăng tỷ lệ bỏ cuộc của người dùng lên hơn 50% (Google Research).
- **[RULE]:**
  1. Tuyệt đối không đổ lỗi cho người dùng hoặc thông báo lỗi kỹ thuật hệ thống.
  2. Áp dụng kỹ thuật **Rapid Reprompt** hoặc tái cấu trúc câu hỏi có tính định hướng (ví dụ: *"Bạn muốn đi chuyến sáng hay chuyến chiều?"* thay vì *"Bạn đã chọn sai chuyến"*).
  3. Giới hạn vòng lặp sửa lỗi tối đa 3 lần trước khi kích hoạt kênh hỗ trợ người thật hoặc trả về menu chính.
