# SOURCE: Apple Human Interface Guidelines (Audio, Siri & Haptics)

> Tài liệu trích xuất chuẩn mực thiết kế âm thanh, trợ lý Siri và phản hồi xúc giác từ hệ sinh thái Apple HIG.

- **URL:** [https://developer.apple.com/design/human-interface-guidelines/playing-audio](https://developer.apple.com/design/human-interface-guidelines/playing-audio)
- **Tổ chức:** Apple Inc.
- **Ngày tham chiếu:** 2026-09-14

---

## Các Chuẩn Mực Cốt Lõi Được Trích Xuất

### 1. Quản Lý Phiên Âm Thanh (Audio Session Management)
- **Nguyên tắc:** Thiết bị di động là tài sản cá nhân nhạy cảm. Ứng dụng phải định rõ danh mục âm thanh (`AVAudioSessionCategoryPlayback` vs `AVAudioSessionCategoryAmbient`) để tôn trọng nút gạt im lặng phần cứng (Silent Switch).
- **Audio Ducking:** Khi có thông báo tạm thời (turn-by-turn navigation, incoming message), ứng dụng phải tạm thời giảm 70% âm lượng giọng nói thay vì ngắt đột ngột.
- **Interruption Handling:** Tạm dừng hoàn toàn khi có cuộc gọi điện thoại đến hoặc kích hoạt Siri; lưu lại vị trí con trỏ âm thanh để phục hồi mượt mà sau khi cuộc gọi kết thúc.

### 2. Phản Hồi Xúc Giác & Âm Thanh (Playing Haptics & Feedback)
- **URL:** [https://developer.apple.com/design/human-interface-guidelines/playing-haptics](https://developer.apple.com/design/human-interface-guidelines/playing-haptics)
- **Nguyên tắc:** Luôn ghép đôi tín hiệu âm thanh (Earcons) với rung phản hồi xúc giác (Haptic Patterns) để gia tăng khả năng tiếp cận và giảm thời gian phản xạ người dùng trong môi trường ồn ào.

### 3. Thiết Kế Trợ Lý Giọng Nói (Siri & Speech Recognition)
- Phản hồi ngắn gọn, đưa thông tin thiết yếu nhất lên đầu.
- Hỗ trợ đầy đủ màn hình hình ảnh đi kèm (visual display accompaniment) khi có thể.
