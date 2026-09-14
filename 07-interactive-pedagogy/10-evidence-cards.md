# 10-EVIDENCE-CARDS: Thư Viện Thẻ Bằng Chứng Thực Nghiệm

> Kho lưu trữ các thẻ bằng chứng thực nghiệm (Evidence Cards) được định danh chính thức, phục vụ việc đối chiếu, trích dẫn và kiểm định chất lượng nội dung trong toàn bộ khoá học Voice UX.

---

## Danh Mục Thẻ Bằng Chứng Chuẩn Hóa

### EVID-PD01: Ngưỡng Chuyển Lượt Con Người (Human Turn-Transition Gap)
- **[FACT]:** Khoảng lặng tự nhiên giữa hai lượt nói của con người là 200–250ms trên hầu hết các ngôn ngữ (Sacks et al., 1974). Độ trễ phản hồi máy móc >800ms kích hoạt phản xạ nói bồi gây va chạm âm thanh.
- **Source:** Sacks, Schegloff, & Jefferson (1974), *Language 50(4)*; LiveKit Benchmarks.
- **[RULE]:** Thiết kế Voice UX bắt buộc duy trì thời gian phản hồi 200–400ms; nếu quá trình xử lý vượt quá 700ms bắt buộc phải chèn Acoustic Filler trong vòng 400ms đầu tiên.
- **[RECOMMENDATION]:** Bài tập *Interactive Latency Slider* trên timeline dải sóng âm.

---

### EVID-PD02: Giới Hạn Cắt Âm Barge-In & Truncation Ngữ Cảnh
- **[FACT]:** Khung thời gian triệt tiêu âm thanh phát ra loa khi phát hiện ngắt lời (Barge-in Cut-off) phải diễn ra dưới 80–100ms để loại bỏ hoàn toàn cảm giác va chạm âm thanh (LiveKit 2024).
- **Source:** OpenAI Realtime Model Guide; LiveKit Interruption Handling.
- **[RULE]:** Khi ngắt lời, client phải lập tức dừng phát audio cục bộ và phát sự kiện `conversation.item.truncate` kèm mốc thời gian `audio_end_ms`. Không lưu văn bản chưa phát vào ngữ cảnh hội thoại.
- **[RECOMMENDATION]:** Bài tập *Barge-In Context Debugger* phân tích waveform kết hợp inspect context memory của LLM.

---

### EVID-PD03: Giới Hạn 4 Chunks Của Trí Nhớ Âm Thanh (Nelson Cowan)
- **[FACT]:** Trí nhớ làm việc thính giác chỉ có thể lưu giữ 3–4 đơn vị thông tin rời rạc trong vòng 3–5 giây trước khi dấu vết thần kinh âm thanh suy biến (Cowan, 2001).
- **Source:** Nelson Cowan (2001), *Behavioral and Brain Sciences*.
- **[RULE]:** Nghiêm cấm đưa ra nhiều hơn 3 lựa chọn thoại trong một lượt nói. Luôn đưa danh mục định hướng lên trước, chi tiết thao tác theo sau.
- **[RECOMMENDATION]:** Bài tập *Auditory Memory Overload Lab* nghe danh sách 7 món hàng không có màn hình hỗ trợ.

---

### EVID-PD04: Tiêu Chuẩn "Một Hơi Thở" (The One Breath Test)
- **[FACT]:** Sự chú ý thính giác tập trung liên tục của người nghe tương ứng với một chu kỳ hô hấp bình thường (khoảng 4–6 giây, tương đương 20–25 từ).
- **Source:** Amazon Alexa Design Guide — Be Clear; Google Conversation Design.
- **[RULE]:** Mọi câu thoại phản hồi của trợ lý ảo bắt buộc phải vượt qua "The One Breath Test": độ dài tối đa 25–30 từ và không quá 2 câu ngắn trong một lượt nói.
- **[RECOMMENDATION]:** Bài tập *Voice Script Word Diet* gạch bỏ từ thừa để nén câu thoại dài về chuẩn <22 từ.

---

### EVID-PD05: Hiệu Suất Của Active Learning So Với Nghe Thụ Động
- **[FACT]:** Học chủ động (Active Learning) giảm 33% tỷ lệ trượt môn và tăng kết quả kiểm tra lên gần 0.5 độ lệch chuẩn so với nghe giảng thụ động (Freeman et al., PNAS).
- **Source:** Freeman et al. (2014), *PNAS 111(23)*; Brilliant.org Pedagogy.
- **[RULE]:** Không cho phép trợ lý âm thanh độc thoại quá 60 giây liên tục. Mọi khối kiến thức đều phải kích hoạt phản hồi tương tác từ học viên ngay sau khi giải thích.
- **[RECOMMENDATION]:** Bài tập *Socratic Voice Discovery* hướng dẫn học viên tự rút ra nguyên lý thiết kế qua các câu hỏi tương tác.

---

### EVID-PD06: Nấc Thang Gợi Ý 4 Bậc Tiến Tiến (Progressive Hint Ladder)
- **[FACT]:** Cung cấp ngay đáp án khi học viên làm sai sẽ triệt tiêu hiệu ứng tự nhận thức ("Aha! moment") và làm suy giảm khả năng tự học độc lập (Koedinger & Corbett, 2006).
- **Source:** Intelligent Tutoring Systems (ITS) Research; Brilliant.org Guidance.
- **[RULE]:** Bắt buộc hỗ trợ cấu trúc gợi ý 4 bậc: Nudge (Khều nhẹ) → Principle (Nhắc nguyên tắc) → Next Step (Chỉ bước đi) → Bottom-out Solution (Lời giải cặn kẽ).
- **[RECOMMENDATION]:** Bài tập *Hint Ladder Authoring Workshop* thiết kế kịch bản gợi ý leo thang cho tình huống thiết kế UI.

---

### EVID-PD07: Leo Thang Nhắc Lại 3 Bậc (Alexa 3-Tier Progressive Reprompting)
- **[FACT]:** Việc lặp lại nguyên văn câu hỏi cũ khi người dùng im lặng khiến 65% người dùng nản lòng hoặc phản ứng tiêu cực với trợ lý ảo (Amazon Alexa Research).
- **Source:** Amazon Alexa Design Guide — Handle Errors.
- **[RULE]:** Mỗi lần reprompt bắt buộc phải gia tăng mức độ hỗ trợ (escalating detail), cung cấp ví dụ mẫu cụ thể và giới hạn vòng lặp lỗi ở tối đa 3 lượt trước khi thoát hiểm.
- **[RECOMMENDATION]:** Bài tập *Reprompt Escalator Simulation* xử lý tình huống người học im lặng 5 giây qua 3 cấp độ hỗ trợ.

---

### EVID-PD08: Nghĩa Vụ Minh Bạch Danh Tính AI (Mandatory AI Disclosure)
- **[FACT]:** Đạo luật AI của Liên minh Châu Âu (EU AI Act - Article 50) và chính sách OpenAI bắt buộc các hệ thống giọng nói tổng hợp phải công khai minh bạch danh tính máy móc.
- **Source:** EU Artificial Intelligence Act; OpenAI Voice Safety Policies.
- **[RULE]:** Thông báo rõ ràng là trợ lý AI ngay trong lượt chào đầu tiên hoặc ngữ cảnh giới thiệu. Nghiêm cấm giả mạo cảm xúc sinh học hoặc đóng giả người thật.
- **[RECOMMENDATION]:** Bài tập *Onboarding Persona Scripting* viết lời chào mở đầu minh bạch danh tính AI một cách ấm áp và tự nhiên.

---

### EVID-PD09: Mã Hóa Kép Xúc Giác & Âm Thanh (Haptic Dual-Coding)
- **[FACT]:** Tín hiệu âm thanh (Earcon) khi được ghép đôi đồng bộ với rung xúc giác (Haptics) giúp giảm 22% thời gian phản ứng của người dùng (Blattner et al., 1989) và đảm bảo tiếp cận trong môi trường ồn.
- **Source:** Apple Human Interface Guidelines — Feedback & Haptics.
- **[RULE]:** Mọi trạng thái hệ thống quan trọng bắt buộc phải có đủ bộ 3 tín hiệu đồng bộ: Earcon (Âm thanh) + Haptics (Rung) + Visual Cue (Thị giác). Không phát âm thanh đơn độc.
- **[RECOMMENDATION]:** Bài tập *Earcon & Haptic Orchestration Studio* phối ghép dải tần số âm thanh và kiểu rung cho các trạng thái của trợ lý.

---

### EVID-PD10: Định Chuẩn Sự Không Chắc Chắn (Calibrated Confidence)
- **[FACT]:** Khi trợ lý giọng nói đưa ra câu trả lời ảo giác (hallucination) với giọng điệu tự tin, mức độ suy giảm niềm tin của người dùng cao gấp 3 lần so với trường hợp hệ thống thừa nhận sự không chắc chắn (Microsoft Research, 2019).
- **Source:** Amershi et al. (2019), *Guidelines for Human-AI Interaction*.
- **[RULE]:** Khi độ tin cậy nhận dạng < 0.75, hệ thống tuyệt đối không được tự ý đoán mò hành động; bắt buộc phải hỏi lại xác nhận hoặc thừa nhận giới hạn kiến thức.
- **[RECOMMENDATION]:** Bài tập *Confidence Threshold Switchboard* phân tích file âm thanh nhiễu và thiết lập phản hồi tương ứng theo 3 bậc tin cậy.
