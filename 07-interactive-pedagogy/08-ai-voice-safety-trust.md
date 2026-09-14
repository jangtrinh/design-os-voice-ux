# 08-AI-VOICE-SAFETY-TRUST: An Toàn, Minh Bạch Danh Tính và Sự Tin Cậy

> Khung tiêu chuẩn về minh bạch danh tính máy móc, kiểm soát ảo giác âm thanh, định chuẩn độ tin cậy và ranh giới an toàn theo EU AI Act, OpenAI & Microsoft Research.

---

## 1. Bắt Buộc Minh Bạch Danh Tính AI (Mandatory AI Disclosure)

- **[FACT]:** Đạo luật Trí tuệ Nhân tạo của Liên minh Châu Âu (EU AI Act - Article 50) và Chính sách an toàn giọng nói của OpenAI bắt buộc mọi hệ thống giao tiếp bằng giọng nói nhân tạo phải thông báo rõ ràng cho người dùng biết họ đang tương tác với máy móc.
- **[RULE]:**
  1. Trợ lý giọng nói phải công khai danh tính AI ngay trong lượt thoại đầu tiên hoặc trong màn hình chào đón (Onboarding).
  2. Tuyệt đối nghiêm cấm:
     - Giả mạo giọng nói của người nổi tiếng hoặc cá nhân có thật khi chưa được cấp phép.
     - Tuyên bố có cảm xúc sinh học thật (*"Tôi đang cảm thấy rất đau lòng..."*), có cơ thể vật lý hay có trải nghiệm cuộc sống như con người (Tránh bẫy Uncanny Valley và hiệu ứng ELIZA).
     - Đánh lừa người dùng rằng họ đang nói chuyện với tư vấn viên con người.

---

## 2. Định Chuẩn Độ Tin Cậy & Minh Bạch Sự Không Chắc Chắn (Calibrated Confidence)

- **[FACT]:** Khi trợ lý giọng nói đưa ra câu trả lời sai (hallucination) với giọng điệu tự tin, mức độ suy giảm niềm tin của người dùng cao gấp 3 lần so với trường hợp hệ thống thừa nhận mình không chắc chắn (Microsoft Human-AI Interaction Guidelines, Amershi et al., 2019).
- **[RULE] Ngưỡng Xử Lý Điểm Tin Cậy (Confidence Threshold Routing):**
  - **High Confidence (> 0.85):** Thực thi lệnh ngay lập tức và đưa ra phản hồi xác nhận ngầm (Implicit Confirmation).
  - **Medium Confidence (0.60 – 0.85):** Không tự ý thực thi. Bắt buộc phải hỏi lại xác thực nhẹ (ví dụ: *"Có phải bạn muốn đặt vé đi Đà Nẵng vào ngày mai không?"*).
  - **Low Confidence (< 0.60):** Thừa nhận giới hạn nhận dạng và yêu cầu người dùng lặp lại hoặc cung cấp phương án lựa chọn thay thế (ví dụ: *"Xin lỗi, xung quanh hơi ồn nên mình chưa nghe rõ điểm đến. Bạn có thể nói lại tên thành phố được không?"*).

---

## 3. Ranh Giới An Toàn Dữ Liệu Âm Thanh & Quyền Riêng Tư (Audio Privacy)

- **[FACT]:** Dữ liệu âm thanh (Voice Audio) chứa các đặc trưng sinh trắc học cá nhân nhạy cảm (giới tính, độ tuổi, cảm xúc, sức khỏe, môi trường xung quanh).
- **[RULE]:**
  1. Không bao giờ lưu trữ file ghi âm thô (raw PCM audio) trên máy chủ nếu không có sự đồng thuận rõ ràng (Explicit Opt-in) từ người dùng.
  2. Bắt buộc xóa bộ đệm âm thanh tạm thời (Ephemeral Audio Buffer) ngay sau khi hoàn thành phiên xử lý STT/LLM.
  3. Cấm phát lại các dữ liệu nhạy cảm (số thẻ tín dụng, mật khẩu, mã OTP) qua loa ngoài ở nơi công cộng; phải tự động chuyển hướng hiển thị che giấu (masked display) trên màn hình cá nhân.
