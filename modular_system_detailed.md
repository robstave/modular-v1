
# 🔧 Modular Synth System Overview (Lunetta-Inspired)

This document describes a custom-built modular synth system inspired by **Stanley Lunetta’s CMOS-based designs**, along with elements from **CGS** (Cat Girl Synth) and microcontroller logic. The system uses banana jacks and 5V logic-level signals, mixing analog and digital modules across 11 vertical panels.

---

## 🧭 System Map

Each vertical panel in the lower row is numbered left to right:

| Panel # | Module Type                         | Key Components                          |
|---------|-------------------------------------|------------------------------------------|
| 1       | Power + Ground Distribution         | Switch, banana jacks                     |
| 2       | Hex Oscillators (40106)             | 40106 IC, toggle switches                |
| 3       | VCOs (x2)                           | CV, square out, partial mix              |
| 4       | Logic Gates                         | NANDs and XORs                           |
| 5       | ATTINY85 LFOs                       | Sine/Triangle, Square, chaotic sum       |
| 6       | NAND/NOR + One-Shots                | CMOS logic, buttons                      |
| 7       | Probability Gate                    | ATTINY85, CV knobs, clock in             |
| 8       | LPGs + Mixers + Output              | Vactrols, passive mixers, banana-to-¼"   |
| 9       | Clock Dividers                      | /2, /4, /8, etc.                         |
| 10      | R-2R DAC + Mixer + Output           | Digital-to-analog, sequencer behavior    |
| 11      | Audio Mixer                         | Final summing stage                      |

---

## 🔌 Panel 1: Power and Ground Distribution
- Provides 5V power and a ground reference for the whole system.
- Essential when patching in external modules (e.g., Baby 8).
- Red banana jack = +5V, black = GND.

> 💡 **Tip**: Always connect ground before any signal to avoid floating logic levels.

---

## 🎛️ Panel 2: Hex Oscillators ([40106](https://www.ti.com/product/CD40106B))
- Each inverter is configured as a square wave oscillator.
- Toggle switches select high or low frequency range.
- Black jack = gate input.
- Useful for tones or modulation of logic gates.

---

## 🔊 Panel 3: Voltage-Controlled Oscillators (VCOs)
- Two working VCOs with:
  - Top knob: frequency
  - Bottom knob: CV amount
  - Blue jack: CV input
  - Square wave output on right
- Green jack outputs are likely a mix.
- One VCO section is non-functional.

> ⚙️ **CV input works best with**: LFOs or output from R-2R for stepped tones.

---

## 🔗 Panel 4: NAND & XOR Logic Gates
- 2 NANDs and 2 XORs using CMOS logic chips.
- Black jacks = inputs, Red = outputs.
- Great for creating gate patterns or rhythmic pulses.

> ⚠️ **Requires full logic HIGH (5V)** to activate gates properly.

---

## 🌊 Panel 5: Analog LFOs (ATTINY85-Based)
- Microcontroller-driven scene selection.
- Red button selects waveform combinations.
- Outputs:
  - Green: analog (sine, ramp, triangle)
  - Red: logic-level square
  - Blue: chaotic mix of both LFOs

> 🎯 Excellent for clocking VCOs, driving CV inputs, or modulating LPGs.

---

## 🔘 Panel 6: NAND/NOR + Manual One-Shots
- Three sets of logic gates:
  - IN1 + IN2 (black)
  - OUT1 = NAND, OUT2 = NOR (red)
- Bottom buttons = momentary logic HIGH triggers.

> ✋ **Use case**: Interactive triggering for rhythm generation or clock seeding.

---

## 🎲 Panel 7: Probability Gate (ATTINY85-Based)
- Clock-driven random gate generator.
- Inputs:
  - Black = Clock
- Outputs:
  - Red = Probabilistic gates
- Knobs:
  - Top: probability
  - Bottom: gate width

> 🥁 **Ideal for**: Triggering drum modules or adding randomness to sequences.

---

## 🚪 Panel 8: LPGs + Mixers + Output Adapter
- 4x **Low-Pass Gates** using vactrols:
  - Blue = audio in
  - Yellow = gate trigger
  - Green = output
  - Switch = darker/faster cap choice
- 2x passive mixers with grounding buttons.
- Passive banana to ¼" output.

> 🧼 Best for subtle, organic fading with LFOs — not snappy percussive envelopes.

---

## ⏱️ Panel 9: Clock Dividers
- Two independent divider banks.
- Black input, red divided outputs.
- Visual feedback via **bright blue LEDs**.

> 🔁 Use to derive slower patterns or sub-rhythms from fast clocks.

---

## 🧮 Panel 10: R-2R Ladder DAC + Mixer + Output
- R-2R resistor ladder creates stepped voltages.
- Input digital signals via black jacks.
- Output stepped analog voltages via red jacks.
- Patch red to VCO CV for sequencer-style output.
- Bottom section includes passive mixer and ¼" output.

> 🔢 Generates sequences when clocked digital inputs are sent to black jacks.

---

## 🎚️ Panel 11: Audio Mixer
- Summing mixer for combining audio sources.
- Final output stage.
- Likely passive.

> 🎧 Combine all your oscillators or processed signals here before external amplification or recording.

---

## 📎 Links and References
- [Stanley Lunetta overview on electro-music.com](https://electro-music.com/forum/forum-160.html)
- [40106 Hex Schmitt Trigger Inverter Datasheet](https://www.ti.com/product/CD40106B)
- [CGS Synth DIY Projects](http://www.cgs.synth.net/)
- [ATTINY85 Microcontroller Overview](https://www.microchip.com/en-us/product/ATtiny85)
- [Banana jack synth building basics](https://sdiy.info/wiki/Banana)

---

*System by: [Your Name]*  
*Documented with ❤️ by ChatGPT*

