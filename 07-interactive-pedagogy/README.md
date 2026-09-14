# 07-INTERACTIVE-PEDAGOGY: Voice UX Interactive Pedagogy Knowledge Base

> Khung chuẩn mực sư phạm tương tác (Interactive Pedagogy) và ma trận bằng chứng thực nghiệm (Empirical Evidence Matrix) dành riêng cho đào tạo Voice UX, được tổng hợp từ 6 nhóm nguồn tham chiếu hàng đầu: Apple HIG, Google Conversation Design, Amazon Alexa Design Guide, OpenAI Realtime API / LiveKit Agents, Brilliant.org và Uxcel.

---

## 1. Tuyên Ngôn Sư Phạm: "Intuition First → Action → Formalize"

Học Voice UX không thể chỉ bằng việc đọc tài liệu hay nghe giảng thụ động. Dựa trên Mayer's Cognitive Theory of Multimedia Learning và phương pháp Active Learning (Freeman et al., PNAS):

1. **Visual-first, text-second:** Mọi khái niệm âm học trừu tượng (độ trễ, ngắt lượt, cướp lời) đều phải được cụ thể hóa bằng mô hình đồ họa trực quan (Graphic UI Visual).
2. **Loại bỏ Split-Attention:** Nhãn thông số, mốc thời gian và trạng thái VAD/Endpointing được đặt trực tiếp lên dải sóng âm (Waveform) và thanh tiến trình (Waterfall), không tách rời nhau.
3. **Explore → Predict → Formalize:** Người học phải trực tiếp chạm, kéo, nghe sự va chạm âm thanh trước khi hệ thống công bố định nghĩa lý thuyết.

---

## 2. Ma Trận Tri Thức 5 Nhóm Cốt Lõi

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                 DESIGN:OS VOICE UX INTERACTIVE PEDAGOGY                     │
├──────────────────────┬──────────────────────┬───────────────────────────────┤
│ 1. Conversation      │ 2. Cognitive Load    │ 3. Interactive Learning       │
│    Mechanics         │    & Voice Pedagogy  │    Loops                      │
│ • Turn-gap 200ms     │ • Cowan 4-chunk limit│ • Active Learning (Freeman)   │
│ • Sub-100ms Barge-in │ • One Breath Test    │ • 6-Stage Pedagogy Loop       │
│ • Adaptive VAD       │ • 1 Idea / Utterance │ • First-Principles Intuition  │
│ • Repair Heuristics  │ • SSML Pacing        │ • Socratic Discovery          │
├──────────────────────┴──────────────────────┼───────────────────────────────┤
│ 4. Feedback, Error & Mastery                │ 5. Trust, Accessibility & AI  │
│ • 4-Tier Progressive Hint Ladder            │ • Mandatory AI Disclosure     │
│ • Alexa 3-Tier Progressive Reprompting      │ • Audio Ducking & Interrupts  │
│ • Formative Multi-Modal Testing (Uxcel)     │ • Earcons & Haptic Dual-Code  │
│ • Instant Visual & Acoustic Validation      │ • Calibrated Confidence       │
└─────────────────────────────────────────────┴───────────────────────────────┘
```

---

## 3. Danh Mục Chi Tiết 5 Nhóm Chuẩn Mực & Bằng Chứng

### Nhóm 1: Conversation Mechanics (Turn-taking, Barge-in, Silence, Latency, Repair)

#### 1.1. Chu kỳ Turn-Taking và Ngưỡng Perceptual Latency
- **Nguồn:** Sacks, Schegloff, & Jefferson (1974), *Language 50(4)*; LiveKit Agents Benchmarks (2024).
- **[FACT]:** Khoảng lặng chuyển lượt tự nhiên (turn-transition gap) trong giao tiếp con người là 200–250ms. Khi hệ thống voice có độ trễ phản hồi >700–800ms mà không có âm thanh báo hiệu, người dùng sẽ tự động nói bồi ("Alo?", "Nghe không?"), gây va chạm âm thanh (audio collision).
- **[RULE]:** 
  1. Phản hồi tức thì cho turn thông thường phải đạt 200–400ms.
  2. Nếu quá trình xử lý LLM inference hoặc truy vấn cơ sở dữ liệu dự kiến vượt quá 700ms, hệ thống bắt buộc phải phát **Acoustic Filler** (ví dụ: *"Để mình xem...", "Đợi xíu nhé..."*) hoặc âm thanh thinking pulse trong vòng 400ms đầu tiên để chiếm giữ kênh âm thanh (claim the conversational floor).
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Interactive Latency Calibration Slider:* Học viên nghe 3 đoạn hội thoại mô phỏng phản hồi ở các mốc 100ms (giật mình vì quá nhanh), 250ms (tự nhiên), và 900ms (chết lặng). Học viên điều chỉnh thanh trượt độ trễ và kích hoạt acoustic filler để đạt điểm tối ưu trên thang đo độ tự nhiên (Naturalness Score).

#### 1.2. Sub-100ms Barge-In & Cắt tỉa ngữ cảnh (Audible Boundary Truncation)
- **Nguồn:** OpenAI Realtime API Guide; LiveKit Interruption Handling (2024).
- **[FACT]:** Trong kiến trúc Full-Duplex WebRTC, việc ngắt âm thanh (barge-in onset) phải diễn ra dưới 80–100ms kể từ khi phát hiện giọng nói người dùng để loại bỏ cảm giác "máy nói đè lên người".
- **[RULE]:** Ngay khi phát hiện barge-in, client phải lập tức dừng phát audio cục bộ, gửi tín hiệu hủy inference đến LLM, và kích hoạt sự kiện `conversation.item.truncate` với thông số `audio_end_ms` chính xác tại thời điểm người dùng cắt ngang. Nghiêm cấm giữ lại phần văn bản chưa được phát vào ngữ cảnh hội thoại của LLM.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Barge-In Context Debugger:* Hiển thị dòng thời gian audio dạng sóng (waveform) cùng hộp thoại context memory của LLM. Người học kéo mốc cắt âm thanh (scrubber) vào điểm người dùng cắt ngang câu nói, quan sát trực tiếp sự khác biệt giữa trường hợp "có gửi lệnh truncate" (LLM phản hồi ăn khớp) và "quên truncate" (LLM bị ảo giác ngữ cảnh).

#### 1.3. Adaptive VAD vs. Ngưỡng Silence Tĩnh
- **Nguồn:** Silero VAD Repository; LiveKit Agents Turn Detection.
- **[FACT]:** Silero VAD phân tích khung âm thanh 32ms với độ trễ trigger ~30ms, nhưng VAD thuần túy dựa trên năng lượng biên độ không thể phân biệt được từ đệm (backchanneling như *"uh-huh"*, *"vâng"*) với việc ngắt lời thực sự.
- **[RULE]:** Không sử dụng ngưỡng ngắt âm cứng nhắc (hard threshold). Hệ thống phải kết hợp phân loại ngữ âm thích ứng (Adaptive Interruption) và Semantic Endpointing: chỉ nhường quyền nói (yield floor) khi phát hiện ý định ngắt lời thực tế, duy trì phát nếu người dùng chỉ phát ra backchannel hoặc tiếng ho.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Backchannel vs. Interruption Audio Classifier:* Học viên nghe 5 mẫu âm thanh (tiếng ho nhẹ, tiếng *"ừm hửm"*, câu ngắt lời *"khoan đã"*, tiếng thở dài, tiếng còi xe) và thực hiện thao tác kéo thả (drag & drop) vào 2 vùng: "Giữ lượt phát (Keep Playing)" hoặc "Ngắt lượt phát (Barge-in)".

#### 1.4. Conversational Repair & Văn hóa sửa sai không đổ lỗi
- **Nguồn:** Google Conversation Design — Error Handling & Conversational Repair.
- **[FACT]:** Nghiên cứu hành vi của Google chỉ ra rằng thông báo lỗi mang tính kỹ thuật ("Lỗi nhận dạng giọng nói", "Dữ liệu không hợp lệ") kích hoạt phản xạ phòng thủ và gia tăng tỷ lệ thoát tác vụ của người dùng lên hơn 50%.
- **[RULE]:** Nghiêm cấm sử dụng các câu xin lỗi rập khuôn vô cảm hoặc đổ lỗi cho người dùng. Phải sử dụng kỹ thuật Rapid Reprompt hoặc tái cấu trúc câu hỏi một cách tự nhiên (ví dụ: *"Bạn muốn bay vào thứ Bảy hay Chủ nhật?"* thay vì *"Bạn đã nhập sai định dạng ngày"*).
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Dialogue Repair Surgery:* Cung cấp một đoạn kịch bản IVR truyền thống đầy lỗi đổ người dùng. Học viên thực hiện chỉnh sửa trực tiếp trên màn hình, thay thế bằng kỹ thuật conversational repair tôn trọng nguyên lý hợp tác của Grice.

#### 1.5. Cơ chế Xác nhận: Explicit vs. Implicit Grounding
- **Nguồn:** Google Conversation Design Guidelines — Confirmations; Clark & Brennan (1991).
- **[FACT]:** Việc bắt buộc người dùng xác nhận rõ ràng (Explicit Confirmation - *"Bạn có chắc chắn muốn làm việc này không?"*) trong các tác vụ đơn giản làm tăng gấp đôi số lượt thoại (turn count) và gây ức chế tinh thần nặng nề.
- **[RULE]:** 
  1. Chỉ sử dụng **Explicit Confirmation** cho các tác vụ mang tính rủi ro cao, không thể đảo ngược (chuyển tiền, xóa tài khoản, đặt vé có phí).
  2. Mọi tác vụ có thể hoàn tác hoặc tra cứu thông thường bắt buộc phải dùng **Implicit Confirmation** (lồng ghép thông tin đã hiểu vào hành động kế tiếp: *"Đã thêm cà phê sữa vào giỏ hàng. Bạn có muốn chọn thêm bánh ngọt không?"*).
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Matrix Sắp xếp Mức độ Rủi ro (Stakes Sorter):* Học viên nhận 8 kịch bản tình huống thực tế và phân loại vào 2 cột: Explicit Confirmation vs. Implicit Confirmation.

---

### Nhóm 2: Cognitive Load & Voice Pedagogy (1 Idea/Utterance, Chunking, Cowan Limit, Pacing)

#### 2.1. Giới hạn 4 Chunks của Nelson Cowan trong Trí nhớ Âm thanh
- **Nguồn:** Nelson Cowan (2001), *Behavioral and Brain Sciences*.
- **[FACT]:** Trí nhớ làm việc (working memory) của con người trong môi trường âm thanh thuần túy chỉ có khả năng lưu giữ tối đa 3–4 đơn vị thông tin (chunks) trước khi dấu vết thần kinh âm thanh (echoic trace) bị xóa nhòa. Hiệu ứng Primacy và Recency làm cho các mục ở giữa danh sách thoại bị quên gần như hoàn toàn.
- **[RULE]:** Không bao giờ liệt kê quá **3 lựa chọn** trong một lượt thoại bằng giọng nói. Luôn đưa danh mục định hướng lên trước, chi tiết thao tác theo sau.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Auditory Overload Tester:* Hệ thống đọc to một danh sách 7 món hàng không hiển thị văn bản. Sau khi nghe xong, học viên được yêu cầu bấm chọn lại các món vừa nghe để tự cảm nhận sự đứt gãy trí nhớ.

#### 2.2. Kiểm tra "Một Hơi Thở" (The "One Breath Test")
- **Nguồn:** Amazon Alexa Design Guide — Be Clear; Google Conversation Design.
- **[FACT]:** Người nghe chỉ có thể duy trì sự chú ý tập trung liên tục vào một mệnh đề âm thanh trong khoảng thời gian tương đương một chu kỳ thở bình thường (khoảng 4–6 giây, tương đương 20–25 từ).
- **[RULE]:** Mọi câu thoại phản hồi của trợ lý giọng nói bắt buộc phải vượt qua "The One Breath Test": độ dài tối đa không quá 25–30 từ và không quá 2 câu ngắn trong một lượt nói trước khi trả quyền nói lại cho người dùng.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Voice Script Word Diet:* Hiển thị một câu trả lời dài 60 từ của AI. Học viên sử dụng công cụ gạch bỏ (strike-through) để loại bỏ các từ thừa, biến câu thoại dài dòng thành một câu súc tích dưới 20 từ.

#### 2.3. Nguyên tắc 1 Ý Tưởng / Một Lượt Thoại (1 Idea per Utterance)
- **Nguồn:** Amazon Alexa Design Guide — Tenets of Situational Design; Sweller (1988).
- **[FACT]:** Khi một câu hỏi bằng giọng nói chứa 2 yêu cầu hoặc 2 quyết định phức hợp (Compound Questions), hơn 60% người dùng chỉ trả lời vế thứ hai hoặc đưa ra câu trả lời mơ hồ, làm đứt gãy luồng hội thoại.
- **[RULE]:** Nghiêm cấm đặt câu hỏi kép trong một lượt nói. Mỗi lượt thoại chỉ truyền tải đúng một khái niệm hoặc yêu cầu duy nhất một quyết định từ người dùng.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Compound Question Splitter:* Học viên kéo tách một câu hỏi kép phức tạp thành 2 lượt thoại tuần tự (multi-turn progressive disclosure).

#### 2.4. Nhịp điệu, Tốc độ Phát âm (Prosody) và Khoảng Dừng Âm học
- **Nguồn:** Apple HIG — Playing Audio; Amazon Alexa SSML Guide.
- **[FACT]:** Tốc độ tiếp nhận âm thanh hội thoại lý tưởng dao động từ 140 đến 160 từ/phút (WPM). Giọng đọc nhân tạo không có khoảng nghỉ giữa các mệnh đề sẽ làm giảm khả năng ghi nhớ nội dung giáo dục tới 35%.
- **[RULE]:** Nội dung âm thanh giảng dạy phải duy trì tốc độ 145–155 WPM và bắt buộc phải chèn thẻ ngắt âm SSML `<break time="250ms"/>` hoặc `<break time="400ms"/>` giữa các vế câu độc lập.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *SSML Pacing Tuner:* Học viên điều chỉnh thanh trượt tốc độ (Rate: 80%–120%) và đặt các điểm ngắt `<break>` trên đoạn mã SSML mẫu của bài học, sau đó bấm nghe trực tiếp để thẩm định chất lượng tiếp thu.

---

### Nhóm 3: Interactive Learning Loops (Explain -> Demonstrate -> Practice -> Feedback -> Retry -> Transfer)

#### 3.1. Active Learning & Guided Inquiry vs. Passive Lecturing
- **Nguồn:** Brilliant.org Learning Principles; Freeman et al. (2014), *PNAS*.
- **[FACT]:** Nghiên cứu meta-analysis trên 225 công trình của PNAS chứng minh rằng phương pháp học chủ động (Active Learning) giảm tỷ lệ trượt môn 33% và tăng kết quả kiểm tra lên gần 0.5 độ lệch chuẩn so với việc nghe giảng thụ động.
- **[RULE]:** Nghiêm cấm trợ lý âm thanh độc thoại thuyết giảng liên tục quá 60 giây. Mọi khối kiến thức đều phải kích hoạt phản hồi tương tác (nói, bấm, kéo thả) từ học viên ngay sau khi đưa ra thông tin nền tảng.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Socratic Voice Discovery:* Thiết kế kịch bản dạy khái niệm "Tỉ lệ tương phản màu sắc". AI không đọc định nghĩa lý thuyết mà đặt câu hỏi tương tác để người học tự rút ra nguyên lý.

#### 3.2. Vòng Lặp Sư Phạm 6 Giai Đoạn (The 6-Stage Pedagogy Loop)
- **Nguồn:** Fisher & Frey (2013); Uxcel Learning Methodology.
- **[FACT]:** Nếu không có giai đoạn Sửa sai (Retry) và Vận dụng mở rộng (Transfer), kiến thức mới tiếp thu sẽ suy giảm hơn 70% trong vòng 48 giờ theo đường cong quên lãng Ebbinghaus.
- **[RULE]:** Mọi bài học giọng nói phải tuân thủ nghiêm ngặt chu trình khép kín 6 bước: Explain → Demonstrate → Practice → Feedback → Retry → Transfer.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Pedagogy Flowchart Builder:* Học viên kéo thả các khối chức năng để ráp hoàn chỉnh một quy trình 6 bước cho bài học "Touch Target 44x44pt" trên nền tảng Canvas tương tác.

#### 3.3. Trực Giác Nguyên Lý Đầu Tiên Trước Khi Hình Thức Hóa (First-Principles Intuition)
- **Nguồn:** Brilliant.org Pedagogy Whitepaper; Jerome Bruner (1966).
- **[FACT]:** Việc đưa thuật ngữ học thuật, công thức trừu tượng hoặc thuật ngữ viết tắt ra trước khi người học hình thành mô hình tâm trí trực quan sẽ gây nghẽn nhận thức ngoại lai (extraneous cognitive load).
- **[RULE]:** Nghiêm cấm giới thiệu thuật ngữ chuyên ngành (WCAG, Fitts's Law, Affordance) trước khi người học trải nghiệm hiện tượng thực tế thông qua các tương tác vật lý hoặc phép so sánh đời sống.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Fitts's Law Target Sizing Game:* Trước khi nhắc đến tên "Định luật Fitts", màn hình hiện 2 nút bấm: một nút nhỏ xíu ở góc xa và một nút to ở ngay ngón tay cái. Học viên bấm thử cả hai, cảm nhận sự chênh lệch rồi AI mới công bố định luật.

---

### Nhóm 4: Feedback, Error & Mastery (Instant Feedback, Hint Ladder, Formative Assessment)

#### 4.1. Thang Đo Gợi Ý 4 Bậc (The 4-Tier Progressive Hint Ladder)
- **Nguồn:** Intelligent Tutoring Systems (ITS) Research; Brilliant.org Adaptive Guidance.
- **[FACT]:** Cung cấp ngay đáp án đúng khi người học làm sai sẽ triệt tiêu cảm giác thỏa mãn tự khám phá ("Aha! moment") và làm suy giảm năng lực tự học. Ngược lại, không có gợi ý sẽ dẫn đến tâm lý thất vọng và bỏ cuộc.
- **[RULE]:** Hệ thống gia sư giọng nói bắt buộc phải hỗ trợ cấu trúc gợi ý bậc thang tối thiểu 3–4 nấc (Nudge → Principle → Next Step → Bottom-out Solution), không bao giờ nhảy thẳng vào đáp án cuối cùng ở lần sai đầu tiên.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Hint Ladder Authoring Workshop:* Học viên biên soạn kịch bản thoại cho 4 nấc gợi ý của một câu hỏi tình huống thiết kế UI.

#### 4.2. Amazon Alexa 3-Tier Progressive Reprompting
- **Nguồn:** Amazon Alexa Design Guide — Handle Errors.
- **[FACT]:** Việc lặp lại nguyên văn câu hỏi cũ khi người dùng im lặng hoặc trả lời không đúng ý khiến 65% người dùng nản lòng hoặc phản ứng gắt gỏng với trợ lý ảo.
- **[RULE]:** Mỗi lần reprompt đều phải gia tăng mức độ hỗ trợ (escalating detail), cung cấp ví dụ mẫu cụ thể (exemplar phrasing) và giới hạn vòng lặp lỗi ở tối đa 3 lượt trước khi đưa ra giải pháp thoát hiểm (fallback/handoff).
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Reprompt Escalator Simulation:* Học viên viết kịch bản xử lý cho tình huống người học im lặng trong 5 giây sau câu hỏi kiến thức qua 3 lượt leo thang gợi ý.

#### 4.3. Đánh Giá Quá Trình Đa Thức (Formative Multi-Modal Testing - Chuẩn Uxcel)
- **Nguồn:** Uxcel Interactive Micro-Exercises; Black & Wiliam (1998).
- **[FACT]:** Kiểm tra đánh giá quá trình (Formative Assessment) kết hợp phản hồi giải thích tức thì mang lại hiệu quả học tập vượt trội gấp 2 lần so với việc làm bài kiểm tra trắc nghiệm tổng kết cuối khóa.
- **[RULE]:** Nền tảng học qua giọng nói khi kết hợp màn hình hiển thị phải hỗ trợ các dạng tương tác xúc giác trực quan: Spot the Error, Tune the Slider, Drag & Drop.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Audio-Visual Micro-Challenge:* AI phát âm thanh hướng dẫn, học viên chạm vào điểm lỗi trên mockup; hệ thống lập tức phát earcon thành công kèm lời khen ngợi bằng giọng nói.

---

### Nhóm 5: Trust, Accessibility & AI Behavior (Disclosure, Uncertainty, Noise, Safety)

#### 5.1. Bắt Buộc Minh Bạch Danh Tính AI (Mandatory AI Disclosure)
- **Nguồn:** OpenAI Voice Safety Guidelines; EU Artificial Intelligence Act (Article 50).
- **[FACT]:** Đạo luật AI của Liên minh Châu Âu (EU AI Act) và chính sách của OpenAI bắt buộc mọi hệ thống giao tiếp bằng giọng nói tổng hợp phải công khai minh bạch danh tính máy móc để phòng chống gian lận và mạo danh con người.
- **[RULE]:** Hệ thống phải thông báo rõ ràng là trợ lý AI ngay trong lượt chào đầu tiên hoặc ngữ cảnh giới thiệu. Tuyệt đối không giả mạo danh tính cá nhân thật, không tuyên bố có cảm xúc sinh học hay cơ thể vật lý của con người.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Onboarding Persona Scripting:* Học viên viết lời chào mở đầu (Onboarding Greeting) cho 3 loại trợ lý (Gia sư, Tài chính, Y tế), đảm bảo nêu rõ danh tính AI một cách tự nhiên và ấm áp.

#### 5.2. Quản Lý Audio Session, Audio Ducking & Xử Lý Gián Đoạn (Chuẩn Apple HIG)
- **Nguồn:** Apple HIG — Playing Audio; Apple AVAudioSession Documentation.
- **[FACT]:** Người dùng coi thiết bị cá nhân là không gian riêng tư. Ứng dụng tự ý phát âm thanh khi máy đang bật chế độ Im Lặng hoặc không nhường quyền ưu tiên cho cuộc gọi đến sẽ ngay lập tức đánh mất sự tin tưởng của người dùng.
- **[RULE]:**
  1. **Primary Interruption (Cuộc gọi đến, Siri):** Tạm dừng toàn bộ âm thanh và lưu trạng thái ngay lập tức.
  2. **Transient Interruption (Thông báo, âm thanh GPS):** Thực hiện cơ chế **Audio Ducking** (tự động giảm 70% âm lượng giọng nói trong thời gian thông báo vang lên và hồi phục mượt mà).
  3. Tôn trọng nút gạt im lặng phần cứng trên thiết bị.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Audio Interruption Matrix Mapping:* Học viên hoàn thành bảng điều khiển ánh xạ 4 sự kiện gián đoạn với hành vi chính xác của ứng dụng (Pause, Duck, Mute, Disconnect).

#### 5.3. Earcons, Sonic Branding và Mã Hóa Kép Xúc Giác (Haptic Dual-Coding)
- **Nguồn:** Apple HIG — Feedback & Playing Haptics; Blattner et al. (1989).
- **[FACT]:** Tín hiệu âm thanh (Earcon) khi được ghép đôi đồng bộ với rung phản hồi xúc giác (Haptics) giúp giảm 22% thời gian phản ứng của người dùng, đồng thời đảm bảo khả năng tiếp cận trọn vẹn cho người khiếm thính hoặc trong môi trường có tiếng ồn lớn.
- **[RULE]:** Mọi trạng thái hệ thống quan trọng (Lắng nghe, Đang suy nghĩ, Thành công, Lỗi) bắt buộc phải có đủ bộ 3 tín hiệu đồng bộ: **Earcon (Âm thanh)** + **Haptics (Rung)** + **Visual Cue (Thị giác)**. Không bao giờ phát âm thanh đơn độc.
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Earcon & Haptic Orchestration Studio:* Học viên lựa chọn dải tần số âm thanh (Hz) và cấu hình cường độ rung cho 4 trạng thái cốt lõi của trợ lý học tập DESIGN:OS.

#### 5.4. Độ Tin Cậy Định Chuẩn & Minh Bạch Sự Không Chắc Chắn (Calibrated Confidence)
- **Nguồn:** Google Conversation Design — Grice's Maxim of Quality; Amershi et al. (2019), *Microsoft Research*.
- **[FACT]:** Khi một hệ thống AI đưa ra câu trả lời sai lệch (hallucination) với giọng điệu tự tin trôi chảy, mức độ suy giảm niềm tin của người dùng cao gấp 3 lần so với trường hợp hệ thống trung thực thừa nhận mình không chắc chắn.
- **[RULE]:** Khi độ tin cậy nhận dạng (ASR Confidence Score) dưới ngưỡng an toàn (< 0.75), hệ thống tuyệt đối không được tự ý đoán mò hành động. Phải thể hiện sự không chắc chắn có định chuẩn và yêu cầu làm rõ (ví dụ: *"Có phải bạn vừa nói là...?"* thay vì tự động thực thi).
- **[RECOMMENDATION] (Dạng bài tập tương tác):**
  * *Confidence Threshold Switchboard:* Cung cấp 3 file âm thanh người dùng nói trong môi trường tiếng ồn. Học viên phân tích điểm Confidence Score và thiết lập phản hồi tương ứng: Thực thi ngay (High), Hỏi lại nhẹ (Medium), Yêu cầu nói lại (Low).

---

## 4. Bảng Tổng Hợp So Sánh Đa Nguồn (Cross-Source Synthesis Matrix)

| Chủ Đề / Vấn Đề | Apple HIG | Google Assistant | Amazon Alexa | OpenAI / LiveKit | Sư Phạm (Brilliant/Uxcel) | Chuẩn DESIGN:OS Voice UX |
|---|---|---|---|---|---|---|
| **Turn-taking Latency** | Instant response | Gricean cadence | One Breath rule | Target <400ms, Acoustic filler | Active feedback <1s | **200–400ms; filler at 400ms** |
| **Barge-in Cut-off** | Pause on interrupt | Cooperative yield | Dynamic cutoff | WebRTC Sub-100ms + truncate | Instant pause on input | **Sub-100ms + mandatory truncate** |
| **Cognitive Chunking** | Simple, clear | Cowan 4 chunks | Max 3 choices | Concise system prompts | Micro-learning 1 idea/card | **Max 3 options, 1 idea/utterance** |
| **Error Handling** | Don't disrupt | Conversational repair | 3-tier reprompting | Graceful fallback | Hint ladder 4 rungs | **4-tier hint ladder, no blame** |
| **Accessibility & Audio** | Haptic dual-coding | Multimodal chips | Visual cards sync | Streaming transcripts | Tactile + Visual tasks | **Trio: Earcon + Haptic + Visual** |
| **AI Transparency** | Clear assistant identity | Persona consistency | Alexa persona | Mandatory AI disclosure | Guided tutor persona | **Mandatory AI disclosure on onboarding** |
