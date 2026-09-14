# 02-CONVERSATION-DESIGN-RULES: Quy Tắc Thiết Kế Hội Thoại Chuẩn Sư Phạm

> Hệ thống các quy tắc cốt lõi về tải nhận thức, cấu trúc lượt thoại và tâm lý đàm thoại cho các bài học Voice UX.

---

## 1. Giới Hạn Bộ Nhớ Thính Giác Của Nelson Cowan (2001)

- **[FACT]:** Bộ nhớ ngắn hạn thính giác (Auditory Working Memory) của con người chỉ có dung lượng tối đa 3–4 đơn vị thông tin (chunks). Vượt quá giới hạn này, dấu vết thần kinh âm thanh (echoic memory trace) bị xóa sạch trong vòng 3–5 giây.
- **[RULE] The Rule of Three:**
  - Không bao giờ liệt kê quá **3 lựa chọn âm thanh** trong một menu thoại.
  - Khi có nhiều hơn 3 lựa chọn, bắt buộc phải nhóm thành cây phân cấp (hierarchical categories) hoặc chuyển quyền hiển thị sang màn hình (multimodal offloading).
- **[RECOMMENDATION] Dạng bài tập:**
  - *Auditory Memory Overload Lab:* Trình phát đọc ngẫu nhiên 7 món hàng. Học viên chỉ được nghe mà không nhìn văn bản, sau đó bấm chọn lại danh sách để tự nghiệm chứng sự suy giảm của trí nhớ.

---

## 2. Kiểm Tra "Một Hơi Thở" (The One Breath Test)

- **[FACT]:** Khả năng duy trì sự chú ý tập trung thính giác liên tục của người nghe tương ứng với chu kỳ một hơi thở bình thường (4–6 giây, tương đương 20–25 từ).
- **[RULE] The One Breath Constraint:**
  - Mọi câu phản hồi của trợ lý giọng nói phải đọc được hết trong một hơi thở tự nhiên mà không bị hụt hơi.
  - Độ dài chuẩn: Tối đa 25–30 từ và không quá 2 câu ngắn trong một lượt nói trước khi trả quyền kiểm soát lại cho người dùng.
- **[RECOMMENDATION] Dạng bài tập:**
  - *Voice Script Word Diet:* Cho một câu trả lời 65 từ của LLM. Học viên sử dụng công cụ gạch bỏ từ thừa để nén câu thoại về dưới 22 từ đạt chuẩn One Breath Test.

---

## 3. Nguyên Tắc 1 Ý Tưởng / Một Lượt Thoại (1 Idea per Utterance)

- **[FACT]:** Khi một câu hỏi bằng giọng nói chứa từ 2 yêu cầu trở lên (Compound Question), hơn 60% người dùng chỉ trả lời vế câu cuối cùng hoặc trả lời mơ hồ, gây đứt gãy luồng hội thoại.
- **[RULE]:** Tuyệt đối cấm đặt câu hỏi ghép trong một lượt nói. Mỗi lượt thoại chỉ truyền tải một thông điệp duy nhất và yêu cầu đúng một quyết định từ người nghe.
- **[RECOMMENDATION] Dạng bài tập:**
  - *Compound Question Splitter:* Tách các câu thoại phức hợp thành luồng hội thoại phân cấp tuần tự (Progressive Disclosure).

---

## 4. Bốn Phương Châm Hội Thoại của Paul Grice (Gricean Maxims) Ứng Dụng Trong VUI

1. **Maxim of Quantity (Lượng):** Chỉ cung cấp lượng thông tin vừa đủ, không nói thừa, không bỏ sót thông tin thiết yếu.
2. **Maxim of Quality (Chất):** Chỉ nói điều có bằng chứng xác thực, không tự bịa thông tin khi độ tin cậy thấp.
3. **Maxim of Relation (Quan hệ):** Mọi câu thoại phải bám sát trực tiếp vào ngữ cảnh và mục tiêu hiện tại của người dùng.
4. **Maxim of Manner (Cách thức):** Ngắn gọn, rõ ràng, tránh mơ hồ và tránh dùng từ ngữ kỹ thuật gây khó hiểu.
