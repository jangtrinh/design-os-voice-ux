# Nielsen Norman Group 10 Usability Heuristics Applied to VUI

> Jakob Nielsen's classic 10 Usability Heuristics were originally created for graphical user interfaces. When applied to Voice User Interfaces (VUIs), they must be reinterpreted through the lens of auditory processing and non-visual interaction.

![Nielsen Norman Usability Heuristics Applied to Voice AI Architecture](../assets/images/vui-heuristics-luminous.jpg)

---

## 1. Visibility of System Status -> Acoustic Status Awareness

* **Original Heuristic**: The system should always keep users informed about what is going on, through appropriate feedback within reasonable time.
* **Applied to VUI**: Lacking visual progress bars, the system must communicate four core states via auditory signifiers or spoken cues:
  1. **Listening**: Visual LED ring illumination or an ascending wake earcon.
  2. **Thinking**: Ambient pulse or a conversational filler (*"Give me just a second..."*).
  3. **Speaking**: Active waveform indicator or synthesized voice output.
  4. **Turn Complete**: Downward terminal prosody signalling that speaking rights have yielded back to the user.

---

## 2. Match Between System and the Real World

* **Original Heuristic**: The system should speak the users' language, with words, phrases, and concepts familiar to the user.
* **Applied to VUI**:
  - Avoid forcing users into rigid syntax templates (such as *"Schedule meeting [Name] [Date] [Time]"*).
  - Support natural conversational phrasing, vernacular variations, and anaphoric references (*"it"*, *"tomorrow"*, *"that day"*).
  - Use natural prosody with appropriate intonation, cadence, and stress instead of robotic, flat text-to-speech.

---

## 3. User Control and Freedom

* **Original Heuristic**: Users often make mistakes and need a clearly marked "emergency exit" to leave the unwanted state.
* **Applied to VUI**:
  - **Universal Barge-In**: Users must be able to interrupt the voice agent at any millisecond without waiting for it to finish speaking.
  - **Global Emergency Exits**: The system must reliably recognize escape utterances: *"Stop"*, *"Go back"*, *"Skip"*, and *"Cancel"* at every stage of the dialogue flow.

---

## 4. Consistency and Standards

* **Original Heuristic**: Users should not have to wonder whether different words, situations, or actions mean the same thing.
* **Applied to VUI**:
  - Maintain a consistent **Voice Persona**: Tone, vocabulary register, and conversational framing must remain coherent throughout the session.
  - Consistent **Earcons**: A success confirmation chime must maintain identical frequency, envelope, and acoustic structure across the product ecosystem.

---

## 5. Error Prevention

* **Original Heuristic**: Better than even the best error messages is a careful design which prevents a problem from occurring in the first place.
* **Applied to VUI**:
  - **Implicit Confirmation**: Embed understood parameters into the subsequent question so users can catch misunderstandings without breaking dialogue momentum.
    - *Example*: *"I booked a ride to 123 Le Loi Street. Would you like to pay with cash or your digital wallet?"* (Implicitly confirms destination).
  - **Explicit Confirmation**: Mandatory for high-stakes or irreversible actions (funds transfer, data deletion, sensitive communications).

---

## 6. Recognition Rather Than Recall

* **Original Heuristic**: Minimize the user's memory load by making objects, actions, and options visible.
* **Applied to VUI**:
  - Because spoken audio leaves no persistent visual footprint, **never present more than 3 options** per turn.
  - **Contextual Re-anchoring**: Briefly recap context when resuming an interrupted conversation: *"Earlier, you were looking for flights to Da Nang for this Saturday. Would you like to continue?"*

---

## 7. Flexibility and Efficiency of Use

* **Original Heuristic**: Accelerators may speed up the interaction for the expert user.
* **Applied to VUI**:
  - **Multi-slot One-shot Execution**:
    - *Novice*: Guided step-by-step through slot filling.
    - *Expert*: Expresses all intents simultaneously: *"Order two iced milk coffees with light sugar delivered to the office before 9 AM"* -> System extracts all parameters in a single turn without tedious sub-prompting.

---

## 8. Aesthetic and Minimalist Design

* **Original Heuristic**: Dialogues should not contain information which is irrelevant or rarely needed.
* **Applied to VUI**:
  - **Verbal Economy**: Eliminate repetitive conversational boilerplate and excessive pleasantries like: *"Yes certainly, valued customer, I would be delighted to inform you that..."*.
  - Go straight to core information value. In VUI, verbosity is auditory clutter.

---

## 9. Help Users Recognize, Diagnose, and Recover from Errors

* **Original Heuristic**: Error messages should be expressed in plain language, precisely indicate the problem, and constructively suggest a solution.
* **Applied to VUI**:
  - Never use dead-end generic errors: *"An error occurred. Please try again later."*
  - State clearly what was parsed and what is missing: *"I heard you want to book tickets to Nha Trang, but what date would you like to depart?"*

---

## 10. Help and Documentation

* **Original Heuristic**: Even though it is better if the system can be used without documentation, it may be necessary to provide help.
* **Applied to VUI**:
  - When a user asks: *"What can I do here?"* or *"Help me"*, do not read a five-minute manual; deliver **2–3 relevant sample actions tailored to the current context**.
  - Provide an escalation path to human agents or send a deep link with complete documentation to their mobile device.
