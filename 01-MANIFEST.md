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

---

## Evidence Classification Tags

To prevent subjective bias from being masqueraded as universal truth, every claim across this Knowledge Base is explicitly categorized under one of four epistemological tags:

- `[FACT]`: A proven physical, psychoacoustic, physiological, or neurological truth verified by empirical science (e.g., Cowan's 4-chunk working memory ceiling, 200ms human conversational turn-gap).
- `[RULE]`: An inviolable design constraint whose breach precipitates catastrophic failure (e.g., prohibiting audio menus > 3 items, forbidding spoken card credentials in public).
- `[RECOMMENDATION]`: An industry-tested heuristic synthesized from production deployments (e.g., conversational pacing, 800ms adaptive silence thresholds).
- `[OPEN QUESTION]`: An active technical or philosophical debate with legitimate trade-offs on multiple sides (e.g., whether speech-to-speech agents should mirror human emotional extremes such as crying or laughter).
