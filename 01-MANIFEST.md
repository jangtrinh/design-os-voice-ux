# 01-MANIFEST: Voice UX Knowledge Base Inventory

> Complete inventory of all 26 core specifications and engineering artifacts in the DESIGN:OS Voice UX Knowledge Base, delineating Purpose, Target Audience, Lifecycle Status, and Empirical Evidence.

---

## 1. Core Specification Inventory (26 Specifications)

| ID | Document | Category | Core Purpose | Target Audience | Status | Empirical Evidence Basis |
|---|---|---|---|---|---|---|
| **M00** | [`README.md`](./README.md) | Navigation | Master Index, knowledge architecture & VUI Maturity Levels | All Roles | **Stable** | Standard UX Architecture |
| **M01** | [`CONTEXT.md`](./CONTEXT.md) | Governance | Canonical glossary standard (Canonical Terms vs Anti-terms) | All Roles | **Stable** | Grice, Clark & Brennan, NN/g |
| **F01** | [`01-foundations/mental-models-and-affordance.md`](./01-foundations/mental-models-and-affordance.md) | Foundations | Resolving the Gulf of Execution, invisibility & transience | Designers | **Stable** | Don Norman, Cathy Pearl |
| **F02** | [`01-foundations/conversational-psychology.md`](./01-foundations/conversational-psychology.md) | Foundations | Gricean Maxims, turn structure & Cowan's 4-chunk capacity | Designers, PMs | **Stable** | Paul Grice (1975), Cowan (2001) |
| **F03** | [`01-foundations/vui-heuristics.md`](./01-foundations/vui-heuristics.md) | Foundations | Translating Nielsen's 10 Heuristics to acoustic environments | Designers, QA | **Stable** | Nielsen Norman Group (NN/g) |
| **F04** | [`01-foundations/microphone-snr-acoustic-front-end.md`](./01-foundations/microphone-snr-acoustic-front-end.md) | Foundations | Microphone arrays, SNR, AGC, far-field physics, POLQA standards | Audio/DSP Eng | **Production** | ITU-T P.863 (POLQA), ANSI S3.5 |
| **IP01** | [`02-interaction-patterns/turn-taking-and-barge-in.md`](./02-interaction-patterns/turn-taking-and-barge-in.md) | Patterns | Sub-100ms barge-in, Semantic VAD & Audible Boundary Truncation | Designers, Eng | **Validated** | Full-duplex WebRTC research |
| **IP02** | [`02-interaction-patterns/error-recovery-and-repair.md`](./02-interaction-patterns/error-recovery-and-repair.md) | Patterns | 3-tier progressive re-prompting, non-blaming error culture | Designers | **Stable** | Google Assistant, Conversation Analysis |
| **IP03** | [`02-interaction-patterns/audio-feedback-and-earcons.md`](./02-interaction-patterns/audio-feedback-and-earcons.md) | Patterns | Earcon design, sonic branding, 4-state acoustic frequency allocation | Sound Designers | **Validated** | Acoustic UX, Apple/Google Sound Design |
| **IP04** | [`02-interaction-patterns/multimodal-handshake.md`](./02-interaction-patterns/multimodal-handshake.md) | Patterns | Voice + GUI coordination, visual offloading, hands-busy matrix | Product Designers | **Stable** | Cheryl Platz (*Design Beyond Devices*) |
| **IP05** | [`02-interaction-patterns/deep-acoustics/aec-echo-control.md`](./02-interaction-patterns/deep-acoustics/aec-echo-control.md) | Deep Acoustics | ERL/ERLE, double-talk detection, acoustic coupling & false barge-in | DSP/WebRTC Eng | **Production** | ITU-T G.168, ITU-T P.340 |
| **IP06** | [`02-interaction-patterns/deep-acoustics/opus-jitter-resilience.md`](./02-interaction-patterns/deep-acoustics/opus-jitter-resilience.md) | Deep Acoustics | Opus codec, in-band FEC, PLC, DTX/CNG, WebRTC NetEQ jitter buffer | Network Eng | **Production** | RFC 6716, RFC 7587, RFC 3550 |
| **IP07** | [`02-interaction-patterns/deep-acoustics/semantic-vad-endpointing.md`](./02-interaction-patterns/deep-acoustics/semantic-vad-endpointing.md) | Deep Acoustics | Neural Silero VAD, pitch contours (F0), syntactic turn closure | Speech Scientists | **Production** | WebRTC VAD, Silero v5 |
| **DS01** | [`03-conversational-design-system/persona-and-tone.md`](./03-conversational-design-system/persona-and-tone.md) | Design System | 4-axis persona framework, avoiding Uncanny Valley & ELIZA effect | Content, UX | **Stable** | Erika Hall, Reeves & Nass |
| **DS02** | [`03-conversational-design-system/prompt-and-dialog-engineering.md`](./03-conversational-design-system/prompt-and-dialog-engineering.md) | Design System | Writing for the ear, Voice LLM System Prompt standard, SSML | Prompt Eng, UX | **Validated** | W3C SSML 1.1, LLM System Prompts |
| **DS03** | [`03-conversational-design-system/latency-budgets.md`](./03-conversational-design-system/latency-budgets.md) | Design System | 300ms latency budgeting, acoustic fillers & Native S2S architectures | Architects, Perf | **Validated** | Psychoacoustics, LiveKit benchmarks |
| **DS04** | [`03-conversational-design-system/s2s-prosody-expression.md`](./03-conversational-design-system/s2s-prosody-expression.md) | Design System | Pitch F0, tempo, affect grounding, paralinguistic backchanneling | Prompt Eng, UX | **Production** | S2S Speech Tokenization, W3C SSML |
| **VT01** | [`03-conversational-design-system/verticals/healthcare-hipaa.md`](./03-conversational-design-system/verticals/healthcare-hipaa.md) | Industry Verticals | HIPAA ePHI, real-time PII redaction, ESI clinical triage & 911 gates | Healthcare Leads | **Production** | HIPAA 45 CFR §164, ESI v4 |
| **VT02** | [`03-conversational-design-system/verticals/banking-voice-biometrics.md`](./03-conversational-design-system/verticals/banking-voice-biometrics.md) | Industry Verticals | Voiceprints (ECAPA-TDNN), PAD deepfake anti-spoofing, step-up MFA | FinTech Security | **Production** | NIST SRE, ISO/IEC 30107 |
| **VT03** | [`03-conversational-design-system/verticals/automotive-infotainment.md`](./03-conversational-design-system/verticals/automotive-infotainment.md) | Industry Verticals | ISO 15005 dialogue management, NHTSA distraction rules, cabin noise | Auto HMI Leads | **Production** | ISO 15005:2026, NHTSA DOT HS 811 |
| **VT04** | [`03-conversational-design-system/verticals/telephony-sip-ivr.md`](./03-conversational-design-system/verticals/telephony-sip-ivr.md) | Industry Verticals | SIP RFC 3261, G.711 transcoding, RFC 4733 DTMF, warm SIP REFER | Telecom Arch | **Production** | RFC 3261, RFC 4733, ITU-T G.711 |
| **BM01** | [`04-benchmarks-and-case-studies/industry-benchmarks.md`](./04-benchmarks-and-case-studies/industry-benchmarks.md) | Benchmarks | Empirical tear-downs of OpenAI Realtime, Gemini Live, Siri, Hume, CarPlay | All Roles | **Stable** | Empirical Benchmarking 2026 |
| **BM02** | [`04-benchmarks-and-case-studies/open-source-repos-and-tools.md`](./04-benchmarks-and-case-studies/open-source-repos-and-tools.md) | Tooling | Survey of LiveKit Agents, Pipecat AI, Silero VAD, PatternFly | Eng, Designers | **Stable** | GitHub Open-source Ecosystem |
| **DB01** | [`05-debate-and-tradeoffs/5-persona-debate.md`](./05-debate-and-tradeoffs/5-persona-debate.md) | Strategy | 5-expert debate: STT-LLM-TTS vs S2S, privacy, and voice anti-patterns | Tech Leads, PMs | **Validated** | Multi-persona strategic review |
| **CK01** | [`06-checklists-and-heuristics/vui-design-checklist.md`](./06-checklists-and-heuristics/vui-design-checklist.md) | Production QA | 25-item production readiness checklist | QA, Tech Leads | **Production** | Industry Production Standards |
| **CK02** | [`06-checklists-and-heuristics/usability-testing-protocol.md`](./06-checklists-and-heuristics/usability-testing-protocol.md) | Research | Wizard of Oz (WoZ) user testing protocol, 4-step script, TCR/CER metrics | UX Researchers | **Production** | Dahlbäck WoZ Methodology |

---

## 2. Production Engineering & Evidence Artifacts

| Artifact | Location | Category | Purpose |
|---|---|---|---|
| **Production Transcripts Comparison** | [`examples/good-vs-bad/transcripts-comparison.md`](./examples/good-vs-bad/transcripts-comparison.md) | Concrete Evidence | Side-by-side good vs. bad transcripts with acoustic root-cause diagnosis. |
| **Voice Reference Architectures** | [`architectures/voice-reference-architectures.md`](./architectures/voice-reference-architectures.md) | Topologies | Topologies for WebRTC S2S, Carrier SIP Trunking, and Embedded Automotive. |
| **Acoustic & Dialog Test Vectors** | [`test-vectors/audio-and-conversation-suites.yaml`](./test-vectors/audio-and-conversation-suites.yaml) | CI/CD Testing | Machine-readable test parameters for noise, jitter, packet loss, and conversational stress. |
| **Voice Quality Scorecard (VQS)** | [`benchmarks/voice-quality-scorecard.md`](./benchmarks/voice-quality-scorecard.md) | Metrics | 6-layer quantitative scoring rubric with 6 non-negotiable Hard-Fail gates. |
| **Academy Master Curriculum** | [`curriculum/curriculum.yaml`](./curriculum/curriculum.yaml) | Training | 8-module interactive curriculum with 10 micro-lessons adhering to 8-slide invariant. |

---

## 3. Evidence Classification Tags

To prevent subjective bias from being masqueraded as universal truth, every claim across this Knowledge Base is explicitly categorized under one of four epistemological tags:

- `[FACT]`: A proven physical, psychoacoustic, physiological, or neurological truth verified by empirical science (e.g., Cowan's 4-chunk working memory ceiling, 200ms human conversational turn-gap).
- `[RULE]`: An inviolable design constraint whose breach precipitates catastrophic failure (e.g., prohibiting audio menus > 3 items, forbidding spoken card credentials in public).
- `[RECOMMENDATION]`: An industry-tested heuristic synthesized from production deployments (e.g., conversational pacing, 800ms adaptive silence thresholds).
- `[OPEN QUESTION]`: An active technical or philosophical debate with legitimate trade-offs on multiple sides (e.g., whether speech-to-speech agents should mirror human emotional extremes such as crying or laughter).
