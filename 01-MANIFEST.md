# 01-MANIFEST: Voice UX Knowledge Base Inventory

> Complete inventory of all specifications in the DESIGN:OS Voice UX Knowledge Base, delineating Purpose, Target Audience, Lifecycle Status, and Empirical Evidence.

---

## Core Specification Inventory

| ID | Document | Category | Core Purpose | Target Audience | Status | Empirical Evidence Basis |
|---|---|---|---|---|---|---|
| **M00** | [`README.md`](./README.md) | Navigation | Master Index, knowledge architecture & VUI Maturity Levels | All Roles | **Stable** | Standard UX Architecture |
| **M01** | [`CONTEXT.md`](./CONTEXT.md) | Governance | Canonical glossary standard (Canonical Terms vs Anti-terms) | All Roles | **Stable** | Grice, Clark & Brennan, NN/g |
| **F01** | [`01-foundations/mental-models-and-affordance.md`](./01-foundations/mental-models-and-affordance.md) | Foundations | Resolving the Gulf of Execution, invisibility & transience | Designers | **Stable** | Don Norman, Cathy Pearl |
| **F02** | [`01-foundations/conversational-psychology.md`](./01-foundations/conversational-psychology.md) | Foundations | Gricean Maxims, turn structure & Cowan's 4-chunk capacity | Designers, PMs | **Stable** | Paul Grice (1975), Cowan (2001) |
| **F03** | [`01-foundations/vui-heuristics.md`](./01-foundations/vui-heuristics.md) | Foundations | Translating Nielsen's 10 Heuristics to acoustic environments | Designers, QA | **Stable** | Nielsen Norman Group (NN/g) |
| **IP01** | [`02-interaction-patterns/turn-taking-and-barge-in.md`](./02-interaction-patterns/turn-taking-and-barge-in.md) | Patterns | Sub-100ms barge-in, Semantic VAD & Audible Boundary Truncation | Designers, Eng | **Validated** | Full-duplex WebRTC research |
| **IP02** | [`02-interaction-patterns/error-recovery-and-repair.md`](./02-interaction-patterns/error-recovery-and-repair.md) | Patterns | 3-tier progressive re-prompting, non-blaming error culture | Designers | **Stable** | Google Assistant, Conversation Analysis |
| **IP03** | [`02-interaction-patterns/audio-feedback-and-earcons.md`](./02-interaction-patterns/audio-feedback-and-earcons.md) | Patterns | Earcon design, sonic branding, 4-state acoustic frequency allocation | Sound Designers | **Validated** | Acoustic UX, Apple/Google Sound Design |
| **IP04** | [`02-interaction-patterns/multimodal-handshake.md`](./02-interaction-patterns/multimodal-handshake.md) | Patterns | Voice + GUI coordination, visual offloading, hands-busy matrix | Product Designers | **Stable** | Cheryl Platz (*Design Beyond Devices*) |
| **DS01** | [`03-conversational-design-system/persona-and-tone.md`](./03-conversational-design-system/persona-and-tone.md) | Design System | 4-axis persona framework, avoiding Uncanny Valley & ELIZA effect | Content, UX | **Stable** | Erika Hall, Reeves & Nass |
| **DS02** | [`03-conversational-design-system/prompt-and-dialog-engineering.md`](./03-conversational-design-system/prompt-and-dialog-engineering.md) | Design System | Writing for the ear, Voice LLM System Prompt standard, SSML | Prompt Eng, UX | **Validated** | W3C SSML 1.1, LLM System Prompts |
| **DS03** | [`03-conversational-design-system/latency-budgets.md`](./03-conversational-design-system/latency-budgets.md) | Design System | 300ms latency budgeting, acoustic fillers & Native S2S architectures | Architects, Perf | **Validated** | Psychoacoustics, LiveKit benchmarks |
| **BM01** | [`04-benchmarks-and-case-studies/industry-benchmarks.md`](./04-benchmarks-and-case-studies/industry-benchmarks.md) | Benchmarks | Empirical tear-downs of OpenAI Realtime, Gemini Live, Siri, Hume, CarPlay | All Roles | **Stable** | Empirical Benchmarking 2026 |
| **BM02** | [`04-benchmarks-and-case-studies/open-source-repos-and-tools.md`](./04-benchmarks-and-case-studies/open-source-repos-and-tools.md) | Tooling | Survey of LiveKit Agents, Pipecat AI, Silero VAD, PatternFly | Eng, Designers | **Stable** | GitHub Open-source Ecosystem |
| **DB01** | [`05-debate-and-tradeoffs/5-persona-debate.md`](./05-debate-and-tradeoffs/5-persona-debate.md) | Strategy | 5-expert debate: STT-LLM-TTS vs S2S, privacy, and voice anti-patterns | Tech Leads, PMs | **Validated** | Multi-persona strategic review |
| **CK01** | [`06-checklists-and-heuristics/vui-design-checklist.md`](./06-checklists-and-heuristics/vui-design-checklist.md) | Production QA | 25-item production readiness checklist | QA, Tech Leads | **Production** | Industry Production Standards |
| **CK02** | [`06-checklists-and-heuristics/usability-testing-protocol.md`](./06-checklists-and-heuristics/usability-testing-protocol.md) | Research | Wizard of Oz (WoZ) user testing protocol, 4-step script, TCR/CER metrics | UX Researchers | **Production** | Dahlbäck WoZ Methodology |
| **PD01** | [`07-interactive-pedagogy/README.md`](./07-interactive-pedagogy/README.md) | Pedagogy | Master index, interactive pedagogy framework & evidence matrix | All Roles | **Validated** | Apple, Google, Alexa, LiveKit, Brilliant, Uxcel |
| **PD02** | [`07-interactive-pedagogy/01-learning-principles.md`](./07-interactive-pedagogy/01-learning-principles.md) | Pedagogy | Mayer's multimedia learning theory & 6-stage pedagogy loop | Educators, UX | **Validated** | Mayer (2001), Freeman et al. (2014) |
| **PD03** | [`07-interactive-pedagogy/02-conversation-design-rules.md`](./07-interactive-pedagogy/02-conversation-design-rules.md) | Pedagogy | Cognitive load, Cowan's 4 chunks, One Breath test & Gricean rules | Designers, PMs | **Validated** | Cowan (2001), Amazon Alexa, Grice |
| **PD04** | [`07-interactive-pedagogy/03-turn-taking-latency-repair.md`](./07-interactive-pedagogy/03-turn-taking-latency-repair.md) | Pedagogy | 200ms cadence, sub-100ms barge-in, fillers & non-blaming repair | Eng, Designers | **Validated** | Sacks (1974), OpenAI, LiveKit, Google |
| **PD05** | [`07-interactive-pedagogy/04-feedback-scaffolding.md`](./07-interactive-pedagogy/04-feedback-scaffolding.md) | Pedagogy | 4-tier progressive hint ladder & Alexa 3-tier reprompting | Educators, Eng | **Validated** | Koedinger (2006), Amazon, Uxcel |
| **PD06** | [`07-interactive-pedagogy/05-exercises-simulations.md`](./07-interactive-pedagogy/05-exercises-simulations.md) | Pedagogy | 5 pedagogical primitives: Locate, Tune, Repair, Predict, Sandbox | Educators, Eng | **Production** | Brilliant.org, Uxcel, LiveKit |
| **PD07** | [`07-interactive-pedagogy/06-assessment-mastery.md`](./07-interactive-pedagogy/06-assessment-mastery.md) | Pedagogy | Free vs Pro tiering & 5 quantitative certification rubrics | All Roles | **Production** | Industry SLA & Assessment Standards |
| **PD08** | [`07-interactive-pedagogy/07-accessibility-inclusive-voice.md`](./07-interactive-pedagogy/07-accessibility-inclusive-voice.md) | Pedagogy | Earcon + Haptic + Visual trio & Apple HIG audio session management | Designers, Eng | **Validated** | Apple HIG, Blattner (1989), W3C |
| **PD09** | [`07-interactive-pedagogy/08-ai-voice-safety-trust.md`](./07-interactive-pedagogy/08-ai-voice-safety-trust.md) | Pedagogy | Mandatory AI disclosure, calibrated confidence & audio privacy | Tech Leads, PMs | **Production** | EU AI Act, OpenAI, Microsoft Research |
| **PD10** | [`07-interactive-pedagogy/09-source-comparison-matrix.md`](./07-interactive-pedagogy/09-source-comparison-matrix.md) | Pedagogy | Cross-vendor comparison matrix (Apple, Google, Alexa, OpenAI, LiveKit) | Architects, PMs | **Validated** | Multi-vendor Industry Benchmarks |
| **PD11** | [`07-interactive-pedagogy/10-evidence-cards.md`](./07-interactive-pedagogy/10-evidence-cards.md) | Pedagogy | Official evidence cards repository (EVID-PD01 to EVID-PD10) | QA, Researchers | **Production** | Empirical Evidence Ledger |

---

## Evidence Classification Tags

To prevent subjective bias from being masqueraded as universal truth, every claim across this Knowledge Base is explicitly categorized under one of four epistemological tags:

- `[FACT]`: A proven physical, psychoacoustic, physiological, or neurological truth verified by empirical science (e.g., Cowan's 4-chunk working memory ceiling, 200ms human conversational turn-gap).
- `[RULE]`: An inviolable design constraint whose breach precipitates catastrophic failure (e.g., prohibiting audio menus > 3 items, forbidding spoken card credentials in public).
- `[RECOMMENDATION]`: An industry-tested heuristic synthesized from production deployments (e.g., conversational pacing, 800ms adaptive silence thresholds).
- `[OPEN QUESTION]`: An active technical or philosophical debate with legitimate trade-offs on multiple sides (e.g., whether speech-to-speech agents should mirror human emotional extremes such as crying or laughter).
