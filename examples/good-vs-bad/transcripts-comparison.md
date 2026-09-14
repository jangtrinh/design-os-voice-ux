# Production Transcripts: Good vs. Bad Dialog Design

> Practical engineering analysis of real-world conversational failures, acoustic root causes, and production-certified design patterns.

---

## Case 1: Mid-Sentence Cognitive Hesitation

### The Scenario
User is booking a return flight and pauses to look up their calendar on their phone.

### ❌ The Broken Dialog (Static Energy VAD @ 300ms Hangtime)
```
[T=0.00s] USER:  "I'd like to book a flight to Seattle on Thursday..."
[T=2.10s] USER:  "...and return on..."
[T=2.45s] SILENCE: [User pauses to glance at calendar; 350ms passes]
[T=2.80s] VAD:   [Static VAD detects silence > 300ms. Fires Turn-Complete event!]
[T=3.10s] AGENT: "What date did you want to return?"
[T=3.25s] USER:  "...Sunday the 14th!" [COLLISION! User and Agent speak simultaneously]
[T=3.40s] AGENT: [Halts abruptly via barge-in]
[T=3.80s] AGENT: "Sorry, what did you say?"
```
- **Observed Failure**: Disjointed turn collision, user annoyance, repeated turn.
- **Acoustic Root Cause**: Static energy VAD with $300\text{ms}$ hangtime fired on preposition *"on"*, ignoring the rising/flat syntactic pitch contour.

### ✅ The Production Dialog (Semantic VAD + Grammar Prediction)
```
[T=0.00s] USER:  "I'd like to book a flight to Seattle on Thursday..."
[T=2.10s] USER:  "...and return on..."
[T=2.45s] SILENCE: [User pauses; 350ms passes]
[T=2.70s] VAD:   [Neural VAD flags silence, but Token Predictor detects incomplete preposition 'on'.]
[T=2.75s] VAD:   [Dynamically expands hangtime window to 850ms.]
[T=3.10s] USER:  "...Sunday the 14th."
[T=3.80s] VAD:   [User pitch drops -35 Hz on '14th'. Syntactic closure confirmed.]
[T=4.40s] AGENT: "Got it. Seattle departing Thursday, returning Sunday the 14th. Checking flights now."
```

---

## Case 2: Speakerphone Echo & False Self-Barge-in

### The Scenario
User is interacting with a voice assistant on a laptop through internal speakers and microphone in a conference room.

### ❌ The Broken Dialog (Misaligned Software AEC)
```
[T=0.00s] AGENT: "I found three doctors in your network with immediate availability..."
[T=0.85s] SPEAKER: [Loudspeaker plays 'availability' at 74 dB SPL]
[T=0.90s] MIC:   [Internal mic captures 'availability' echo from tabletop reflection]
[T=0.95s] AEC:   [AEC adaptive filter reference delay misaligned by 80ms; ERLE is only 9 dB]
[T=1.00s] VAD:   [VAD interprets un-canceled echo as user speech!]
[T=1.05s] CLIENT: [Triggers barge-in interrupt: kills audio playback immediately!]
[T=1.10s] AGENT: [Silent pause... awaiting user completion]
[T=3.00s] AGENT: "Sorry, I didn't catch that. Could you repeat?"
[T=4.20s] USER:  "Wait, why did you stop talking?!"
```
- **Observed Failure**: The bot interrupts itself mid-sentence without user intervention.
- **Acoustic Root Cause**: Residual echo leak exceeded VAD detection threshold due to acoustic reference timing drift.

### ✅ The Production Dialog (Hardware-Coupled AEC with DTD)
```
[T=0.00s] AGENT: "I found three doctors in your network with immediate availability..."
[T=0.85s] SPEAKER: [Plays audio]
[T=0.90s] MIC:   [Captures echo reflection]
[T=0.92s] AEC:   [Hardware AEC reference tap aligned; ERLE = 42 dB. Echo completely subtracted.]
[T=1.50s] USER:  "Just the closest one!" [User legitimately barges in]
[T=1.58s] DTD:   [Double-Talk Detector recognizes near-end speech energy distinct from echo]
[T=1.65s] CLIENT: [Smooth 20ms cosine fade of speaker output]
[T=2.10s] AGENT: "Dr. Elena Vance is 1.2 miles away on Market Street."
```

---

## Case 3: Emotional Misalignment in Bereavement

### The Scenario
Caller notifies life insurance provider of their spouse's death.

### ❌ The Broken Dialog (Saccharine Toxic Positivity)
```
[T=0.00s] USER:  [Voice trembling, slow rate, 52 dB]: "Hello... I'm calling about my husband's policy... he passed away on Monday."
[T=2.50s] AGENT: [Upbeat cheerful pitch, 170 WPM]: "Great! Thanks for calling Apex Life today! I would be more than happy to help you with that policy cancellation! Could you give me his 10-digit account number right away?"
[T=6.80s] USER:  [Weeps, clicks phone, hangs up call in distress]
```
- **Observed Failure**: Instant emotional alienation, customer trauma, regulatory complaint.
- **Root Cause**: Fixed cheerful customer-service prompt persona ignoring acoustic affect and semantic gravity.

### ✅ The Production Dialog (Calibrated Empathetic Grounding)
```
[T=0.00s] USER:  [Voice trembling, slow rate, 52 dB]: "Hello... I'm calling about my husband's policy... he passed away on Monday."
[T=2.20s] AGENT: [Classifies affect: Grief/Bereavement. Switches to 'compassionate_grounded' profile.]
[T=2.40s] AGENT: [Initial respectful 600ms acoustic pause...]
[T=3.00s] AGENT: [Low pitch contour, 115 WPM, warm timbre]: "I am so very sorry for your loss. Please take your time. There's no rush at all. Whenever you're ready, do you happen to have his name or policy number with you?"
[T=9.50s] USER:  [Calmed]: "Yes... thank you. His name is Robert Miller."
```

---

## Case 4: Cold Telephony Drop vs Warm SIP REFER

### The Scenario
Customer struggles with an automated billing system and requires human specialist escalation.

### ❌ The Broken Dialog (Cold PSTN Blind Transfer)
```
[T=0.00s] USER:  [Spends 3.5 minutes entering policy number, billing zip code, and dispute details]
[T=210s]  AGENT: "Please hold while I transfer you."
[T=212s]  SYSTEM: [Sends bare SIP BYE and blind dials queue. Session context destroyed.]
[T=245s]  HUMAN: "Thank you for calling. Can I have your full name, policy number, and the reason for your call today?"
[T=250s]  USER:  [Furious]: "I just told all of that to your stupid robot for five minutes!!"
```

### ✅ The Production Dialog (Warm SIP REFER with Encrypted UUI Context)
```
[T=0.00s] USER:  [Explains dispute details to AI]
[T=180s]  AGENT: "I see the $140 charge from August 2nd. Since this requires billing manager approval, I'm transferring you directly to Sarah in billing with your account details ready."
[T=184s]  SYSTEM: [Dispatches SIP REFER with User-to-User Information (UUI) header containing session payload.]
[T=195s]  HUMAN: [Screen pops with full transcript, verified identity, and disputed invoice]
[T=196s]  HUMAN: "Hi Mark! I'm Sarah from billing. I see the $140 charge from August 2nd on your screen right now. Let's get that credit issued for you."
[T=205s]  USER:  "Wow, thank you so much for already having that ready!"
```
