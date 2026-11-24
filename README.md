# Quantizer XT for Disting NT

A C++ plugin for the Expert Sleepers Disting NT: the stock Quantizer with per-channel transpose and shift, plus hysteresis and full microtuning (Scala, .kbm and MTS).

## Features

- 1–12 channels, each with CV/gate in and CV/gate/change out
- Per-channel **Transpose** and **Shift**
- **Hysteresis** (0–90 %, default 20 %) to stop notes flickering when the input sits near a note boundary; 0 % gives the stock behaviour
- Quantize modes: Nearest, Mapped, Warped
- Scales: Chromatic, Major (modes Ionian–Locrian), Natural/Harmonic Minor, Dominant, Fully Diminished, Dominant Dim, Augmented, Whole Tone, with per-note include masks
- Microtuning, as on the stock Quantizer:
  - Scala `.scl` files from the SD card
  - Scala `.kbm` keyboard maps from `/kbm`, or the automatic map (Auto kbm root / Hz); keys marked `x` are never output
  - MTS (MIDI Tuning Standard) `.syx` files from `/mts`
  - Live MTS SysEx over MIDI: bulk dumps, single-note changes and scale/octave tuning retune it straight away
- Built-in **poole-rod12tone** just-intonation tuning (1/1, 33/32, 9/8, 7/6, 14/11, 4/3, 11/8, 3/2, 14/9, 27/16, 7/4, 11/6), the default
- MIDI input (any octave / exact) and MIDI output with optional pitch bend, to breakout, Select Bus, USB or internal; pitch bend follows the microtuning
- Output gate modes: Triggers, Inverted Triggers, Gates
- Piano-keyboard display of the active scale

## Requirements

Disting NT firmware **1.19.0 or later**. The `.kbm` and MTS file support uses the plugin filesystem API added in 1.19.

## Installation

Copy `quant_xpose.o` to `/programs/plug-ins/steveflato/` on the Disting NT SD card, or install it with [nt_helper](https://nosuch.dev/nt-helper) from the [disting NT plugin gallery](https://nt-gallery.nosuch.dev/).

Put keyboard maps in `/kbm` and MTS files in `/mts` on the SD card.

**Upgrading from v1.0:** the Microtuning page gained Scala .kbm and MTS .syx in the same places as on the stock Quantizer. Presets saved with v1.0 need the parameters from Auto kbm root onward set again.

GUID: `SfQx`
