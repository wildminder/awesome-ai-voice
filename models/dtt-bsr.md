---
release_date: "October 16, 2025"
model_name: "DTT-BSR"
category: "restoration"
summary: "Origami Shido (Wuhan University) — ICASSP 2026 Music Source Restoration Challenge system: DTTNet-style time-frequency U-Net + BandSplitRNN-inspired band-sequence module + RoPE-based Transformer for joint time/frequency restoration."
slug: "dtt-bsr"
---

# DTT-BSR

DTT-BSR (DTTNet with **B**and**S**equence and **R**oPE) is a music-source-restoration challenge submission from team AC/DC (Wuhan University) to ICASSP 2026. It is built inside the official MSR-Kit GAN framework, where the baseline generator is replaced by a DTTNet-style time-frequency U-Net and augmented at the bottleneck with:

- a **BandSplitRNN-derived dual-path recurrence** that views the frequency axis as multiple subbands and runs grouped bi-directional RNNs alternately along time and subband dimensions, and
- a **RoPE-based Transformer** for long-range time/frequency dependencies.

The dual-path TFC-TDF backbone captures local time-frequency patterns and broader spectral correlations, while explicit sub-band modeling preserves harmonic structure for non-vocal stems.

## Links

- GitHub: https://github.com/OrigamiShido/DTT-BSR

## Features

- type: Music Source Restoration
- bandwidth_extension: no
- inpainting: no
- architecture: DTTNet TFC-TDF U-Net (complex STFT) + Improved Dual-Path BandSplitRNN block + RoPE-Transformer
- input: complex STFT (real + imag channels; n_fft=2048, hop=512)
- discriminator: Multi-Frequency Discriminator (baseline)
- framework: MSR-Kit GAN (reconstruction + adversarial + feature-matching losses)
- license: MIT

## Comparison

- type: Music Source Restoration
- bandwidth_extension: ❌
- inpainting: ❌
- license: MIT

## Innovation

Treats music-source restoration as a **complex-STFT time-frequency U-Net enhancement at the bottleneck**: keep the strong DTTNet dual-path TFC-TDF structure for local spectral patterns, then layer in BandSplitRNN-style sub-band recurrence + RoPE self-attention so the generator can model long-range, cross-band harmonic structure that ordinary GAN baselines miss — critical for restoring non-vocal stems cleanly.
