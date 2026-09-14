# 01-LEARNING-PRINCIPLES: Sư Phạm Tương Tác Trong Voice UX

> Nền tảng nhận thức và các nguyên lý tâm lý học giáo dục ứng dụng cho việc thiết kế bài học tương tác trong DESIGN:OS Voice UX Academy.

---

## 1. Cơ Sở Khoa Học Nhận Thức (Cognitive Foundation)

Khác với giao diện đồ họa (GUI) dựa trên không gian tĩnh, giao diện giọng nói (VUI) dựa trên thời gian và có tính biến mất tức thời (evanescent). Do đó, sư phạm Voice UX bắt buộc phải tích hợp hai lý thuyết khoa học nhận thức hàng đầu:

### 1.1. Lý Thuyết Học Đa Phương Tiện của Richard Mayer (Mayer's Cognitive Theory of Multimedia Learning)
- **[FACT] Modality Principle:** Con người tiếp thu kiến thức tốt hơn khi hình ảnh đồ họa đi kèm với lời giải thích bằng âm thanh hơn là hình ảnh đi kèm với các khối văn bản dài trên màn hình.
- **[FACT] Signaling Principle:** Việc làm nổi bật trực quan (highlight, animated pulse) chính xác vị trí tín hiệu âm thanh đang vang lên giúp giảm 30% tải nhận thức ngoại lai (extraneous cognitive load).
- **[FACT] Spatial & Temporal Contiguity Principle:** Thông tin giải thích phải xuất hiện đồng thời và đặt sát cạnh thành phần đồ họa (ví dụ: nhãn latency gắn trực tiếp lên dải sóng âm, không đặt trong bảng chú giải riêng biệt).

### 1.2. Active Learning vs. Thuyết Giảng Thụ Động (Freeman et al., PNAS)
- **[FACT]:** Phân tích tổng hợp 225 nghiên cứu chứng minh phương pháp học chủ động (Active Learning) giảm 33% tỷ lệ thất bại và tăng kết quả kiểm tra lên gần 0.5 độ lệch chuẩn so với việc nghe giảng thụ động.
- **[RULE]:** Không bao giờ để trợ lý giọng nói độc thoại quá 60 giây mà không có thao tác tương tác từ người học.

---

## 2. Chu Trình Học Tương Tác 6 Giai Đoạn (The 6-Stage Pedagogy Loop)

Mọi bài học trong Voice UX Academy bắt buộc phải tuân theo chu trình chuẩn hóa:

```
┌──────────────┐      ┌──────────────┐      ┌──────────────┐
│  1. EXPLAIN  │ ───> │ 2. DEMO      │ ───> │ 3. PRACTICE  │
│  Định nghĩa  │      │ Minh họa     │      │ Thử thách    │
│  < 30 từ     │      │ Graphic UI   │      │ Micro-task   │
└──────────────┘      └──────────────┘      └──────────────┘
                                                    │
┌──────────────┐      ┌──────────────┐              ▼
│ 6. TRANSFER  │ <─── │  5. RETRY    │ <─── ┌──────────────┐
│ Áp dụng bối  │      │ Sửa lỗi có   │      │ 4. FEEDBACK  │
│ cảnh mới     │      │ mục tiêu     │      │ Phản hồi     │
└──────────────┘      └──────────────┘      │ tức thì      │
                                            └──────────────┘
```

1. **Explain (Giải thích ngắn gọn):** Nêu bật một nghịch lý hoặc mô hình cốt lõi dưới 30 từ.
2. **Demonstrate (Làm mẫu):** Hiển thị Graphic UI trực quan (Waveform, Timeline, Waterfall) kèm âm thanh thực tế.
3. **Practice (Thực hành vi mô):** Yêu cầu học viên tương tác ngay (kéo slider, bấm điểm lỗi, cướp lời bot).
4. **Feedback (Phản hồi tức thì):** Phát Earcon đúng/sai và giải thích nguyên nhân vật lý/tâm lý tại sao đúng hoặc sai.
5. **Retry (Làm lại có mục tiêu):** Nếu sai, cung cấp nấc gợi ý tiếp theo và cho phép thử lại ngay lập tức.
6. **Transfer (Chuyển giao năng lực):** Cho học viên áp dụng nguyên lý vừa học vào một kịch bản production phức tạp hơn.

---

## 3. Nguyên Tắc "Trực Giác Trước Thuật Ngữ" (Intuition-Before-Jargon)

Dựa trên lý thuyết phát triển nhận thức của Jerome Bruner (Enactive → Iconic → Symbolic):

- **[RULE]:** Tuyệt đối không đưa ra các thuật ngữ trừu tượng (ví dụ: *Endpointing, VAD, Sub-100ms Barge-in, Acoustic Masking*) ở đầu slide.
- **Quy trình triển khai bắt buộc:**
  1. *Bước 1 (Enactive):* Cho học viên bấm nghe hoặc thử cướp lời để cảm nhận sự va chạm âm thanh gây khó chịu.
  2. *Bước 2 (Iconic):* Thể hiện hiện tượng đó bằng dải sóng âm màu đỏ hoặc khoảng lặng đơ máy trên màn hình.
  3. *Bước 3 (Symbolic):* Đặt tên cho hiện tượng đó bằng thuật ngữ chuyên ngành và công bố quy tắc chuẩn.
