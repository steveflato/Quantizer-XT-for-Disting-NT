# Quantizer XT for Disting NT

A C++ plugin for the Expert Sleepers Disting NT: the stock Quantizer with per-channel transpose and shift.

## Features

- 1–12 channels, each with CV/gate in and CV/gate/change out
- Per-channel **Transpose** and **Shift**
- Quantize modes: Nearest, Mapped, Warped
- Scales: Chromatic, Major (modes Ionian–Locrian), Natural/Harmonic Minor, Dominant, Fully Diminished, Dominant Dim, Augmented, Whole Tone, with per-note include masks
- Microtuning via Scala `.scl` files from the SD card (auto KBM root/Hz)
- MIDI input (any octave / exact) and MIDI output with optional pitch bend, to breakout, Select Bus, USB or internal
- Output gate modes: Triggers, Inverted Triggers, Gates
- Piano-keyboard display of the active scale

## Installation

Copy `quant_xpose.o` to `/programs/plug-ins/steveflato/` on the Disting NT SD card, or install it with [nt_helper](https://nosuch.dev/nt-helper) from the [disting NT plugin gallery](https://nt-gallery.nosuch.dev/).

GUID: `SfQx`
