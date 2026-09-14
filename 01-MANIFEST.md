# 01-MANIFEST: Voice UX Knowledge Base Inventory

> Bảng kiểm kê (inventory) toàn bộ các tài liệu trong Voice UX & Conversational Design Knowledge Base, phân định rõ Mục đích, Đối tượng độc giả, Trạng thái phát triển và Cơ sở chứng cứ thực nghiệm.

---

## Bảng Kiểm Kê 17 Tài Liệu Cốt Lõi

| ID | Tên Tài Liệu | Phân Loại | Mục Đích Cốt Lõi | Đối Tượng Đọc | Trạng Thái | Cơ Sở Chứng Cứ (Evidence) |
|---|---|---|---|---|---|---|
| **M00** | [`README.md`](./README.md) | Navigation | Master Index, bản đồ kiến trúc & phân cấp VUI Maturity Levels | Toàn team | **Stable** | Standard UX Architecture |
| **M01** | [`CONTEXT.md`](./CONTEXT.md) | Governance | Bảng từ điển thuật ngữ chuẩn hóa (Canonical Terms vs Anti-terms) | Toàn team | **Stable** | Grice, Clark & Brennan, NNG |
| **F01** | [`01-foundations/mental-models-and-affordance.md`](./01-foundations/mental-models-and-affordance.md) | Foundations | Giải quyết Vực thẳm thực thi (Gulf of Execution), tính vô hình & thoáng qua | Designer | **Stable** | Don Norman, Cathy Pearl |
| **F02** | [`01-foundations/conversational-psychology.md`](./01-foundations/conversational-psychology.md) | Foundations | 4 Phương châm Grice, cấu trúc lượt lời & giới hạn 4 khối nhớ ngắn hạn | Designer, PM | **Stable** | Paul Grice (1975), Cowan (2001) |
| **F03** | [`01-foundations/vui-heuristics.md`](./01-foundations/vui-heuristics.md) | Foundations | Chuyển dịch 10 Heuristics của Nielsen sang không gian âm thanh | Designer, QA | **Stable** | Nielsen Norman Group (NN/g) |
| **IP01** | [`02-interaction-patterns/turn-taking-and-barge-in.md`](./02-interaction-patterns/turn-taking-and-barge-in.md) | Patterns | Cơ chế ngắt lời sub-100ms, Semantic VAD & cắt tỉa bộ nhớ (Audible Truncation) | Designer, Eng | **Validated** | Full-duplex WebRTC research |
| **IP02** | [`02-interaction-patterns/error-recovery-and-repair.md`](./02-interaction-patterns/error-recovery-and-repair.md) | Patterns | 3-tier progressive prompting, nguyên tắc không đổ lỗi, grounding | Designer | **Stable** | Google Assistant, Conversational Analysis |
| **IP03** | [`02-interaction-patterns/audio-feedback-and-earcons.md`](./02-interaction-patterns/audio-feedback-and-earcons.md) | Patterns | Thiết kế Earcons, sonic branding, phân bổ tần số 4 trạng thái cốt lõi | Sound Designer | **Validated** | Acoustic UX, Apple/Google Sound Design |
| **IP04** | [`02-interaction-patterns/multimodal-handshake.md`](./02-interaction-patterns/multimodal-handshake.md) | Patterns | Bàn giao Voice + GUI, phân tải hiển thị, ma trận Hands-busy/Eyes-free | Product Designer| **Stable** | Cheryl Platz (*Design Beyond Devices*) |
| **DS01** | [`03-conversational-design-system/persona-and-tone.md`](./03-conversational-design-system/persona-and-tone.md) | Design System | Bản đồ 4 trục persona, tránh Uncanny Valley & bẫy ELIZA, thấu cảm chức năng | Content, UX | **Stable** | Erika Hall, Reeves & Nass |
| **DS02** | [`03-conversational-design-system/prompt-and-dialog-engineering.md`](./03-conversational-design-system/prompt-and-dialog-engineering.md) | Design System | Viết kịch bản cho đôi tai, System prompt chuẩn Voice LLM, SSML prosody | Prompt Eng, UX | **Validated** | W3C SSML 1.1, LLM System Prompts |
| **DS03** | [`03-conversational-design-system/latency-budgets.md`](./03-conversational-design-system/latency-budgets.md) | Design System | Phân bổ ngân sách độ trễ 300ms, Acoustic Fillers & kiến trúc Native S2S | Architect, Perf | **Validated** | Psychoacoustics, LiveKit benchmarks |
| **BM01** | [`04-benchmarks-and-case-studies/industry-benchmarks.md`](./04-benchmarks-and-case-studies/industry-benchmarks.md) | Benchmarks | So sánh thực chiến OpenAI Realtime, Gemini Live, Siri, Hume EVI, CarPlay | Toàn team | **Stable** | Empirical Benchmarking 2026 |
| **BM02** | [`04-benchmarks-and-case-studies/open-source-repos-and-tools.md`](./04-benchmarks-and-case-studies/open-source-repos-and-tools.md) | Tooling | Khảo sát LiveKit Agents, Pipecat AI, Silero VAD, PatternFly Guidelines | Eng, Designer | **Stable** | GitHub Open-source Ecosystem |
| **DB01** | [`05-debate-and-tradeoffs/5-persona-debate.md`](./05-debate-and-tradeoffs/5-persona-debate.md) | Strategy | Tranh biện 5 chuyên gia: STT-LLM-TTS vs S2S, Privacy, 5 cấm kỵ dùng Voice | Tech Lead, PM | **Validated** | `ak:predict` Multi-persona debate |
| **CK01** | [`06-checklists-and-heuristics/vui-design-checklist.md`](./06-checklists-and-heuristics/vui-design-checklist.md) | Production QA | Checklist 25 tiêu chuẩn nghiệm thu trước khi release ra thị trường | QA, Tech Lead | **Production** | Industry Production Standards |
| **CK02** | [`06-checklists-and-heuristics/usability-testing-protocol.md`](./06-checklists-and-heuristics/usability-testing-protocol.md) | Research | Quy trình test người dùng Wizard of Oz (WoZ), kịch bản 4 bước & chỉ số TCR/CER | UX Researcher | **Production** | Dahlbäck WoZ Methodology |

---

## Quy Ước Nhãn Chứng Cứ Trong Tài Liệu

Để đảm bảo tính trung thực kỹ thuật và tránh việc biến giả định chủ quan thành "best practice", mọi luận điểm trong Knowledge Base được phân cấp bằng 4 nhãn:

- `[FACT]`: Sự thật vật lý, sinh học thính giác hoặc tâm lý học đã được khoa học chứng minh qua thí nghiệm (ví dụ: Cowan 4-chunk limit, độ trễ nhận thức 200ms).
- `[RULE]`: Quy tắc thiết kế bắt buộc không được vi phạm (ví dụ: cấm danh sách âm thanh quá 3 mục, cấm đọc mã số thẻ ngân hàng nơi công cộng).
- `[RECOMMENDATION]`: Đề xuất kinh nghiệm dựa trên thực tế triển khai sản phẩm hàng đầu (ví dụ: dùng xưng hô "Mình - Bạn", đặt ngưỡng VAD wait 800ms).
- `[OPEN QUESTION]`: Vấn đề mở hoặc nan đề kỹ thuật còn đang tranh luận (ví dụ: mô hình speech-to-speech có nên nhại cảm xúc khóc/cười của người dùng hay không).
