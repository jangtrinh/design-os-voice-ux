# 07-ACCESSIBILITY-INCLUSIVE-VOICE: Thiết Kế Toàn Diện, Xúc Giác & Đa Phương Thức

> Chuẩn mực tiếp cận toàn diện (Accessibility), mã hóa kép âm thanh - xúc giác (Haptic Dual-Coding), quản lý Audio Session và xử lý môi trường thực tế theo Apple HIG & W3C.

---

## 1. Nguyên Tắc Bộ Ba Đồng Bộ: Earcon + Haptic + Visual (Trio Feedback)

- **[FACT]:** Tín hiệu âm thanh (Earcon) khi được ghép đôi đồng bộ với rung xúc giác (Haptics) giúp giảm 22% thời gian phản ứng của người dùng (Blattner et al., 1989), đồng thời đảm bảo người khiếm thính hoặc người đang ở môi trường ồn ào vẫn nhận biết được trạng thái hệ thống.
- **[RULE]:** Mọi trạng thái hệ thống quan trọng bắt buộc phải kích hoạt đồng thời 3 kênh:
  1. **Acoustic Signifier (Earcon):** Âm báo ngắn 50–150ms có cao độ phân biệt (Success: nốt C5 lên E5; Error: nốt trầm sawtooth).
  2. **Haptic Signifier (Xúc giác):** Xung rung nhẹ (Transient Haptic Tap) cho thành công, rung kép (Double Pulse) cho cảnh báo.
  3. **Visual Cue (Thị giác):** Đổi màu viền hoặc icon trạng thái trên màn hình.
  - Tuyệt đối không phát âm thanh đơn độc mà không có kênh phản hồi thứ hai hỗ trợ.

---

## 2. Quản Lý Audio Session & Audio Ducking (Apple HIG Standard)

- **[FACT]:** Người dùng coi thiết bị là không gian riêng tư cá nhân. Phát âm thanh khi thiết bị đang ở chế độ Rung/Im lặng hoặc đè lên cuộc gọi thoại sẽ phá hủy niềm tin ngay tức khắc.
- **[RULE] Phân Cấp Gián Đoạn Âm Thanh (Audio Interruption Hierarchy):**
  1. **Primary Interruption (Cuộc gọi đến, Siri, Báo thức):** Bắt buộc phải **Tạm dừng ngay lập tức (Pause/Stop)** và lưu lại con trỏ trạng thái bài học.
  2. **Transient Interruption (Thông báo tin nhắn, âm thanh dẫn đường GPS):** Kích hoạt cơ chế **Audio Ducking** (tự động giảm 70% âm lượng giọng nói trong thời gian âm báo vang lên, sau đó khôi phục mượt mà).
  3. **Tôn trọng Silent Switch:** Nếu người dùng bật nút gạt im lặng phần cứng trên điện thoại, tự động chuyển toàn bộ giao diện bài học sang chế độ hình ảnh + phụ đề chữ (Captions/Subtitles) mà không phát loa ngoài.

---

## 3. Thiết Kế Cho Môi Trường Thực Tế (Hands-Busy & Eyes-Busy Context)

- **[FACT]:** Giọng nói thường được sử dụng trong các tình huống "bận tay, bận mắt" (lái xe, nấu ăn, tập thể thao). Trong bối cảnh này, khả năng nhìn vào màn hình của người dùng bằng 0.
- **[RULE]:**
  - Trong chế độ rảnh tay (Hands-free mode), mọi tác vụ phải hoàn tất được 100% bằng âm thanh mà không đòi hỏi thao tác chạm xác nhận trên màn hình.
  - Phải có âm thanh báo mở mic (Earcon Chime) để người dùng biết máy đã sẵn sàng nhận lệnh mà không cần nhìn đèn led tín hiệu.
