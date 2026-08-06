---
release_date: "February 4, 2026 (v1.5)"
model_name: "SoproTTS"
category: "tts"
summary: "SoproTTS is a lightweight English text-to-speech model with zero-shot voice cloning."
slug: "soprotts"
---

# SoproTTS

SoproTTS is a lightweight English text-to-speech model with zero-shot voice cloning. It uses dilated convolutions (WaveNet-style) and lightweight cross-attention layers instead of the common Transformer architecture.

## Links

- GitHub: https://github.com/samuel-vitorino/sopro
- HuggingFace: https://huggingface.co/samuel-vitorino/sopro

## Features

- parameters: 135M
- voice_cloning: yes (3-12s)
- asr: no
- pronunciation: no
- emotion_control: yes
- languages: English
- streaming: yes (250ms TTFA)
- license: Apache-2.0
- rtf: 0.05 (CPU M3)
- training-cost: ~$100
## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English
- streaming: ✅
- license: Apache-2.0
