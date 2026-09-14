# SOURCE: Google Conversation Design Guidelines (Assistant & CxD)

> Tài liệu trích xuất chuẩn mực thiết kế đàm thoại, xử lý lỗi và nguyên lý hợp tác từ Google Conversation Design.

- **URL:** [https://developers.google.com/assistant/conversation-design/overview](https://developers.google.com/assistant/conversation-design/overview)
- **Tổ chức:** Google LLC
- **Ngày tham chiếu:** 2026-09-14

---

## Các Chuẩn Mực Cốt Lõi Được Trích Xuất

### 1. Nguyên Lý Hợp Tác Của Grice (Cooperative Principle)
- Áp dụng triệt để 4 phương châm Gricean Maxims: Lượng (Quantity), Chất (Quality), Quan hệ (Relation), Cách thức (Manner).
- Viết cho tai nghe (Writing for the Ear): câu ngắn, từ vựng thông dụng, nhịp điệu tự nhiên.

### 2. Sửa Lỗi Hội Thoại Không Đổ Lỗi (Conversational Repair)
- **URL:** [https://developers.google.com/assistant/conversation-design/repair](https://developers.google.com/assistant/conversation-design/repair)
- Nghiêm cấm đổ lỗi cho người dùng hoặc thông báo lỗi kỹ thuật.
- Sử dụng kỹ thuật Rapid Reprompt hoặc tái cấu trúc câu hỏi có tính định hướng để giúp người dùng tự sửa sai một cách êm thấm.

### 3. Cơ Chế Xác Nhận (Confirmations: Explicit vs. Implicit)
- **URL:** [https://developers.google.com/assistant/conversation-design/confirmations](https://developers.google.com/assistant/conversation-design/confirmations)
- Chỉ dùng Explicit Confirmation cho các hành động có hậu quả lớn, không thể hoàn tác.
- Tác vụ thông thường dùng Implicit Confirmation để duy trì tốc độ hội thoại mượt mà.
