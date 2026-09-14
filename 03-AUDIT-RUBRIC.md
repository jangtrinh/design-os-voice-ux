# 03-AUDIT-RUBRIC: 100-Point Scoring Framework & 6 Hard Gates

> Comprehensive audit rubric established by senior Voice AI engineering and design leads, structured across 4 core pillars (100 points) and 6 fatal Hard-Fail Gates.

---

## 🚦 6 Hard-Fail Gates

Violating **any single one of these 6 gates** results in an immediate **AUTOMATIC VETO**, categorizing the system as **`NOT PRODUCTION READY`**, regardless of overall point score:

| Gate | Name | Immediate Failure Trigger |
|---|---|---|
| **G1** | **Measurable Timing** | Absence of quantitative latency specifications across psychoacoustic boundaries (0–300ms, 300–500ms, >800ms). |
| **G2** | **Endpointing Rigor** | Equating static acoustic silence timeouts with Semantic End-of-Turn completion. |
| **G3** | **Barge-in Reality** | Treating Barge-In as a simplistic boolean toggle rather than an asynchronous multi-tier State Machine. |
| **G4** | **Audible Context** | Permitting unvoiced assistant speech (portions truncated before user heard them) to persist in conversation memory (`Audible Boundary Truncation`). |
| **G5** | **Structured Repair** | Lack of progressive, escalating repair strategies (e.g., verbatim repetition of generic error prompts > 2 times). |
| **G6** | **Test Traceability** | Inability to trace design checklist assertions back to measurable empirical test suites (Usability Testing Protocol / CI suite). |

---

## 📊 100-Point Scoring Matrix

```
Total Score: 100 Points
├── 1. Latency & Pacing             : 30 Points
├── 2. Barge-In & Turn-Taking       : 30 Points
├── 3. Conversational Psychology    : 30 Points
└── 4. Cross-Document Integrity     : 10 Points
```

---

### 1. Latency & Pacing (30 Points)

| Criterion | Points | Acceptance Standard |
|---|---|---|
| **L1. Latency Anatomy** | 6 | Precise breakdown of all 4 latency components: Client VAD, Network Transport, TTFT (Time-to-first-token/audio), Audio Playback Buffering. |
| **L2. Conversational Sweet Spot** | 6 | Architecture guarantees standard conversational latency strictly within `< 400ms`. |
| **L3. Acoustic Fillers & Bridging** | 6 | Natural bridging fillers (*"Let me check that"*, subtle haptics/ambience) triggered when processing exceeds `> 600ms`. |
| **L4. Dead-Air Prevention** | 6 | Strict guarantee that acoustic dead air never exceeds 1.0 second without sensory feedback. |
| **L5. Network Adaptation** | 6 | Graceful degradation and adaptive jitter buffering over unstable mobile networks (WebRTC UDP). |

---

### 2. Barge-In & Turn-Taking (30 Points)

| Criterion | Points | Acceptance Standard |
|---|---|---|
| **B1. Interruption State Model** | 6 | Rigorous multi-state interruption handling: Listening / Thinking / Speaking / Tool Execution. |
| **B2. Interruption Latency** | 5 | Time to acoustic speaker silence from user onset strictly `< 100ms` (`p50 < 80ms`, `p95 < 120ms`). |
| **B3. Intent vs Noise Discrimination** | 5 | Robust differentiation between intentional speech and backchanneling, coughing, throat clearing, or ambient bursts. |
| **B4. Audible Boundary Truncation** | 5 | **MANDATORY**: Memory pruned strictly at the exact timestamp of acoustic interruption. |
| **B5. Post-Interruption Recovery** | 5 | Immediate prioritization of the interrupting intent without defensive apologies or re-explanations. |
| **B6. Compliance & Safety Exceptions** | 4 | Explicit protocol defining legally mandated disclosures and life-critical warnings that prohibit interruption or require re-affirmation. |

---

### 3. Conversational Psychology & Grounding (30 Points)

| Criterion | Points | Acceptance Standard |
|---|---|---|
| **P1. Grounding (Clark & Brennan)** | 5 | Clear demarcation: Implicit grounding for low-risk actions vs. Explicit confirmation for high-stakes transactions. |
| **P2. Turn-Taking Psychology** | 5 | Natural floor transfer pacing (200–300ms gap); neither conversational collision nor sluggish lag. |
| **P3. 3-Tier Escalating Repair** | 5 | Progressive escalation: Tier 1 Gentle re-prompt → Tier 2 Concrete exemplar → Tier 3 Bounded menu or graceful human handoff. |
| **P4. Cognitive Load & Chunking** | 4 | Strict adherence to Cowan's working memory law: Maximum 3 items per audio menu; sentences under 30 words. |
| **P5. Agency & User Control** | 4 | Universal emergency commands (*"Stop"*, *"Cancel"*, *"Back"*) functional across 100% of dialog states. |
| **P6. Trust & Transparency** | 4 | Full transparency regarding AI identity; truthful error reporting; no hallucinated certainty. |
| **P7. Functional Empathy** | 3 | Avoidance of ELIZA traps and the Uncanny Valley; expressing empathy through swift operational competence rather than performative sentiment. |

---

### 4. Cross-Document Integrity (10 Points)

| Criterion | Points | Acceptance Standard |
|---|---|---|
| **I1. Canonical Glossary Consistency** | 3 | 100% adherence to definitions specified in `CONTEXT.md`. |
| **I2. Architectural Coherence** | 3 | Zero contradictions between Foundations, Interaction Patterns, Design System, and Benchmarks. |
| **I3. Traceability to Testing** | 2 | Every design heuristic maps directly to measurable criteria in `usability-testing-protocol.md`. |
| **I4. Provenance & Evidence** | 2 | Every claim tagged with `[FACT]`, `[RULE]`, `[RECOMMENDATION]`, or `[OPEN QUESTION]`. |

---

## 🏆 Maturity Classification Tiers

```
90 - 100 Points + PASS 6 Gates  ──►  Tier 1: PRODUCTION READY (Approved for broad deployment)
75 - 89 Points  + PASS 6 Gates  ──►  Tier 2: FIELD TEST READY (Restricted pilot trials permitted)
< 75 Points   OR FAIL 1 Gate    ──►  Tier 3: NOT PRODUCTION READY (Deployment blocked, remediation required)
```
