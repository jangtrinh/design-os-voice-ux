# 05-EXERCISES-SIMULATIONS: Danh Mục Các Mẫu Tương Tác Sư Phạm (Pedagogical Interaction Primitives)

> Thư viện chuẩn hóa các cơ chế tương tác và kịch bản phòng lab giả lập trong DESIGN:OS Voice UX Academy.

---

## 1. Năm Dạng Tương Tác Sư Phạm Cốt Lõi (The 5 Interaction Primitives)

Mọi bài tập kiểm tra hoặc thực hành tương tác đều phải thuộc một trong 5 primitive sau:

### Primitive 1: LOCATE (Chỉ điểm sai phạm trên Graphic UI)
- **Cơ chế:** Màn hình hiển thị dòng thời gian hội thoại (Timeline) hoặc dải sóng âm (Waveform). Học viên bấm trực tiếp vào vùng xảy ra lỗi.
- **Ví dụ áp dụng:**
  - *Dead Air Spotter:* Bấm vào khoảng trống im lặng >800ms giữa hai lượt thoại.
  - *Collision Spotter:* Bấm vào điểm giao nhau màu đỏ nơi Agent tiếp tục nói đè lên người dùng.

### Primitive 2: TUNE (Cân chỉnh tham số tương tác thời gian thực)
- **Cơ chế:** Học viên kéo thanh trượt (slider) để tìm vùng giá trị tối ưu. Hệ thống mô phỏng âm thanh và biểu diễn trực quan hiệu ứng tức thì.
- **Ví dụ áp dụng:**
  - *Silence Threshold Tuner:* Tìm vùng 350ms – 550ms.
  - *Min Speech Duration (Debounce):* Tìm vùng 200ms – 300ms để chặn tiếng ho 80ms mà không bỏ sót lệnh thật.
  - *SSML Speech Rate:* Căn chỉnh tốc độ đọc 145–155 WPM kèm khoảng dừng `<break time="300ms"/>`.

### Primitive 3: REPAIR (Sửa chữa nút hoặc cấu trúc câu thoại)
- **Cơ chế:** Học viên thực hiện thao tác sửa lỗi trực tiếp trên sơ đồ luồng (Pipeline Graph) hoặc gạch bỏ từ thừa trong văn bản (Word Diet).
- **Ví dụ áp dụng:**
  - *Pipeline Node Reconnect:* Nối đúng tín hiệu ngắt âm `Stop Playback Buffer` khi VAD kích hoạt.
  - *One Breath Script Diet:* Cắt tỉa câu trả lời từ 60 từ xuống <20 từ.

### Primitive 4: PREDICT (Dự đoán hành vi hoặc kết quả)
- **Cơ chế:** Hệ thống phát một đoạn âm thanh hoặc đặt một tình huống. Học viên dự đoán trạng thái tiếp theo của máy hoặc con người trước khi hệ thống chạy tiếp.
- **Ví dụ áp dụng:**
  - *Turn Expectation Game:* Bấm dừng ngay tại mili-giây dự đoán người nói kết thúc câu.
  - *Confidence Routing:* Dự đoán xem hệ thống nên thực thi ngay hay hỏi lại khi confidence = 0.65.

### Primitive 5: ADVERSARIAL SANDBOX (Phòng thử nghiệm phá hủy hệ thống)
- **Cơ chế:** Dành cho Pro Level. Học viên kích hoạt các sự cố môi trường (nhiễu ồn, rớt gói tin WebRTC, nói ngắt quãng) để kiểm tra độ bền vững của Voice Agent.
- **Ví dụ áp dụng:**
  - *65dB Cafe Noise Injection:* Xem tỷ lệ False Interruption vọt lên bao nhiêu % và cấu hình bộ lọc bù đắp.
  - *Packet Loss Injection:* Đánh giá độ trễ re-buffering Opus frames.
