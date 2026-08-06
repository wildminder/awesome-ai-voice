---
release_date: "2026"
model_name: "VoxCPM2"
category: "tts"
summary: "OpenBMB's next-generation tokenizer-free diffusion autoregressive TTS model with 2 billion parameters."
slug: "voxcpm2"
---

# VoxCPM2

OpenBMB's next-generation tokenizer-free diffusion autoregressive TTS model with 2 billion parameters. Supports 30 languages with automatic detection, voice design from text descriptions, and high-fidelity voice cloning.

## Links

- GitHub: https://github.com/OpenBMB/VoxCPM
- HuggingFace: https://huggingface.co/openbmb/VoxCPM2
- Demo: https://huggingface.co/spaces/OpenBMB/VoxCPM-Demo

## Features

- parameters: 2B
- voice_cloning: yes
- asr: no
- pronunciation: yes
- emotion_control: yes
- languages: 30 (+ 9 Chinese dialects)
- streaming: yes (RTF ~0.3)
- audio_output: 48 kHz
- license: Apache-2.0

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 30
- streaming: ✅
- license: Apache-2.0

## Innovation

Tokenizer-free design with LocEnc → TSLM → RALM → LocDiT pipeline. Built-in super-resolution via AudioVAE V2 for 48kHz output.
