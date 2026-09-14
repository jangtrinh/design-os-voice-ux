# SOURCE: LiveKit Agents & Real-Time Voice Infrastructure

> Tài liệu trích xuất chuẩn mực Voice Pipeline, Adaptive Interruption, Silero VAD và WebRTC Audio từ LiveKit.

- **URL:** [https://docs.livekit.io/agents/overview/](https://docs.livekit.io/agents/overview/)
- **Tổ chức:** LiveKit Inc.
- **Ngày tham chiếu:** 2026-09-14

---

## Các Chuẩn Mực Cốt Lõi Được Trích Xuất

### 1. Phân Tầng Turn Detection & Adaptive Interruption
- **URL:** [https://blog.livekit.io/adaptive-interruption-handling/](https://blog.livekit.io/adaptive-interruption-handling/)
- Không sử dụng ngưỡng silence tĩnh cứng nhắc.
- Tích hợp Silero VAD (32ms frames) kết hợp bộ phân loại đặc trưng âm học (Pitch, Energy, Rhythm) để phân biệt tiếng ho/tiếng thở/backchannel với câu ngắt lời thực sự.

### 2. Ngân Sách Độ Trễ & Client-Side Audio Cancellation
- Đạt mục tiêu triệt tiêu âm thanh client trong <80–100ms khi người dùng nói cướp lời.
- Kiến trúc WebRTC Full-Duplex truyền âm thanh Opus frame với độ trễ mạng tối thiểu.
