---
release_date: "March 30, 2026"
model_name: "LongCat-AudioDiT"
category: "tts"
summary: "State-of-the-art diffusion-based TTS model operating directly in waveform latent space."
slug: "longcat-audiodit"
---

# LongCat-AudioDiT

State-of-the-art diffusion-based TTS model operating directly in waveform latent space. Developed by Meituan's LongCat team, it requires only a Waveform VAE and Diffusion backbone, effectively mitigating compounding errors.

## Links

- GitHub: https://github.com/meituan-longcat/LongCat-AudioDiT
- HuggingFace: https://huggingface.co/meituan-longcat/LongCat-AudioDiT-1B
- HuggingFace: https://huggingface.co/meituan-longcat/LongCat-AudioDiT-3.5B

## Features

- parameters: 1B / 3.5B
- voice_cloning: yes
- asr: no
- pronunciation: no
- emotion_control: no
- languages: Chinese, English
- streaming: no
- audio_output: 24000 Hz
- license: MIT

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Chinese, English
- streaming: ❌
- license: MIT

## Innovation

Adaptive Projection Guidance (APG) replaces traditional classifier-free guidance for elevated generation quality. Outperforms Seed-TTS on zero-shot voice cloning benchmarks.
