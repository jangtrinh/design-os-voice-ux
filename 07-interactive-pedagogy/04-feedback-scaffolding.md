# 04-FEEDBACK-SCAFFOLDING: Giàn Giáo Hỗ Trợ và Thang Đo Gợi Ý

> Nguyên lý sư phạm về nấc thang gợi ý tiến tiến (Hint Ladder), quy tắc nhắc lại leo thang (Progressive Reprompting) và kiểm định hình thành (Formative Assessment).

---

## 1. Thang Đo Gợi Ý 4 Bậc Tiến Tiến (The 4-Tier Progressive Hint Ladder)

- **[FACT]:** Cung cấp ngay lời giải khi học viên gặp khó khăn sẽ triệt tiêu hiệu ứng tự nhận thức ("Aha! moment") và làm suy giảm khả năng tư duy độc lập (Intelligent Tutoring Systems Research, Koedinger & Corbett, 2006).
- **[RULE] 4 Nấc Thang Bắt Buộc:**
  1. **Nấc 1 (The Nudge - Khều nhẹ):** Đưa ra một câu hỏi định hướng mở hoặc góc nhìn mới, không nhắc đến dữ kiện cụ thể.
  2. **Nấc 2 (The Principle - Nhắc nguyên tắc):** Nhắc lại định luật hoặc nguyên lý cốt lõi liên quan (ví dụ: *"Nhớ lại định luật Cowan về giới hạn bộ nhớ thính giác"*).
  3. **Nấc 3 (The Next Step - Hướng dẫn bước đi):** Chỉ rõ hành động tiếp theo cần thực hiện (ví dụ: *"Hãy kéo thanh trượt xuống dưới mốc 600ms"*).
  4. **Nấc 4 (Bottom-out Solution - Lời giải cặn kẽ):** Trình bày đáp án chính xác kèm phân tích sâu nguyên nhân tại sao giải pháp này tối ưu.

---

## 2. Amazon Alexa 3-Tier Progressive Reprompting

Khi người dùng im lặng hoặc cung cấp câu trả lời không hợp lệ, hệ thống phải leo thang mức độ hỗ trợ qua 3 lượt thoại:

```
[LƯỢT 1: NHẮC NGẮN GỌN] ──> "Bạn muốn nghe nhạc pop hay rock?"
        │
        ▼ (Nếu tiếp tục im lặng/sai)
[LƯỢT 2: ĐƯA VÍ DỤ MẪU]  ──> "Bạn có thể nói: 'Mở nhạc Pop' hoặc 'Mở bài hát của Sơn Tùng'."
        │
        ▼ (Nếu tiếp tục thất bại)
[LƯỢT 3: GIỚI HẠN LỰA CHỌN HOẶC THOÁT HIỂM] ──> "Mình có thể mở top bài hát thịnh hành ngay bây giờ được không?"
```

- **[RULE]:** Không bao giờ lặp lại y nguyên câu hỏi cũ ở lần reprompt tiếp theo.

---

## 3. Kiểm Định Hình Thành Đa Thức (Formative Multi-Modal Testing - Chuẩn Uxcel)

- **[FACT]:** Kiểm tra đánh giá quá trình (Formative Assessment) kết hợp phản hồi trực quan tức thì mang lại hiệu quả tiếp thu kiến thức cao gấp 2 lần so với bài kiểm tra trắc nghiệm văn bản tổng kết cuối khóa (Black & Wiliam, 1998).
- **[RULE]:** Mọi bài kiểm tra trong Voice UX Academy phải gắn liền với thao tác trực quan:
  - **Locate / Spot the Error:** Chạm vào điểm va chạm âm hoặc vùng dead air trên timeline.
  - **Tune the Slider:** Kéo thanh trượt căn chỉnh thông số VAD / Latency / Rate.
  - **Drag & Drop:** Sắp xếp các node luồng xử lý hoặc phân loại rủi ro xác nhận.
