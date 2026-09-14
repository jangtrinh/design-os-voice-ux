# DESIGN:OS Voice UX — Art Direction & Meta-Prompt Specification

> **Style System**: Luminous Layered Precision (Isometric 3D)  
> **Philosophy**: Architectural exploded-view product visualization translating conversational voice AI mechanics into tactile, frosted-glass hardware layers with strict 35° isometric perspective, minimal typography, and studio illumination.

---

## 📐 The 4 Core Visual Laws

| Law | Specification | Anti-Pattern to Avoid |
|---|---|---|
| **1. Strict 35° Isometric Grid** | Every UI element (pill buttons, waveforms, gauges, sliders, chips) must be mapped flush onto the 3D surface plane of its glass wafer. | 2D flat text overlays, misaligned skew, floating billboards disconnected from plane |
| **2. Radical Text Minimization** | Max 1–2 words per chip/button (e.g., `Confirm`, `Latency`, `0.58`). Never put explanatory paragraphs, headers, or bullet points on the canvas. | Text-heavy infographics, poster title blocks, illegible miniature text |
| **3. Tactile Glass & Material Physics** | Thick borosilicate glass wafers with rounded corners, 1px bright specular chamfers, soft caustic refractions, hovering over a brushed frosted aluminum base. | Flat opacity boxes, dirty smudge textures, harsh plastic reflections |
| **4. Studio Atmospheric Lighting** | Clean seamless soft lilac studio gradient (`#F5F4FC` → `#ECE7FF`). Diffused violet-cyan subsurface glow radiating from underneath the glass wafers. | Pitch black sci-fi, cyberpunk neon bloom, dark gamer/hacker aesthetics |

---

## 🎨 Design Tokens & Palette

```yaml
Atmosphere:
  canvas_base: "#F5F4FC"      # Clean soft atmospheric lilac
  ambient_lavender: "#ECE7FF" # Subtle secondary depth glow
  fill_daylight: "#DFEDFF"    # Subtle daylight fill

Materials:
  wafer_glass: "Translucent borosilicate glass (90% transmission, refractive index 1.52)"
  edge_bevel: "1px crisp white specular chamfer (#FFFFFF)"
  chassis_base: "Anodized pearl-white & satin-brushed aluminum (#F0EEF8)"
  caustic_shadow: "Soft neutral-violet contact shadows rgba(105, 80, 216, 0.08)"

Luminous Acoustic Accents:
  royal_violet: "#6950D8"     # Active focus, intent selection, confirmation
  electric_cyan: "#66CFF5"    # Speech intake, live audio waveforms, microphone onset
  amber_alert: "#F5A623"      # Audible boundary truncation, rollback, warning
```

---

## 🧬 Reusable Meta-Prompt Schema

When generating illustrations for any section, use this parameterized template:

```text
High-end 3D architectural exploded isometric product visualization demonstrating {TOPIC_NAME} in a Next-Gen Voice AI Operating System.
Style: Luminous Layered Precision.
Color palette: Clean soft lilac studio background (#F5F4FC, #ECE7FF), royal violet (#6950D8) and electric cyan (#66CFF5) glowing acoustic elements, white translucent frosted borosilicate glass wafers with sharp 1px specular edges.
Composition: 35-degree isometric exploded view with 3 vertically floating translucent glass interface slabs hovering over a solid frosted satin-aluminum chassis slab:
- Base slab ({TIER_1_NAME}): {TIER_1_ELEMENTS_EMBOSSED_ON_PLANE}.
- Middle slab ({TIER_2_NAME}): {TIER_2_ELEMENTS_EMBOSSED_ON_PLANE}.
- Top slab ({TIER_3_NAME}): {TIER_3_ELEMENTS_EMBOSSED_ON_PLANE}.
Perspective & Affordance: Strict 35-degree isometric alignment. All buttons, gauges, tactile chips, and waveforms are surface-mapped directly onto the glass planes with realistic depth, specular highlights, and contact shadows.
Typography: Ultra-minimal. No long sentences, no paragraphs, no canvas titles. Pure tactile iconography, numbers, and short functional chips.
Lighting: Soft studio softbox lighting with delicate caustic reflections, diffused violet-cyan subsurface glow beneath each layer, 8k crisp raytraced industrial product design render.
Avoid: Dark backgrounds, black sci-fi, cyberpunk neon clutter, avatars, human figures, floating 2D billboard text.
```

---

## 🗺️ Master Visual Roadmap for Documentation

| Section | Topic | Visual Metaphor | Status |
|---|---|---|---|
| `README.md` | Hero Overview | Master Voice AI Console with 4 glass tiers | ✅ Ready (`voice-ux-hero.jpg`) |
| `01-foundations/mental-models` | Gulf of Execution | Auditory signifiers bridging GUI vs VUI void | ✅ Ready (`gulf-of-execution-vui.jpg`) |
| `01-foundations/mental-models` | Acoustic Signifiers | Smart speaker puck with 360° cyan LED ring & beamforming pointer | ✅ Ready (`acoustic-signifier-ring.jpg`) |
| `01-foundations/mental-models` | Verbosity vs Brevity | Dense 10-slat text wall vs single cyan acoustic capsule | ✅ Ready (`chatbot-vs-voice-first.jpg`) |
| `01-foundations/conversational-psychology` | Conversational Psychology | Cognitive load timing & Gricean Maxims balance | ✅ Ready (`conversational-psychology-luminous.jpg`) |
| `01-foundations/conversational-psychology` | Working Memory Limits | 3 glowing cyan slots with amber overflow barrier blade | ✅ Ready (`cowans-memory-slots.jpg`) |
| `01-foundations/conversational-psychology` | Auditory Fatigue Filter | Sharp violet spikes smoothed into gentle cyan waves through glass baffle | ✅ Ready (`auditory-fatigue-filter.jpg`) |
| `01-foundations/vui-heuristics` | 7 VUI Heuristics | 7-part radial modular wafer gauge | ✅ Ready (`vui-heuristics-luminous.jpg`) |
| `01-foundations/vui-heuristics` | System Status Indicators | 4 linear bays (Mic, Pulse Ring, Wave, Idle Dot) | ✅ Ready (`acoustic-status-indicator.jpg`) |
| `01-foundations/vui-heuristics` | Emergency Exit Switch | Recessed octagonal ruby stop button with return-arrow glass lens | ✅ Ready (`emergency-exit-switch.jpg`) |
| `02-interaction-patterns/turn-taking` | Turn-Taking & Barge-In | Truncated speech waveform & sub-80ms onset | ✅ Ready (`barge-in-luminous.jpg`) |
| `02-interaction-patterns/turn-taking` | Full-Duplex WebRTC Flow | Dual parallel bidirectional glass light pipes with AEC prism | ✅ Ready (`duplex-webrtc-flow.jpg`) |
| `02-interaction-patterns/turn-taking` | EoU Dual Detection | Parallel acoustic silence gauge & semantic completion latch | ✅ Ready (`vad-semantic-detection.jpg`) |
| `02-interaction-patterns/turn-taking` | Audible Boundary Rollback | Glass razor cutting timeline track & pruning downstream buffer | ✅ Ready (`audible-boundary-rollback.jpg`) |
| `02-interaction-patterns/error-recovery` | Progressive Recovery | 3-Tier Glass Stack (Nudge, Disambiguation, Handshake) | ✅ Ready (`progressive-recovery-luminous.jpg`) |
| `02-interaction-patterns/error-recovery` | Reprompting Escalation | 3-tier staircase (open dish, bifurcated wells, keyhole socket) | ✅ Ready (`reprompting-levels.jpg`) |
| `02-interaction-patterns/audio-feedback` | Earcons & Audio Signifiers | Tactile earcon capsules & spectral frequency chips | ✅ Ready (`earcons-luminous.jpg`) |
| `02-interaction-patterns/audio-feedback` | ADSR Sound Envelope | Tactile acoustic glass wafer with 4-point ADSR inflection curve | ✅ Ready (`adsr-sound-envelope.jpg`) |
| `02-interaction-patterns/audio-feedback` | Decibel Level Ladder | Stepped glass ladder gauge with 5 tactile tiers | ✅ Ready (`decibel-ladder-levels.jpg`) |
| `02-interaction-patterns/multimodal-handshake` | Multimodal Handshake | Cross-device glass handoff (Voice to Watch & Screen) | ✅ Ready (`multimodal-handshake-luminous.jpg`) |
| `02-interaction-patterns/multimodal-handshake` | In-Cabin Automotive Handoff | Steering wheel puck, panoramic glass HUD, and docked tablet | ✅ Ready (`attention-handoff-driving.jpg`) |
| `03-conversational-design/latency-budgets` | Latency Budget Stack | Stacked millisecond timing wafers (VAD, STT, LLM, TTS) | ✅ Ready (`latency-budgets-luminous.jpg`) |
| `03-conversational-design/latency-budgets` | Acoustic Bridging | Levitating pulsing glass bead bridging latency dead-air gap | ✅ Ready (`acoustic-bridging-filler.jpg`) |
| `03-conversational-design/latency-budgets` | Adaptive Jitter Buffer | Linear glass channel reconstructing dropped packets with light | ✅ Ready (`jitter-buffer-adaptive.jpg`) |
| `03-conversational-design/persona-and-tone` | Persona & Acoustic Brand | Dynamic acoustic resonance & vocal pitch profile | ✅ Ready (`persona-tone-luminous.jpg`) |
| `03-conversational-design/persona-and-tone` | Prosodic Emotional Adaptation | Knurled rotary dials with 3 undulating pitch ribbons | ✅ Ready (`speech-synthesis-prosody.jpg`) |
| `03-conversational-design/prompt-and-dialog` | Dialog Engineering | Slot-filling wafer stack with prompt token meters | ✅ Ready (`dialog-engineering-luminous.jpg`) |
| `03-conversational-design/prompt-and-dialog` | Safety Gate & Guardrails | Glass security shield admitting valid tokens, deflecting amber shards | ✅ Ready (`prompt-guardrails-gate.jpg`) |
| `03-conversational-design/prompt-and-dialog` | Entity Slot Filling | Geometric glass puzzle tokens magnetically snapping into cutouts | ✅ Ready (`entity-slot-filling.jpg`) |
| `04-benchmarks-and-case-studies/industry-benchmarks` | Industry Benchmarks | Multi-architecture performance & latency comparator | ✅ Ready (`industry-benchmarks-luminous.jpg`) |
| `04-benchmarks-and-case-studies/open-source-repos` | Toolchain Ecosystem Stack | 4 slide-in modular server cartridges on glowing rack | ✅ Ready (`opensource-toolchain-stack.jpg`) |
| `05-debate-and-tradeoffs/5-persona-debate` | Pipeline vs S2S | 3-hop seamed glass blocks vs unified crystal light pipe | ✅ Ready (`cascaded-vs-speech-to-speech.jpg`) |
| `05-debate-and-tradeoffs/5-persona-debate` | Collision Arbiter Gate | Rotary crystal prism deflecting conflicting voice stream into amber trap | ✅ Ready (`barge-in-collision-gate.jpg`) |
| `06-checklists-and-heuristics/vui-design-checklist` | Production Checklist | 5x5 Verification grid with optical laser inspection lens | ✅ Ready (`vui-checklist-luminous.jpg`) |
| `06-checklists-and-heuristics/usability-testing` | Wizard of Oz Testing Lab | Dual-station testing console with acoustic glass partition | ✅ Ready (`wizard-of-oz-testing.jpg`) |



