# `design-os-voice-ux` Prompt & CLI Cookbook

Copy-paste recipes for **DESIGN:OS Voice UX** (`skills/design-os-voice-ux/SKILL.md`).

---

## 1. Generate & Scaffold

> "Audit our WebRTC voice agent architecture against the 6-dimension Voice UX rubric (latency, barge-in FSM, turn-taking, and error recovery)."

## 2. Audit & Verify

> "Design a full-duplex barge-in finite state machine with acoustic echo cancellation guards and <200ms TTS cut-off."

## 3. Export & Automate

> "Create a tool-call latency choreography spec for a voice banking agent when downstream API calls take 800ms–2500ms."

---

## 4. CLI & Diagnostic Commands

```bash
# Run deterministic offline self-check
python3 scripts/self_check.py

# Run primary domain verification / workflow
python3 scripts/self_check.py

# Run primary CLI command
python3 scripts/self_check.py
```
