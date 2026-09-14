# SOURCE: OpenAI Realtime API & Voice Safety Guidelines

> Tài liệu trích xuất chuẩn mực xử lý Full-Duplex WebRTC audio, Audible Truncation và minh bạch danh tính AI từ OpenAI.

- **URL:** [https://platform.openai.com/docs/guides/realtime-model-capabilities](https://platform.openai.com/docs/guides/realtime-model-capabilities)
- **Tổ chức:** OpenAI
- **Ngày tham chiếu:** 2026-09-14

---

## Các Chuẩn Mực Cốt Lõi Được Trích Xuất

### 1. Xử Lý Gián Đoạn & Cắt Ngữ Cảnh (`conversation.item.truncate`)
- Khi người dùng cắt ngang lời trợ lý, ứng dụng client bắt buộc phải gửi sự kiện `conversation.item.truncate` kèm `audio_end_ms`.
- Mục tiêu: Đồng bộ chính xác độ dài audio người dùng thực sự đã nghe với dữ liệu văn bản được lưu trong context memory của mô hình, ngăn chặn triệt để ảo giác suy diễn (context drift).

### 2. An Toàn Giọng Nói & Minh Bạch Danh Tính Máy Móc
- **URL:** [https://openai.com/policies/usage-policies](https://openai.com/policies/usage-policies)
- Bắt buộc thông báo cho người dùng biết họ đang tương tác với trợ lý AI.
- Cấm mạo danh người thật hoặc tuyên bố có cảm xúc/thể xác con người.
