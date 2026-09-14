# DESIGN:OS Voice UX — Art Direction Specification

> **Style System**: Luminous Layered Precision  
> **Philosophy**: Clean, high-tech conversational product visualization translated into a calm, premium, precise interface.

---

## 🎨 Visual Identity & Mood

| Attribute | Specification | Anti-Pattern to Avoid |
|---|---|---|
| **Tone** | Sophisticated, studio-lit, calm | Flashy, loud, gamified |
| **Era** | Near-future industrial design | Sci-fi tropes, dystopian hacker aesthetic |
| **Dimensionality** | Structured depth & tactile layers | Flat minimalism OR chaotic floating elements |
| **Aesthetic** | Studio hardware & precision typography | Neon cyberpunk, heavy bloom, illegible glow |
| **Space** | Generous, airy breathing room | Crowded dashboards, tiny decorative labels |

---

## 💎 Materials & Physics

- **Surfaces**: Pearl-white (`#FFFFFF`), satin-finished matte polymer, softly tinted surfaces (`#F8F7FD`).
- **Translucency**: Selective frosted glass (Gaussian blur 20–30px, 85–92% opacity) on secondary overlay cards.
- **Metal & Edges**: Thin, micro-chamfered satin-aluminum borders (`#E3DFF0`), soft 1px edge highlights.
- **Lighting**: Broad overhead studio softbox illumination, dual-bounce ambient occlusion, soft neutral-violet contact shadows (`rgba(105, 80, 216, 0.08)`).
- **Glow & Accents**: Strictly reserved for active states, acoustic focal ripples, and immediate confirmation feedback. Never applied to static body text or borders.

---

## 🌈 Design Tokens & Color Palette

```
Canvas & Atmosphere:
├── background_base        : #F5F4FC (Atmospheric Off-White)
├── background_lavender    : #ECE7FF (Soft Ambient Glow)
└── background_blue        : #DFEDFF (Secondary Daylight Fill)

Surfaces & Structures:
├── surface_primary        : #FFFFFF (Pearl-White Enclosure)
├── surface_secondary      : #F8F7FD (Secondary Layer)
├── border_subtle          : #E3DFF0 (Precision Aluminum Bezel)
└── shadow_ambient         : rgba(105, 80, 216, 0.08)

Text & Semantic Hierarchy:
├── text_primary           : #1D1B32 (Deep Obsidian Violet)
├── text_secondary         : #615D78 (Muted Slate)
├── text_tertiary          : #9A95B2 (Subtle Metadata)

Luminous Accents:
├── accent_primary         : #6950D8 (Royal Violet — Focus & Active State)
├── accent_acoustic_cyan   : #66CFF5 (Voice Waveform & Microphone Onset)
└── accent_amber_alert     : #F5A623 (Audible Truncation & State Rollback)
```

---

## 📐 Dimensional Voice Metaphors

1. **The Exploded State Stack**:
   - Represents the 4 tiers of conversational processing (Listening → Thinking → Speaking → Tool Execution) as physical, precision-milled translucent wafers floating in register with soft contact shadows.
2. **The Acoustic Focal Core**:
   - The microphone and speech intake rendered as a physical satin-metal aperture with concentric acoustic sound rings, radiating soft violet and cyan pulses.
3. **Earcon Physicality**:
   - Tactile auditory signifiers visualized as tactile sculpted capsules with micro-relief icons and physical depth rather than flat software icons.
4. **Waveform Architecture**:
   - Speech audio streams visualized as elegant, high-definition vector oscillations rather than jagged, pixelated waveforms.
