# Bảng Kiểm Định Thiết Kế VUI Chuẩn Bị Ra Mắt (Voice UX Production Launch Checklist)

> Bộ checklist 25 tiêu chuẩn vàng giúp UX Designer, Product Manager và Tech Lead rà soát toàn diện trải nghiệm giọng nói trước khi phát hành tính năng ra người dùng thực tế.

---

## 🎯 1. Ngôn Ngữ & Soạn Thảo Cho Đôi Tai (Writing for the Ear)

- [ ] **1.1 Độ dài câu tối ưu**: Mọi câu thoại phản hồi đều dưới 30 từ hoặc đọc không quá 6-8 giây.
- [ ] **1.2 Quy tắc 3 lựa chọn**: Không có bất kỳ danh sách âm thanh nào cung cấp quá 3 phương án lựa chọn trong một lượt nói.
- [ ] **1.3 Tránh định dạng màn hình**: Không còn dấu gạch đầu dòng, bảng biểu, in đậm hoặc đường link URL thô trong câu đọc của TTS.
- [ ] **1.4 Chuẩn hóa phát âm**: Các con số, ngày tháng, tiền tệ, số điện thoại và từ viết tắt đã được chuyển đổi thành văn bản phát âm chuẩn.
- [ ] **1.5 Câu kết nhường lời**: Kết thúc mỗi lượt nói bằng một câu hỏi định hướng hành động rõ ràng thay vì câu cụt.

---

## 👂 2. Dấu Hiệu Âm Thanh & Earcons (Sonic Feedback)

- [ ] **2.1 Âm báo mở micro (Wake Cue)**: Có âm bíp ngắn (<150ms) hoặc tín hiệu thị giác rõ ràng ngay khi máy bắt đầu ghi âm.
- [ ] **2.2 Âm báo xử lý (Thinking State)**: Có câu lấp chỗ trống hoặc âm đệm nhịp nhẹ nhàng nếu quá trình xử lý vượt quá 600ms.
- [ ] **2.3 Âm báo hoàn tất (Success Chime)**: Có âm thanh xác nhận ngắn gọn khi tác vụ thành công thay vì phải đọc một câu dài dòng.
- [ ] **2.4 Không gây mỏi tai (No Auditory Fatigue)**: Các âm thanh lặp lại thường xuyên được điều chỉnh âm lượng êm dịu, không chứa dải tần chói gắt.
- [ ] **2.5 Phản hồi xúc giác (Haptic Pairing)**: Trên thiết bị cầm tay, các âm hiệu quan trọng đều đi kèm độ rung nhẹ tương ứng.

---

## 🔄 3. Cơ Chế Luân Phiên & Ngắt Lời (Turn-Taking & Barge-In)

- [ ] **3.1 Ngắt lời tức thì (Sub-100ms Barge-in)**: Loa lập tức ngừng phát khi người dùng cất tiếng ngắt ngang.
- [ ] **3.2 Khử tiếng vọng phần cứng/phần mềm (AEC Verified)**: Loa phát âm lượng tối đa mà micro không bị kích hoạt nhầm bởi chính giọng của máy.
- [ ] **3.3 Không nhạy cảm thái quá (Robust VAD)**: Tiếng thở, tiếng hắng giọng hoặc từ đệm (*"ừm", "ờ"*) không làm đứt gãy câu nói của trợ lý.
- [ ] **3.4 Khôi phục trạng thái (State Rollback)**: Ngữ cảnh của phần câu nói bị ngắt giữa chừng được xử lý gọn gàng, không gây mâu thuẫn thông tin ở lượt sau.
- [ ] **3.5 Lối thoát khẩn cấp**: Các từ khóa *"Dừng lại", "Hủy", "Quay lại"* hoạt động tức thì ở mọi màn hình và trạng thái.

---

## 🛠️ 4. Xử Lý Lỗi & Phục Hồi Hội Thoại (Error Recovery & Repair)

- [ ] **4.1 Không đổ lỗi cho người dùng**: Thông báo lỗi không chứa các từ ngữ trách móc (*"Bạn nói sai", "Lệnh không hợp lệ"*).
- [ ] **4.2 Gợi ý lũy tiến 3 bước (3-Tier Prompting)**: Khi người dùng im lặng, hệ thống nhắc lại lần 1 nhẹ nhàng -> lần 2 kèm ví dụ -> lần 3 đưa lối thoát/chuyển kênh.
- [ ] **4.3 Xác nhận ngầm linh hoạt**: Áp dụng xác nhận ngầm cho các thao tác an toàn và xác nhận tường minh cho các giao dịch rủi ro cao.
- [ ] **4.4 Thu hẹp nhánh khi mơ hồ**: Khi có 2 kết quả trùng tên, hệ thống chủ động hỏi chọn lọc thay vì báo lỗi.
- [ ] **4.5 Kênh dự phòng an toàn (Fallback Channel)**: Luôn có phương án chuyển sang màn hình chạm, gửi tin nhắn SMS, hoặc gặp tổng đài viên nếu sau 3 lần không hiểu nhau.

---

## 🛡️ 5. Quyền Riêng Tư & An Toàn (Privacy, Ethics & Performance)

- [ ] **5.1 Chỉ báo ghi âm trực quan**: Người dùng luôn biết rõ micro đang mở thông qua đèn LED vật lý hoặc biểu tượng nổi bật trên màn hình.
- [ ] **5.2 Minh bạch danh tính**: Trợ lý không bao giờ tự nhận mình là con người thật khi được hỏi.
- [ ] **5.3 Giấu thông tin nhạy cảm**: Không đọc to mã OTP, mật khẩu hoặc số dư tài khoản nếu phát hiện đang ở môi trường công cộng.
- [ ] **5.4 Ngân sách độ trễ kiểm soát**: Thời gian phản hồi trung bình duy trì dưới 400ms trong điều kiện mạng tiêu chuẩn.
- [ ] **5.5 Tuân thủ nguyên tắc cấm dùng giọng nói**: Đã kiểm tra và đảm bảo không cố tình ép người dùng đọc bảng biểu hoặc dữ liệu phức tạp qua âm thanh.
