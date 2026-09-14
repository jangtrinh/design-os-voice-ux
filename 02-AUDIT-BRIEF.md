# 02-AUDIT-BRIEF: Voice UX Audit Context & Directives

> Executive one-page brief defining target operational scope, reference architectural stacks, and high-risk failure modes evaluated during the DESIGN:OS Voice UX audit.

---

## 1. Product Scope & Operational Context

- **System Mission**: Establish rigorous engineering and design standards for **next-generation Voice AI Agents (Full-Duplex Speech-to-Speech & Multimodal)** operating across:
  1. Multimodal Smart Assistants (Smartphone, Tablet, Smart Displays).
  2. In-Cabin Automotive Voice Interfaces (Hands-free, Eyes-free environments).
  3. Real-Time Customer Voice Support & Contact Center Automation.
- **Explicit Exclusions**: Legacy touch-tone interactive voice response (DTMF IVR tree navigation) and offline, single-keyword acoustic triggers (Offline Hotword Engines).

---

## 2. Reference Voice Stack Architecture

The knowledge base is built to govern two predominant conversational architectures:

```
Pattern 1 — Native Audio-to-Audio (Recommended):
Mic/WebRTC ──► WebAssembly VAD ──► Speech-to-Speech Model (Gemini Live / OpenAI Realtime) ──► Low-Latency Audio Stream

Pattern 2 — Optimized Cascaded Pipeline:
Mic ──► Silero VAD (<10ms) ──► Streaming ASR (Deepgram Nova-2) ──► Low-Latency LLM ──► Streaming TTS (Cartesia/ElevenLabs)
```

- **Transport Layer**: Bidirectional WebRTC UDP (Full-Duplex) with Acoustic Echo Cancellation (AEC).
- **Target Conversational Budget**: `< 400ms` total turn-gap from speech endpointing to speaker playback acoustic onset.

---

## 3. Critical Failure Modes Evaluated

The audit targets 5 catastrophic pitfalls frequently omitted from theoretical UX literature:

1. **Barge-In Collision & State Bleed**:
   - When a user interrupts at second 2 of a 5-second synthesized sentence, does conversation memory retain the unvoiced 3 seconds, polluting future context (`Audible Boundary Truncation`)?
2. **Dead-Air Latency Cliff**:
   - When external tool execution, API calls, or RAG lookups consume 1.5s–2.5s, how are acoustic fillers, earcons, and bridging prosody deployed to prevent the impression of a dropped call?
3. **Infinite Repair Loop (The "Deaf Agent" Trap)**:
   - When ASR misrecognition occurs, does the agent trap the user in repetitive cycles of *"Sorry, could you repeat that?"*, provoking caller abandonment?
4. **Uncanny Empathy & Affective Overreach**:
   - Does the agent perform artificial emotional intimacy (feigned weeping, unearned excitement) or offer speculative medical/financial advice without verified grounding?
5. **Auditory Overreach (Forced Listening)**:
   - Does the agent force users to ingest dense lists, coordinates, or financial transactions aurally instead of triggering proactive Visual Offloading to paired screens?

---

## 4. Production Readiness Gate Criteria

A voice feature is certified as **Tier 1 Production Ready** only when satisfying:
- **Acoustic Barge-In Latency**: `< 100ms` (`p50 < 80ms`) from vocal onset to DAC speaker silence.
- **Task Completion Rate (TCR)**: `> 85%` across Wizard of Oz usability benchmarks.
- **Contextual Memory Integrity**: 100% of interrupted turns pruned precisely at the audible boundary.
- **Global Emergency Escape**: Zero-latency recognition of universal bail-out keywords (*"Stop"*, *"Cancel"*, *"Human"*) across 100% of system states.
