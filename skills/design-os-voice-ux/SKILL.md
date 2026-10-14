---
name: design-os-voice-ux
description: "Use when working with DESIGN:OS Voice UX — Production engineering handbook, full-duplex barge-in state machines, sub-500ms latency budgets, and 6-dimension audit rubric for real-time voice AI agents."
---

# DESIGN:OS Voice UX (`design-os-voice-ux`)

Design and audit voice AI experiences that handle interruptions gracefully, mask tool-call latency with natural earcons/fillers, and degrade cleanly across noisy mobile networks.

## When to Use

Activate this skill when the user asks to:
- `"Audit our WebRTC voice agent architecture against the 6-dimension Voice UX rubric (latency, barge-in FSM, turn-taking, and error recovery)."`
- `"Design a full-duplex barge-in finite state machine with acoustic echo cancellation guards and <200ms TTS cut-off."`
- `"Create a tool-call latency choreography spec for a voice banking agent when downstream API calls take 800ms–2500ms."`

## Progressive Disclosure Routing (`What loads when`)

1. **Always Loaded**: `skills/design-os-voice-ux/SKILL.md` (this router — keeps context lean).
2. **On Demand — Prompt Recipes**: Load `docs/cookbook.md` when selecting multi-step workflows or copy-paste prompt templates.
3. **On Demand — Diagnostics**: Load `commands/doctor.md` or run `python3 scripts/self_check.py` when verifying installation or troubleshooting.
4. **On Demand — Ecosystem Discovery**: Load `llms.txt` when cross-referencing companion `DESIGN:OS` engines.

## Core Execution Workflow

1. **Inspect Context**: Read the target repository or workspace constraints before mutating files.
2. **Execute Deterministically**: Run `python3 scripts/self_check.py` or `python3 scripts/self_check.py` rather than guessing outputs freehand.
3. **Verify Quality Gates**: Run `python3 scripts/self_check.py` and confirm zero errors before reporting completion.

## Quality Bar & Anti-Scope

### It's working if...
- `python3 scripts/self_check.py` exits `0`.
- Outputs match the `DESIGN:OS` 2:1 axonometric B&W art direction and deterministic verification gates.
- Execution remains 100% local with zero external telemetry (`PRIVACY.md`).

### When NOT to use
- Asynchronous voice-note transcription apps where real-time conversational turn-taking is not required.
- Training raw acoustic speech-to-text (ASR) neural network weights from scratch.
- Purely text-based chat interfaces with no audio/speech modality.
