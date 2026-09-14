# CONTEXT.md — Voice UX Domain Glossary

> Bảng chuẩn hóa thuật ngữ chuyên ngành Thiết Kế Giao Diện Giọng Nói (VUI / Conversational Design). Sử dụng các thuật ngữ được chuẩn hóa (`Canonical Terms`) trong toàn bộ tài liệu thiết kế và tránh dùng các từ tối nghĩa (`_Avoid_`).

---

### **Acoustic Signifier**
Một dấu hiệu âm thanh (tiếng bíp ngắn, thay đổi âm lượng, giai điệu nhỏ) giúp người dùng nhận biết hệ thống đang lắng nghe, đang xử lý hoặc đã kết thúc phiên.
_Avoid_: audio button, voice icon, system beep.

---

### **Barge-In**
Khả năng của hệ thống cho phép người dùng cất giọng ngắt lời ngay khi trợ lý ảo đang nói, ngay lập tức dừng phát âm thanh và chuyển sang chế độ lắng nghe.
_Avoid_: interrupt button, audio cutoff, talking over.

---

### **Conversational Repair**
Quá trình thương lượng ý nghĩa giữa người dùng và hệ thống khi xảy ra hiểu lầm hoặc lỗi nhận dạng giọng nói, giúp cuộc trò chuyện quay lại đúng hướng mà không làm đứt gãy tương tác.
_Avoid_: error handling, exception throwing, crash retry.

---

### **Earcon**
Âm thanh ngắn gọn, có cấu trúc âm nhạc hoặc âm sắc đặc trưng, được mã hóa để đại diện cho một sự kiện, trạng thái hoặc thông báo cụ thể trong hệ thống.
_Avoid_: sound effect, SFX, alert noise.

---

### **Full-Duplex**
Giao tiếp âm thanh hai chiều đồng thời, cho phép cả người và máy có thể vừa nghe vừa nói trong cùng một thời điểm tương tự cuộc trò chuyện tự nhiên giữa hai người.
_Avoid_: walkie-talkie mode, half-duplex, push-to-talk.

---

### **Gricean Maxims**
Bốn phương châm đàm thoại nền tảng (Lượng, Chất, Quan hệ, Cách thức) do triết gia Paul Grice đề xuất nhằm đảm bảo cuộc hội thoại diễn ra hợp tác và hiệu quả.
_Avoid_: communication rules, chat guidelines.

---

### **Gulf of Execution (Vực thẳm thực thi trong VUI)**
Khoảng cách nhận thức giữa ý định của người dùng và việc họ không biết phải phát âm câu lệnh nào để hệ thống hiểu được (do VUI không có các nút bấm hiển thị trực quan).
_Avoid_: UI confusion, blank screen error.

---

### **Latency Cliff (Vực thẳm độ trễ)**
Các mốc ranh giới thời gian phản hồi âm thanh (0-300ms, 300-500ms, >800ms) quyết định mức độ tự nhiên hay bực bội của người dùng trong một cuộc trò chuyện.
_Avoid_: loading delay, lag time.

---

### **Progressive Re-prompting**
Kỹ thuật nhắc lại câu hỏi với mức độ chi tiết tăng dần sau mỗi lần người dùng im lặng hoặc hệ thống không nghe rõ (Lần 1: Nhẹ nhàng -> Lần 2: Đưa ra ví dụ -> Lần 3: Đưa ra lựa chọn cụ thể hoặc chuyển kênh).
_Avoid_: infinite retry loop, generic error repetition.

---

### **Prosody (Âm sắc & Ngữ điệu)**
Các yếu tố phi ngôn ngữ trong giọng nói bao gồm cao độ (pitch), nhịp điệu (tempo), cường độ (volume) và sự ngắt nghỉ tạo nên cảm xúc và ý nghĩa bổ sung cho từ ngữ.
_Avoid_: voice modulation, robot pitch.

---

### **Semantic End-of-Turn (Nhận diện điểm dừng ngữ nghĩa)**
Khả năng phân tích cú pháp, ngữ điệu và mạch ý của câu nói để dự đoán người dùng đã kết thúc câu hay chỉ đang ngập ngừng suy nghĩ, vượt trội hơn phương pháp đo khoảng lặng truyền thống (Static VAD).
_Avoid_: silence detector, audio timeout.

---

### **Speech-to-Speech (Mô hình gốc âm thanh)**
Mô hình AI nhận trực tiếp luồng sóng âm thanh đầu vào và tạo ra luồng sóng âm thanh đầu ra mà không cần chuyển thể qua trung gian văn bản (bỏ qua chuỗi STT -> LLM -> TTS).
_Avoid_: cascaded voice, multi-step pipeline.

---

### **Turn-Taking (Luân phiên lượt nói)**
Quy tắc văn hóa và tâm lý tự nhiên điều phối thời điểm một bên dừng nói để bên kia bắt đầu nói trong một cuộc hội thoại mà không bị giẫm chân lên nhau.
_Avoid_: ping-pong chat, sequential messaging.

---

### **Visual Offloading (Phân tải hiển thị)**
Hành vi chuyển bớt thông tin phức tạp (như danh sách dài > 3 mục, bảng biểu, bản đồ chi tiết) từ kênh giọng nói sang màn hình để giảm tải bộ nhớ ngắn hạn của người dùng.
_Avoid_: screen dumping, multi-channel spam.

---

### **Voice Activity Detection (VAD)**
Thuật toán phát hiện sự hiện diện của giọng nói người dùng dựa trên ngưỡng biên độ âm thanh hoặc tần số nhằm xác định thời điểm bắt đầu và kết thúc thu âm.
_Avoid_: microphone listener, noise gate.
