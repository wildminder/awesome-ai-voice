---
release_date: "September 6, 2023"
model_name: "AudioSR"
category: "restoration"
summary: "Versatile audio super-resolution latent-diffusion model that upscales arbitrary low-resolution audio to 48 kHz (any → 48 kHz)."
slug: "audiosr"
---

# AudioSR

AudioSR is a versatile audio super-resolution model from Haoheliu Liu and collaborators, published alongside the arXiv paper `2309.07314`. It is a latent-diffusion model that takes arbitrary low-resolution input audio and reconstructs a 48 kHz waveform — bandwidth extension in one model. Designed to be input-rate-agnostic (8 kHz, 16 kHz, 24 kHz, 32 kHz, 44.1 kHz, 48 kHz), produces a single fixed 48 kHz output regardless of input rate, and supports both mono and stereo material. The HF model id `haoheliu/audiosr_basic` ships the Apache-2.0-licensed basic checkpoint the README links out to; the underlying implementation lives in the GitHub repo `haoheliu/versatile_audio_super_resolution`.

## Links

- HuggingFace: https://huggingface.co/haoheliu/audiosr_basic
- GitHub: https://github.com/haoheliu/versatile_audio_super_resolution
- Paper: https://arxiv.org/abs/2309.07314

## Features

- type: Audio Super-Resolution (any → 48 kHz)
- bandwidth_extension: yes (input 8 kHz – 48 kHz, output 48 kHz fixed)
- inpainting: no
- channels: mono, stereo
- license: Apache-2.0
- vram: 6 GB minimum
- long_audio: yes
- architecture: latent diffusion (audio LDM)

## Comparison

- type: Audio Super-Resolution
- bandwidth_extension: ✅
- inpainting: ❌
- license: Apache-2.0

## Innovation

Versatile bandwidth extension over a wide range of input rates (8–48 kHz) under one fixed 48 kHz output, with monaural-only and stereo-only inference paths working through the same latent-diffusion pipeline — letting a single light checkpoint cover multiple BWE tasks instead of separate per-rate models.
