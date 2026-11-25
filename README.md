# Quantizer XT for Disting NT

A C++ plugin for the Expert Sleepers Disting NT: the stock Quantizer with per-channel transpose and shift, just-intonation ratios you type in on the module, noise-proof hysteresis, and full microtuning (Scala, .kbm and MTS).

## Features

- 1–12 channels, each with CV/gate in and CV/gate/change out. Channel *n* starts out on **Input n → Output n**
- Per-channel **Transpose** and **Shift**
- **JI ratios**: enter a just-intonation scale on the NT, no Scala file needed (merged from the [Just Intonation Quantizer](https://github.com/steveflato/Just-Intonation-Quantizer))
  - A **JI ratios** page right after Microtuning, with a Numerator and Denominator per note; each Denominator shows the ratio and its size in cents
  - 1/1 is always included; ratios are folded into the octave, sorted and de-duplicated automatically
  - Defaults to **poole-rod12tone** (1/1, 33/32, 9/8, 7/6, 14/11, 4/3, 11/8, 3/2, 14/9, 27/16, 7/4, 11/6); 43 notes gives Harry Partch's 43-tone scale
  - Place the 1/1 anywhere with *Auto kbm root* and *Auto kbm Hz*
- **Hysteresis** (0–90 %, default 20 %) with input smoothing and note debounce, so noisy or slewed CV doesn't bounce between notes; 0 % gives the stock behaviour
- Quantize modes: Nearest, Mapped, Warped
- Scales: Chromatic, Major (modes Ionian–Locrian), Natural/Harmonic Minor, Dominant, Fully Diminished, Dominant Dim, Augmented, Whole Tone, with per-note include masks
- Microtuning, as on the stock Quantizer:
  - Scala `.scl` files from the SD card
  - Scala `.kbm` keyboard maps from `/kbm`, or the automatic map; keys marked `x` are never output
  - MTS (MIDI Tuning Standard) `.syx` files from `/mts`
  - Live MTS SysEx over MIDI: bulk dumps, single-note changes and scale/octave tuning retune it straight away
  - Each file selector starts with **None** (or **Off** for .kbm), so it's clear when no file is in use
- MIDI input (any octave / exact) and MIDI output with optional pitch bend, to breakout, Select Bus, USB or internal; pitch bend follows the microtuning
- Output gate modes: Triggers, Inverted Triggers, Gates
- Piano-keyboard display of the active scale

## Requirements

Disting NT firmware **1.19.0 or later**. The `.kbm` and MTS file support uses the plugin filesystem API added in 1.19.

## Installation

1. **Delete any older copies** from the SD card, including `quant_xpose.o` (the old file name) wherever it is, for example in `/programs/plug-ins/` or `/programs/plug-ins/steveflato/`. Every version shares the same plugin ID, so only one can load.
2. Copy `Quantizer_XT.o` to `/programs/plug-ins/steveflato/` on the SD card.
3. Power-cycle the NT. The channel screen shows **XT v1.2** when this version is running.
4. Add **Quantizer XT** (Utility) and set the Specifications:
   - **Channels:** 1–12.
   - **JI notes:** 1–43, default 12. This is the size of the JI scale. With more channels there's room for fewer JI notes: up to 43 with 1–2 channels, 37 with 4, 21 with 8 and 5 with 12.

Put keyboard maps in `/kbm` and MTS files in `/mts` on the SD card.

**Upgrading from v1.1:** JI parameters are added at the end, so v1.1 presets keep their settings and still sound the same. New defaults (routing, None entries) only apply when you add Quantizer XT fresh.

GUID: `SfQx`
