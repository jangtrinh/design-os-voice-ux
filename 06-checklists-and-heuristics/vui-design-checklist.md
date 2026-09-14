# Voice UX Production Launch Checklist

> A comprehensive 25-point gold standard checklist empowering UX Designers, Product Managers, and Tech Leads to rigorously evaluate voice interfaces before deploying features to production users.

![Voice UX Production Quality Verification Console](../assets/images/vui-checklist-luminous.jpg)

---

## 🎯 1. Writing for the Ear (Language & Scripting)

- [ ] **1.1 Optimal Utterance Length**: Every spoken prompt remains under 30 words or completes delivery within 6–8 seconds.
- [ ] **1.2 Rule of Three (Working Memory Bounding)**: No auditory list or spoken menu presents more than 3 selectable options within a single conversational turn.
- [ ] **1.3 Display Formatting Purged**: Bullet points, tables, bold text, markdown symbols, and raw URLs are stripped from the synthesized TTS stream.
- [ ] **1.4 Pronunciation Normalization**: Numerals, dates, currencies, phone numbers, and domain acronyms are pre-processed into normalized phonetic text (SSML/lexicons).
- [ ] **1.5 Turn-Yielding Closures**: Every conversational turn concludes with an unambiguous, action-oriented prompt rather than a dangling, open-ended statement.

---

## 👂 2. Sonic Feedback & Earcons

- [ ] **2.1 Wake Signifier (Wake Cue)**: A crisp, subtle auditory cue (< 150ms) or unambiguous visual state activates the instant microphone streaming begins.
- [ ] **2.2 Latency Bridging (Thinking State)**: An ambient rhythmic pulse or conversational bridging filler activates whenever backend processing exceeds 600ms.
- [ ] **2.3 Success Earcon (Sonic Confirmation)**: A concise earcon confirms routine task completion instead of reciting verbose, redundant confirmation prose.
- [ ] **2.4 Auditory Fatigue Prevention**: Frequently triggered earcons are tuned with soft attack envelopes and balanced frequency profiles that prevent acoustic annoyance.
- [ ] **2.5 Tactile Haptic Pairing**: On mobile and wearable devices, key sonic transitions are reinforced with synchronized, subtle haptic feedback.

---

## 🔄 3. Turn-Taking & Barge-In

- [ ] **3.1 Sub-100ms Barge-In**: Speaker playback halts instantaneously (< 80–100ms acoustic onset) the moment user speech is detected.
- [ ] **3.2 AEC Verification (No Self-Talk)**: Full-duplex Acoustic Echo Cancellation is verified at 100% speaker volume without triggering false-positive barge-in.
- [ ] **3.3 Robust Neural VAD**: Involuntary user exhalations, throat-clearing, laughter, or brief hesitation fillers (*"um"*, *"uh"*) do not prematurely truncate assistant speech.
- [ ] **3.4 Context State Truncation**: When an assistant utterance is interrupted mid-sentence, unvoiced trailing content is purged from conversational memory to prevent state hallucinations.
- [ ] **3.5 Universal Emergency Exit**: Global exit keywords (*"Stop"*, *"Cancel"*, *"Go back"*) execute instantaneously across all dialog branches and system states.

---

## 🛠️ 4. Error Recovery & Conversational Repair

- [ ] **4.1 Non-Blaming Phrasing**: Error prompts never assign fault or reprimand the user (strictly prohibiting phrasing like *"You said it wrong"* or *"Invalid command"*).
- [ ] **4.2 3-Tier Progressive Re-prompting**: Silence or unrecognized input triggers Level 1 gentle prompt -> Level 2 exemplar phrasing -> Level 3 bounded options or channel handoff.
- [ ] **4.3 Context-Sensitive Confirmation**: Applies implicit confirmation for safe, reversible commands and explicit affirmative confirmation for high-risk transactional mutations.
- [ ] **4.4 Proactive Disambiguation**: When entity resolution yields multiple candidates, the system proactively narrows choices rather than throwing a generic failure.
- [ ] **4.5 Graceful Multi-Modal Fallback**: Seamless transition to visual touch interfaces, SMS handoffs, or human escalation after three consecutive conversational repair failures.

---

## 🛡️ 5. Privacy, Ethics & Performance

- [ ] **5.1 Physical Recording Signifier**: Users are provided transparent awareness of active microphone listening via a hardware LED or unmistakable screen signifier.
- [ ] **5.2 Persona Transparency**: The assistant clearly identifies itself as an AI system and never deceives users into believing it is a biological human.
- [ ] **5.3 Public PII Redaction**: Spoken recitation of OTP verification codes, passwords, and sensitive financial balances is suppressed in high-risk or public contexts.
- [ ] **5.4 Latency Budget Compliance**: Average end-to-end response latency remains strictly under 400ms under standard mobile network conditions.
- [ ] **5.5 Voice Anti-Pattern Enforcement**: Verified that dense tabular datasets, fine vector manipulation, and parallel visual comparisons are not forced into voice modalities.
