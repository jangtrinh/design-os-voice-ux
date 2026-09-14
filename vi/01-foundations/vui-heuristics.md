# 10 Nguyên Lý Usability Của Nielsen Norman Group Ứng Dụng Cho VUI (VUI Heuristics)

> 10 Nguyên lý khả dụng kinh điển của Jakob Nielsen ban đầu được xây dựng cho giao diện đồ họa. Khi chuyển sang môi trường giọng nói (VUI), chúng phải được diễn giải lại dưới lăng kính âm thanh và tương tác phi thị giác.

![10 Nguyên lý khả dụng kinh điển ứng dụng cho Voice AI](../../assets/images/vui-heuristics-luminous.jpg)

---

## 1. Khả Năng Nhận Biết Trạng Thái Hệ Thống (Visibility of System Status -> Acoustic Status Awareness)

![Bảng chỉ báo 4 trạng thái âm thanh VUI](../../assets/images/acoustic-status-indicator.jpg)

* **Nguyên lý gốc**: Hệ thống phải luôn thông báo cho người dùng biết chuyện gì đang diễn ra thông qua phản hồi kịp thời.
* **Áp dụng cho VUI**: Vì không có thanh tiến trình (progress bar), hệ thống phải phát tín hiệu âm thanh hoặc lời nói cho 4 trạng thái:
  1. **Lắng nghe (Listening)**: Đèn LED sáng hoặc âm bíp thức dậy.
  2. **Đang xử lý (Thinking)**: Tiếng rung đệm nhẹ (ambient pulse) hoặc câu lấp chỗ trống (*"Đợi mình một giây nhé..."*).
  3. **Phản hồi (Speaking)**: Sóng âm hiển thị hoặc giọng nói phát ra.
  4. **Kết thúc lượt (Turn Complete)**: Ngữ điệu đi xuống ở cuối câu, báo hiệu quyền nói đã chuyển về cho người dùng.

---

## 2. Tương Thích Giữa Hệ Thống Và Thế Giới Thực (Match Between System and the Real World)

* **Nguyên lý gốc**: Nói bằng ngôn ngữ của người dùng, dùng từ ngữ, khái niệm quen thuộc ngoài đời.
* **Áp dụng cho VUI**:
  - Không bắt người dùng học thuộc cú pháp câu lệnh (như *"Đặt lịch họp [Tên] [Ngày] [Giờ]"*).
  - Cho phép người dùng diễn đạt tự do bằng ngôn từ bản địa, tiếp nhận các từ lóng, đại từ thay thế (*"nó"*, *"ngày mai"*, *"hôm đó"*).
  - Sử dụng ngữ điệu tự nhiên (Prosody), nhấn nhá đúng trọng âm thay vì giọng đọc vô hồn như máy đọc mã bưu chính.

---

## 3. Quyền Kiểm Soát & Tự Do Của Người Dùng (User Control and Freedom)

![Lối thoát khẩn cấp và quyền kiểm soát ngắt lời trong Voice AI](../../assets/images/emergency-exit-switch.jpg)

* **Nguyên lý gốc**: Người dùng thường thực hiện sai sót do nhầm lẫn và cần một lối thoát khẩn cấp rõ ràng ("Emergency Exit").
* **Áp dụng cho VUI**:
  - **Khả năng ngắt lời tức thì (Universal Barge-In)**: Người dùng có thể cất tiếng ngắt ngang trợ lý ảo bất kỳ lúc nào mà không cần đợi nó đọc hết câu.
  - **Từ khóa thoát khẩn cấp toàn cục**: Hệ thống luôn nhận diện các câu lệnh: *"Dừng lại"*, *"Quay lại"*, *"Bỏ qua"*, *"Hủy thao tác"* ở mọi bước của quy trình.

---

## 4. Tính Nhất Quán & Tiêu Chuẩn (Consistency and Standards)

* **Nguyên lý gốc**: Người dùng không cần băn khoăn liệu những từ ngữ hay hành động khác nhau có mang cùng ý nghĩa hay không.
* **Áp dụng cho VUI**:
  - Giữ nhất quán về **Nhân vật giọng nói (Persona)**: Giọng điệu, cách xưng hô (ví dụ: *"tôi - bạn"* hoặc *"mình - bạn"*) phải đồng nhất từ đầu đến cuối phiên.
  - Nhất quán về **Âm hiệu (Earcons)**: Một âm bíp xác nhận thành công phải mang cùng tần số và cấu trúc âm sắc trong toàn bộ hệ sinh thái sản phẩm.

---

## 5. Phòng Ngừa Sai Sót (Error Prevention)

* **Nguyên lý gốc**: Thiết kế tốt nhất là ngăn chặn lỗi không xảy ra ngay từ đầu thay vì viết thông báo lỗi hay.
* **Áp dụng cho VUI**:
  - **Xác nhận ngầm (Implicit Confirmation)**: Lồng ghép dữ liệu đã hiểu vào câu hỏi tiếp theo để người dùng tự nhận ra nếu có sai lệch mà không làm gián đoạn luồng.
    - *Ví dụ*: *"Mình đã đặt xe đến 123 Lê Lợi. Bạn muốn chọn thanh toán tiền mặt hay ví điện tử?"* (Xác nhận ngầm địa chỉ).
  - **Xác nhận rõ ràng (Explicit Confirmation)** đối với các hành động rủi ro cao (chuyển tiền, xóa dữ liệu, gửi email nhạy cảm).

---

## 6. Nhận Diện Thay Vì Nhớ Lại (Recognition Rather Than Recall)

* **Nguyên lý gốc**: Giảm thiểu tải ghi nhớ của người dùng bằng cách làm cho các tùy chọn hiển thị rõ ràng.
* **Áp dụng cho VUI**:
  - Vì giọng nói không có khả năng hiển thị tĩnh, hệ thống **không bao giờ bắt người dùng nhớ quá 3 tùy chọn**.
  - Luôn nhắc lại ngữ cảnh ngắn gọn khi tiếp tục một cuộc hội thoại bị gián đoạn: *"Trước đó bạn đang tìm chuyến bay đi Đà Nẵng ngày thứ Bảy, bạn có muốn tiếp tục không?"*

---

## 7. Linh Hoạt & Tối Ưu Hóa Hiệu Suất (Flexibility and Efficiency of Use)

* **Nguyên lý gốc**: Cung cấp lối tắt (accelerators) cho người dùng thành thạo.
* **Áp dụng cho VUI**:
  - **Xử lý đa ý định cùng lúc (Multi-slot One-shot Command)**:
    - *Người mới*: Đi qua từng câu hỏi từng bước.
    - *Người thành thạo*: Nói gộp 1 câu: *"Đặt cho tôi 2 ly cà phê sữa ít đường giao đến công ty trước 9h"* -> Hệ thống tự bóc tách toàn bộ thông tin mà không cần hỏi lại từng bước.

---

## 8. Thiết Kế Thẩm Mỹ & Tối Giản (Aesthetic and Minimalist Design)

* **Nguyên lý gốc**: Không chứa thông tin không cần thiết hoặc hiếm khi dùng đến.
* **Áp dụng cho VUI**:
  - **Tiết kiệm lời thoại (Verbal Economy)**: Loại bỏ các câu xã giao thừa thãi lặp đi lặp lại như: *"Dạ vâng, thưa quý khách thân mến, tôi rất vui lòng được thông báo rằng..."*.
  - Đi thẳng vào giá trị thông tin cốt lõi. Trong VUI, sự rườm rà chính là rác thính giác.

---

## 9. Giúp Người Dùng Nhận Biết, Chẩn Đoán & Khắc Phục Lỗi (Help Users Recognize, Diagnose, and Recover from Errors)

* **Nguyên lý gốc**: Thông báo lỗi phải diễn đạt bằng ngôn ngữ dễ hiểu, chỉ rõ vấn đề và gợi ý cách xử lý mang tính xây dựng.
* **Áp dụng cho VUI**:
  - Không bao giờ dùng thông báo chung chung vô dụng: *"Đã xảy ra lỗi, vui lòng thử lại sau"*.
  - Phân tích rõ cái gì hiểu được, cái gì chưa hiểu: *"Mình nghe được bạn muốn đặt vé đi Nha Trang, nhưng chưa rõ ngày bạn muốn khởi hành là ngày nào?"*

---

## 10. Trợ Giúp & Tài Liệu (Help and Documentation)

* **Nguyên lý gốc**: Dù hệ thống trực quan, đôi khi người dùng vẫn cần tài liệu hướng dẫn.
* **Áp dụng cho VUI**:
  - Khi người dùng nói: *"Tôi có thể làm gì ở đây?"* hoặc *"Giúp tôi với"*, trợ lý ảo không đọc một bản hướng dẫn dài 5 phút mà cung cấp **2-3 ví dụ hành động phù hợp nhất với ngữ cảnh hiện tại**.
  - Cung cấp tùy chọn chuyển tiếp sang tư vấn viên con người hoặc gửi đường link tài liệu chi tiết về điện thoại.
