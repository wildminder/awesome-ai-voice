---
release_date: "2026"
model_name: "MOSS-TTS-Nano"
category: "tts"
summary: "Ultra-lightweight open-source multilingual speech generation model with only 0.1B parameters."
slug: "moss-tts-nano"
---

# MOSS-TTS-Nano

Ultra-lightweight open-source multilingual speech generation model with only 0.1B parameters. Designed for realtime speech generation that runs directly on CPU without GPU.

## Links

- GitHub: https://github.com/OpenMOSS/MOSS-TTS-Nano
- HuggingFace: https://huggingface.co/OpenMOSS-Team/MOSS-TTS-Nano-100M
- Demo: https://huggingface.co/spaces/OpenMOSS-Team/MOSS-TTS-Nano

## Features

- parameters: 0.1B
- voice_cloning: yes
- asr: no
- pronunciation: no
- emotion_control: no
- languages: 20
- streaming: yes (CPU-friendly)
- audio_output: 48 kHz Stereo
- license: Apache-2.0

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 20
- streaming: ✅
- license: Apache-2.0

## Innovation

Pure autoregressive architecture with MOSS-Audio-Tokenizer-Nano. Compresses audio to 12.5 Hz token stream using RVQ with 16 codebooks. Runs on 4-core CPU.
