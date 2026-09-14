# CONTEXT.md — Voice UX Domain Glossary

> Canonical terminology standard for Voice User Interfaces (VUI) and Conversational AI Design. Use standardized **Canonical Terms** across all system documentation and avoid ambiguous phrasing (**_Avoid_**).

---

### **Acoustic Signifier**
An auditory cue (short tone, subtle chime, earcon, volume shift) that signals to users whether the system is listening, thinking, speaking, or terminating a session without requiring visual attention.  
_Avoid_: audio button, voice icon, system beep.

---

### **Barge-In**
The system's real-time capability to detect user speech while the voice assistant is speaking, instantly cease playback (< 80ms onset), truncate audio buffers, and transition seamlessly to listening mode.  
_Avoid_: interrupt button, audio cutoff, talking over.

---

### **Conversational Repair**
The communicative negotiation process between user and system when misunderstanding or speech recognition failure occurs, gracefully steering the interaction back on track without conversational breakdown.  
_Avoid_: error handling, exception throwing, crash retry.

---

### **Earcon**
A brief, structured sound or musical motif coded to represent a specific event, system state, transition, or notification in an audio interface.  
_Avoid_: sound effect, SFX, alert noise.

---

### **Full-Duplex**
Simultaneous bidirectional audio streaming that allows human and machine to speak and listen concurrently, mirroring organic human-to-human conversation.  
_Avoid_: walkie-talkie mode, half-duplex, push-to-talk.

---

### **Gricean Maxims**
Four foundational conversational maxims (Quantity, Quality, Relation, Manner) formulated by philosopher Paul Grice to maintain cooperative, efficient communication.  
_Avoid_: communication rules, chat guidelines.

---

### **Gulf of Execution (in VUI)**
The cognitive gap between a user's intent and their uncertainty about what vocal prompt or phrasing the invisible interface accepts (due to the lack of visible affordances in pure audio).  
_Avoid_: UI confusion, blank screen error.

---

### **Latency Cliff**
Critical perceptual timing thresholds (0–300ms, 300–500ms, >800ms) that determine whether conversational cadence feels fluid, hesitant, or painfully broken.  
_Avoid_: loading delay, lag time.

---

### **Progressive Re-prompting**
An escalating error recovery strategy that systematically increases contextual detail after repeated silence or misrecognition (Level 1: Gentle re-prompt → Level 2: Exemplar phrasing → Level 3: Bounded choice or channel handoff).  
_Avoid_: infinite retry loop, generic error repetition.

---

### **Prosody**
Non-verbal acoustic elements of human speech including pitch, tempo, volume, intonation, and rhythm that convey intent, emotional tone, and pragmatic meaning beyond literal vocabulary.  
_Avoid_: voice modulation, robot pitch.

---

### **Semantic End-of-Turn**
Real-time grammatical, contextual, and prosodic inference that accurately predicts whether a speaker has completed their turn or is merely pausing mid-thought, far surpassing static silence-timeout VAD.  
_Avoid_: silence detector, audio timeout.

---

### **Speech-to-Speech (Native Audio Model)**
An end-to-end multimodal model that accepts audio waveforms directly and synthesizes streaming speech outputs without converting to intermediate text tokens (bypassing the cascaded STT → LLM → TTS pipeline).  
_Avoid_: cascaded voice, multi-step pipeline.

---

### **Turn-Taking**
The psycho-social and linguistic framework that coordinates when one speaker ceases and another begins in natural dialogue without collision or awkward dead air.  
_Avoid_: ping-pong chat, sequential messaging.

---

### **Visual Offloading**
The selective transfer of complex, high-density data (e.g., lists with > 3 items, tabular data, maps, confirmations) from the auditory channel to a companion visual display to safeguard working memory.  
_Avoid_: screen dumping, multi-channel spam.

---

### **Voice Activity Detection (VAD)**
An algorithmic or neural filter that distinguishes human speech from background acoustic noise to determine the precise onset and offset of vocal input.  
_Avoid_: microphone listener, noise gate.
