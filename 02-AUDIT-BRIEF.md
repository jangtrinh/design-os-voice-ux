# 02-AUDIT-BRIEF: Bối Cảnh & Định Hướng Kiểm Định Voice UX

> Bản tóm tắt 1 trang xác định phạm vi áp dụng thực tế, kiến trúc kỹ thuật của hệ thống và các trọng tâm rủi ro cần soi lỗi trong đợt kiểm định Voice UX Knowledge Base.

---

## 1. Bối Cảnh Sản Phẩm & Phạm Vi Ứng Dụng (Product Scope)

- **Mục tiêu hệ thống**: Xây dựng bộ quy chuẩn thiết kế và kỹ nghệ cho các **Voice AI Agents thế hệ mới (Full-Duplex Speech-to-Speech & Multimodal)** phục vụ:
  1. Trợ lý giọng nói đa phương thức (Smartphone / Tablet / Smart Display).
  2. Hệ thống đàm thoại rảnh tay trong xe hơi thông minh (Automotive In-Cabin VUI).
  3. Trợ lý ảo dịch vụ khách hàng thời gian thực (Real-time Customer Voice Support).
- **Phạm vi loại trừ (Cố ý không bao gồm)**: Các hệ thống tổng đài bấm phím truyền thống dạng cây nhị phân tĩnh (Legacy DTMF IVR) hoặc các lệnh thoại ngoại tuyến cục bộ chỉ nhận diện 1 từ khóa (Offline Hotword Engine).

---

## 2. Ngăn Xếp Kỹ Thuật Tham Chiếu (Reference Voice Stack)

Hệ thống kiến thức được thiết kế để áp dụng cho hai nhóm kiến trúc đàm thoại chủ lực:

```
Nhóm 1 - Native Audio-to-Audio (Khuyên dùng):
Micro/WebRTC ──► WebAssembly VAD ──► Speech-to-Speech LLM (Gemini Live / OpenAI Realtime) ──► Low-latency Audio Stream

Nhóm 2 - Optimized Cascaded Pipeline:
Micro ──► Silero VAD (<10ms) ──► Streaming ASR (Deepgram Nova-2) ──► Fast LLM ──► Streaming TTS (Cartesia/ElevenLabs)
```

- **Giao thức vận chuyển**: WebRTC UDP hai chiều (Full-Duplex) có Acoustic Echo Cancellation (AEC).
- **Ngân sách độ trễ mục tiêu**: `< 400ms` từ khi người dùng dứt lời đến khi loa phát âm thanh.

---

## 3. Các Điểm Thất Bại Thực Tế Cần Soi Lỗi (Critical Failure Modes)

Đợt audit cần tập trung bóc tách 5 "điểm mù" lớn nhất thường bị các tài liệu lý thuyết bỏ quên:

1. **Bẫy va chạm ngắt lời (Barge-in Collision & State Bleed)**:
   - Khi người dùng ngắt lời ở giây thứ 2 của câu nói 5 giây, liệu bộ nhớ hội thoại có bị "nhiễm độc" bởi 3 giây sau mà người dùng chưa hề nghe không?
2. **Khoảng lặng chết chóc (Dead-Air Latency Gap)**:
   - Khi hệ thống cần gọi Tool/API hoặc tra cứu RAG mất 1.5s - 2.5s, cơ chế lấp khoảng trống (Acoustic Fillers) được thiết kế như thế nào để người dùng không tưởng bị rớt mạng?
3. **Vòng lặp sửa lỗi vô tận (Repetitive Repair Loop)**:
   - Khi nhận diện sai (ASR misrecognition), trợ lý có bị rơi vào vòng luẩn quẩn *"Xin lỗi, bạn có thể nói lại không?"* khiến người dùng ức chế cúp máy?
4. **Giả lập thấu cảm lố lăng (Uncanny Empathy)**:
   - Tránh việc bot AI giả vờ khóc cười hoặc đưa ra lời khuyên y tế/tài chính sai lệch khi chưa đủ dữ liệu xác thực.
5. **Ngộ nhận về sự hoàn hảo của giọng nói (Voice Overreach)**:
   - Bắt người dùng nghe đọc danh sách dài, số liệu phức tạp thay vì chủ động phân tải hiển thị sang màn hình (Visual Offloading).

---

## 4. Tiêu Chuẩn "Sẵn Sàng Ra Mắt" (Launch-Ready Criteria)

Một tính năng Voice AI chỉ được xem là **Production Ready** khi vượt qua:
- **Độ trễ ngắt lời (Barge-in latency)**: `< 100ms` (User nói -> Loa ngắt ngay).
- **Tỷ lệ hoàn thành tác vụ (TCR)**: `> 85%` trong bài test Wizard of Oz.
- **Tính trọn vẹn ngữ cảnh (Context Integrity)**: 100% các câu nói bị ngắt được cắt tỉa theo ranh giới âm thanh thực tế (`Audible Boundary Truncation`).
- **Lối thoát khẩn cấp toàn cục**: Nhận diện tức thì lệnh *"Dừng lại"*, *"Hủy"* ở 100% các trạng thái.
