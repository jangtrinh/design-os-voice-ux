# 06-ASSESSMENT-MASTERY: Khung Đánh Giá Năng Lực & Tiêu Chuẩn Chứng Chỉ

> Tiêu chuẩn phân tầng Free vs Pro, ma trận rubric chấm điểm thực nghiệm và điều kiện cấp chứng chỉ Voice UX Production Architect.

---

## 1. Phân Tầng Cấp Độ: Free Level vs. Pro Level

| Tiêu Chí | Free Level (Cộng Đồng & Người Mới) | Pro Level (Kỹ Sư & Doanh Nghiệp) |
|---|---|---|
| **Mục tiêu** | Hiểu bản chất tâm lý & trực giác thiết kế | Làm chủ kiến trúc, code production & SLA |
| **Tương tác** | Visual interactive widget, audio A/B | Real-time WebRTC sandbox, LiveKit/Pipecat lab |
| **Thực hành** | Kéo slider thông số có sẵn | Viết code cấu hình, inject lỗi mạng, tune VAD |
| **Độ sâu bài test** | Micro-quiz nhận thức, spot error đơn giản | 30+ adversarial scenarios, audit agent thật |
| **Đầu ra** | Huy hiệu hoàn thành bài học (Badge) | Chứng chỉ thực chiến & báo cáo thẩm định ADR |

---

## 2. Rubric Đánh Giá Thực Nghiệm (Empirical Assessment Rubric)

Để đạt chứng chỉ Pro trong DESIGN:OS Voice UX Academy, đồ án hoặc bài test của học viên phải vượt qua 5 tiêu chí định lượng đo lường bằng telemetry thật:

### Tiêu chí 1: End-of-Turn Latency (Trọng số 25%)
- *Xuất sắc (Pass):* P50 latency < 500ms và P95 latency < 750ms trên đường truyền 4G tiêu chuẩn. Có phát Acoustic Filler hoặc Earcon nếu xử lý vượt quá 600ms.
- *Không đạt (Fail):* P95 latency > 1000ms mà không có bất kỳ phản hồi thính giác tức thời nào.

### Tiêu chí 2: Barge-in Reaction & Truncation (Trọng số 25%)
- *Xuất sắc (Pass):* Loa client ngắt âm thanh hoàn toàn trong < 100ms kể từ khi mic phát hiện tiếng nói. Có kích hoạt `conversation.item.truncate` cắt sạch text thừa trong context memory.
- *Không đạt (Fail):* Âm thanh loa tiếp tục phát > 200ms gây va chạm âm thanh, hoặc không cắt ngữ cảnh gây ảo giác ở lượt thoại kế tiếp.

### Tiêu chí 3: False Interruption Resilience (Trọng số 20%)
- *Xuất sắc (Pass):* Tỷ lệ cướp lời nhầm (False Interruption Rate) < 5% trong môi trường nhiễu âm 60dB (tiếng ho, tiếng thở dài, tiếng gõ bàn phím).
- *Không đạt (Fail):* Tỷ lệ cướp lời nhầm > 12%, ngắt lời liên tục khi người dùng chỉ phát ra âm thanh đệm (*"ừm"*, *"à"*).

### Tiêu chí 4: Cognitive Load & Information Density (Trọng số 15%)
- *Xuất sắc (Pass):* Mọi câu phản hồi đều vượt qua The One Breath Test (< 25 từ). Danh sách lựa chọn không bao giờ vượt quá 3 mục.
- *Không đạt (Fail):* Đọc menu thoại > 3 mục hoặc đọc câu thoại kéo dài > 40 từ không có khoảng nghỉ.

### Tiêu chí 5: Graceful Conversational Repair (Trọng số 15%)
- *Xuất sắc (Pass):* Không đổ lỗi cho người dùng. Khôi phục ngữ cảnh sau lỗi trong vòng 1–2 lượt bằng kỹ thuật Rapid Reprompt hoặc thu hẹp câu hỏi.
- *Không đạt (Fail):* Đổ lỗi ("Bạn nói sai rồi") hoặc lặp lại nguyên văn câu hỏi cũ khi nhận dạng thất bại.
