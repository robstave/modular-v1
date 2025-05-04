
# 🔧 Modular System Overview (Lunetta-Inspired)

This system is inspired by **Stanley Lunetta’s CMOS-based synth designs**, with additional influences from **CGS circuits** and microcontroller-based modules. It mixes **digital logic**, **analog control**, and **hand-built utility modules** — using banana jacks for patching and a 5V logic ecosystem.

---

## Panel 1: Power and Ground Distribution
- Main power switch.
- **Red banana jack**: +5V rail.
- **Black banana jack**: Ground — essential for inter-module compatibility (e.g., Baby 8 above).
- No ground = floating signals = chaos.

---

## Panel 2: Hex Oscillators (40106-Based)
- Uses **40106 hex inverter** for square wave oscillators.
- **Toggle switches** select high or low frequency.
- **Black jack** acts as a gate control for oscillators.
- Ideal for generating tones or modulating logic gates.

---

## Panel 3: Voltage-Controlled Oscillators (VCOs)
- Two working VCOs, one non-functional.
- Each has:
  - **Top knob**: Frequency
  - **Bottom knob**: CV amount/sensitivity
  - **Blue input**: CV
  - **Right output**: Square wave
- **Green outputs** likely mix the two working VCOs.
- Great for sound sources or modulated pitch.

---

## Panel 4: CMOS Logic – NAND & XOR Gates
- Two NANDs + two XORs.
- **Black inputs**, **Red outputs** (CMOS logic).
- High logic level (5V) required.
- Excellent for generating rhythmic patterns and new waveforms from logic combos.

---

## Panel 5: Analog LFOs (ATTINY85-Based)
- Digital brain with analog-feeling output.
- **Red button**: Selects LFO “scene” via ATTINY85.
- **Green outputs**: Analog (ramp, sine, triangle).
- **Red output**: Logic-level square wave (for use with logic gates).
- **Blue output**: Summed/chaotic mix of LFOs.

---

## Panel 6: NAND / NOR + One-Shot Triggers
- Three groups of:
  - **IN1 + IN2 (black)**
  - **OUT1 = NAND**, **OUT2 = NOR** (red)
- **Bottom buttons**: Manual one-shot triggers — inject logic HIGH when pressed.
- Great for step-based logic or manual rhythm triggering.

---

## Panel 7: Probability Gate (ATTINY85-Based)
- Clocked randomness generator.
- **Black input**: Clock source (from oscillator).
- **Red outputs**: Randomly fire per clock step.
- **Top knob**: Probability of triggering.
- **Bottom knob**: Gate width (length of trigger).
- Ideal for **drum triggers** or randomized modulation.

---

## Panel 8: Low-Pass Gates, Mixers, Output
- **Top 4 sections**: Vactrol-based LPGs
  - **Blue input**: Audio
  - **Yellow input**: Trigger
  - **Green output**: Filtered signal
  - **Switch**: Cap selector (up = darker)
- Best for **LFO fades**, not fast percussive VCAs.
- **Middle**: Two passive mixers w/ mute buttons.
- **Bottom**: Passive **banana to ¼" adapter**.

---

## Panel 9: Clock Dividers
- Two sections of **clock division**.
- **Black input**, **Red outputs** (divided signals).
- Useful for slowing down patterns, fattening tones, or syncing sub-events.
- Blue LEDs indicate pulse states visually.

---

## Panel 10: R-2R Ladder DAC + Mixer + Output
- **R-2R Ladder**:
  - **Black inputs**: Digital signals
  - **Red outputs**: Binary-weighted voltages (e.g., 2.5V, 1.25V)
  - Patch outputs to VCO CV for stepped sequences.
- **Middle**: Passive mixer
- **Bottom**: Passive banana-to-¼" output

---

## Panel 11: Audio Mixer
- Summing mixer for audio signals.
- Likely passive or buffered.
- Final stage for combining multiple voices into a single output.
