# 03-AUDIT-RUBRIC: Bộ Tiêu Chí Đánh Giá 100 Điểm & 6 Hard Gates

> Khung tiêu chuẩn kiểm định chất lượng chuyên sâu (Rubric) dành cho Voice UX & Conversational Design, thiết lập bởi chuyên gia Voice AI cấp cao, bao gồm 4 trụ cột đánh giá (100 điểm) và 6 cửa chặn sinh tử (Hard-Fail Gates).

---

## 🚦 6 Cửa Chặn Sinh Tử (Hard-Fail Gates)

Nếu vi phạm **bất kỳ 1 trong 6 cửa chặn này**, toàn bộ tính năng hoặc tài liệu thiết kế bị **ĐÁNH RỚT (VETO)** và bị xếp loại **`NOT PRODUCTION READY`**, bất kể tổng điểm các phần khác cao đến đâu:

| Mã Gate | Tên Cửa Chặn | Điều Kiện Đánh Rớt Ngay Lập Tức (Hard-Fail Trigger) |
|---|---|---|
| **G1** | **Measurable Timing** | Không có định nghĩa định lượng rõ ràng về độ trễ nhận thức (perceived latency) và ranh giới các mốc thời gian (0-300ms, 500ms, 800ms). |
| **G2** | **Endpointing Rigor** | Đánh đồng khoảng lặng tĩnh (Silence timeout) với điểm dừng ngữ nghĩa (Semantic End-of-turn). |
| **G3** | **Barge-in Reality** | Coi khả năng ngắt lời (Barge-in) là một công tắc bật/tắt (Toggle On/Off) đơn thuần thay vì một máy trạng thái (State Machine). |
| **G4** | **Audible Context** | Cho phép bộ nhớ hội thoại (Conversation Memory) lưu lại phần câu nói của bot mà người dùng chưa hề nghe thấy do bị ngắt giữa chừng. |
| **G5** | **Structured Repair** | Không có chiến lược sửa sai đàm thoại lũy tiến (chỉ lặp lại một câu *"Xin lỗi tôi không hiểu"* quá 2 lần). |
| **G6** | **Test Traceability** | Checklist thiết kế không thể truy vết ngược về kịch bản kiểm thử người dùng thực tế (Usability Test Protocol). |

---

## 📊 Bảng Điểm Đánh Giá 100 Điểm (Scoring Matrix)

```
Tổng điểm: 100 Điểm
├── 1. Latency & Pacing (Độ trễ & Nhịp điệu)        : 30 Điểm
├── 2. Barge-in & Turn-taking (Ngắt lời & Lượt nói) : 30 Điểm
├── 3. Conversational Psychology (Tâm lý đàm thoại) : 30 Điểm
└── 4. Cross-Document Integrity (Tính nhất quán)    : 10 Điểm
```

---

### 1. Latency & Pacing (30 Điểm)

| Tiêu Chí | Điểm | Yêu Cầu Đạt Chuẩn |
|---|---|---|
| **L1. Latency Anatomy** | 6 | Bóc tách rõ ràng 4 thành phần trễ: Client VAD, Network Transport, TTFT (Time to first token/audio), Audio Buffering. |
| **L2. Conversational Sweet Spot** | 6 | Thiết kế kiến trúc bảo đảm độ trễ đàm thoại thông thường duy trì trong ngưỡng `< 400ms`. |
| **L3. Acoustic Fillers & Bridging** | 6 | Có cơ chế từ đệm tự nhiên (*"Dạ,"*, *"Để mình kiểm tra"*) hoặc âm rung nền nhẹ khi tác vụ kéo dài `> 600ms`. |
| **L4. Dead-Air Prevention** | 6 | Không bao giờ để im lặng vô tuyến quá 1 giây mà không có phản hồi âm thanh hoặc xúc giác. |
| **L5. Network Adaptation** | 6 | Cơ chế hạ cấp nhẹ nhàng (Graceful degradation) khi mạng di động chập chờn (Adaptive Jitter Buffer). |

---

### 2. Barge-In & Turn-Taking (30 Điểm)

| Tiêu Chí | Điểm | Yêu Cầu Đạt Chuẩn |
|---|---|---|
| **B1. Interruption State Model** | 6 | Phân tách rõ ràng trạng thái ngắt lời khi: Đang nghe / Đang nghĩ / Đang nói / Đang gọi API. |
| **B2. Interruption Latency** | 5 | Tốc độ dừng loa từ khi người dùng cất tiếng đạt chuẩn `p50 < 80ms`, `p95 < 120ms`. |
| **B3. Intent vs Noise Detection** | 5 | Phân biệt tiếng ngắt lời thực thụ với tiếng ho, tiếng thở, tiếng cười, tiếng đệm nhịp (*"ừm"*) hoặc tạp âm môi trường. |
| **B4. Audible Boundary Truncation** | 5 | **BẮT BUỘC**: Cắt tỉa lịch sử ngữ cảnh đúng tại giây người dùng cất tiếng, loại bỏ hoàn toàn phần câu phía sau. |
| **B5. Post-Interruption Recovery** | 5 | Trợ lý ảo ưu tiên ngay ý định mới của câu ngắt lời mà không giải thích vòng vo. |
| **B6. Compliance & Safety Exceptions** | 4 | Quy định rõ các câu thoại pháp lý/khẩn cấp không được phép ngắt lời hoặc cần xác nhận lại. |

---

### 3. Conversational Psychology & Grounding (30 Điểm)

| Tiêu Chí | Điểm | Yêu Cầu Đạt Chuẩn |
|---|---|---|
| **P1. Grounding (Clark & Brennan)** | 5 | Phân biệt rõ: Xác nhận ngầm (Implicit) cho rủi ro thấp vs Xác nhận tường minh (Explicit) cho giao dịch quan trọng. |
| **P2. Turn-Taking Psychology** | 5 | Ngắt nghỉ tự nhiên ~200-300ms; không cướp lời nhưng không phản hồi chậm chạp. |
| **P3. 3-Tier Escalating Repair** | 5 | Quy trình 3 bước: Lần 1 nhắc nhẹ -> Lần 2 đưa ví dụ mẫu -> Lần 3 thu hẹp lựa chọn / chuyển kênh an toàn. |
| **P4. Cognitive Load & Chunking** | 4 | Tuân thủ nghiêm ngặt quy tắc Cowan: Tối đa 3 lựa chọn trong 1 danh sách âm thanh; câu dưới 30 từ. |
| **P5. Agency & User Control** | 4 | Từ khóa khẩn cấp (*"Dừng lại", "Quay lại"*) hoạt động toàn cục 100% các màn hình. |
| **P6. Trust & Transparency** | 4 | Minh bạch danh tính máy móc; không che giấu lỗi; không bịa đặt thông tin khi không chắc chắn. |
| **P7. Functional Empathy** | 3 | Tránh bẫy ELIZA và Uncanny Valley; thấu cảm bằng hành động và tốc độ giải quyết thay vì đóng kịch cảm xúc giả. |

---

### 4. Cross-Document Integrity (10 Điểm)

| Tiêu Chí | Điểm | Yêu Cầu Đạt Chuẩn |
|---|---|---|
| **I1. Canonical Glossary Consistency** | 3 | Toàn bộ 17 tài liệu dùng chung 1 định nghĩa duy nhất cho các thuật ngữ tại `CONTEXT.md`. |
| **I2. Architectural Coherence** | 3 | Không có mâu thuẫn giữa Foundations, Patterns, Design System và Benchmarks. |
| **I3. Traceability to Testing** | 2 | Mọi quy tắc trong `vui-design-checklist.md` đều có thể đo lường trong `usability-testing-protocol.md`. |
| **I4. Provenance & Evidence** | 2 | Mỗi khẳng định đều được gắn nhãn `[FACT]`, `[RULE]`, `[RECOMMENDATION]`, `[OPEN QUESTION]`. |

---

## 🏆 Thang Xếp Hạng Kết Quả (Maturity Tiers)

```
90 - 100 Điểm + PASS 6 Gates  ──►  Tier 1: PRODUCTION READY (Sẵn sàng triển khai quy mô lớn)
75 - 89 Điểm  + PASS 6 Gates  ──►  Tier 2: FIELD TEST READY (Được phép thử nghiệm người dùng hạn chế)
< 75 Điểm   HOẶC FAIL 1 Gate  ──►  Tier 3: NOT PRODUCTION READY (Bị chặn ra mắt, cần chỉnh sửa)
```
