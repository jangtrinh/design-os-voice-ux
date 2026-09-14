# 09-SOURCE-COMPARISON-MATRIX: Bảng Đối Chiếu Đa Nguồn (Multi-Vendor Comparison Matrix)

> Bảng đối chiếu chéo các giải pháp kỹ thuật và sư phạm giữa 7 tổ chức hàng đầu nhằm xây dựng một bộ tiêu chuẩn trung lập, thực chứng và bền vững cho DESIGN:OS Voice UX Academy.

---

## 1. Ma Trận Đối Chiếu Chi Tiết Theo Chủ Đề

| Lĩnh Vực / Vấn Đề | Apple HIG (Siri & Audio) | Google Assistant / CxD | Amazon Alexa Design | OpenAI Realtime API | LiveKit Agents & WebRTC | Sư Phạm (Brilliant / Uxcel) | Tiêu Chuẩn Chuẩn Hóa DESIGN:OS Voice UX |
|---|---|---|---|---|---|---|---|
| **1. Turn-taking Latency** | Instant response ưu tiên cao | Phản xạ theo Gricean Maxims | Tuân thủ One Breath Test | Mục tiêu streaming audio tức thì | Benchmark P50 < 500ms; VAD adaptive | Phản hồi dưới 1 giây giữ nhịp chú ý | **200–400ms target; bắt buộc Acoustic Filler nếu >700ms** |
| **2. Barge-in / Interruption** | Tạm dừng khi có can thiệp | Hợp tác nhường lượt nói | Ngắt âm khi phát hiện intent mới | Gửi lệnh `truncate` với `audio_end_ms` | Sub-100ms client audio cancellation | Tạm dừng ngay khi học viên chạm/nói | **Sub-100ms cut-off + cắt sạch context memory thừa** |
| **3. Dung Lượng Lượt Thoại** | Rõ ràng, tối giản câu từ | Định luật Cowan 4 chunks | Tối đa 3 lựa chọn thoại | Giới hạn token output LLM súc tích | Khuyên dùng câu ngắn cho streaming | Micro-learning: 1 khái niệm/card | **Tối đa 3 lựa chọn âm thanh; The One Breath Test (<25 từ)** |
| **4. Xử Lý Khi Nhận Dạng Lỗi** | Không gây gián đoạn khó chịu | Conversational repair không đổ lỗi | 3-tier progressive reprompting | Graceful fallback & error event | Fallback audio recovery | Hint ladder 4 bậc; phản hồi tích cực | **Thang gợi ý 4 bậc; reprompt leo thang; cấm đổ lỗi** |
| **5. Phản Hồi Trạng Thái** | Haptic + Earcon đồng bộ | Visual chips + spoken cue | Voice prompt + LED ring | WebSocket event telemetry | Data packets + WebRTC track states | Earcon âm thanh + hiệu ứng màu sắc | **Trio đồng bộ: Earcon (Audio) + Haptics (Rung) + Visual Cue** |
| **6. Minh Bạch Danh Tính AI** | Tuyên bố rõ trợ lý Siri | Nhân cách hỗ trợ, không giả người | Nhân cách Alexa nhất quán | Bắt buộc công khai hệ thống AI | Hỗ trợ developer gắn metadata | Gia sư đồng hành định hướng | **Bắt buộc minh bạch AI ngay lời chào; cấm giả cảm xúc** |
| **7. Độ Tin Cậy Thấp (<0.75)** | Đưa ra gợi ý tìm kiếm | Hỏi lại xác nhận nhẹ (implicit) | Giới hạn câu hỏi Có/Không | Return tool call clarify | Emit low confidence event | Đưa nấc gợi ý thay vì nói sai | **Calibrated Uncertainty: Hỏi lại xác nhận, cấm đoán mò** |

---

## 2. Phân Tích Sự Khác Biệt & Lý Do Lựa Chọn Của DESIGN:OS

### 2.1. Tại sao chọn Sub-100ms Barge-in kết hợp Truncate của OpenAI/LiveKit thay vì dừng phát thụ động kiểu Alexa cũ?
- Trong hệ thống Alexa thế hệ trước, việc ngắt lời dựa vào cloud roundtrip khiến độ trễ lên tới 300–500ms, tạo cảm giác máy bị "vọng tiếng" hoặc phản xạ chậm.
- DESIGN:OS chọn kiến trúc **Client-side Local Mute kết hợp Server Truncate**: Trình duyệt/App ngắt loa ngay lập tức trong 50ms qua AudioWorklet, đồng thời gửi tín hiệu WebRTC ngắt server, đảm bảo triệt tiêu va chạm âm thanh tuyệt đối.

### 2.2. Tại sao áp dụng Thang gợi ý 4 bậc của Brilliant/ITS thay vì chỉ Reprompt 3 lần kiểu Amazon?
- Reprompt của Amazon chủ yếu phục vụ các tác vụ thương mại ngắn (mua hàng, mở nhạc).
- Trong môi trường giáo dục tương tác, người học cần được rèn luyện tư duy phản biện. Nấc thang 4 bậc (Nudge → Principle → Next Step → Solution) bảo vệ "Aha! moment", giúp người học tự tìm ra câu trả lời thay vì chỉ thụ động nghe máy đọc đáp án.
