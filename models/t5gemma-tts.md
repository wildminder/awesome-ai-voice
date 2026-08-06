---
release_date: "2026"
model_name: "T5Gemma-TTS"
category: "tts"
summary: "Multilingual TTS model with voice cloning and duration control, built on the T5Gemma encoder-decoder LLM architecture."
slug: "t5gemma-tts"
---

# T5Gemma-TTS

Multilingual TTS model with voice cloning and duration control, built on the T5Gemma encoder-decoder LLM architecture. Supports batch generation for multiple audio variations.

## Links

- GitHub: https://github.com/Aratako/T5Gemma-TTS
- HuggingFace: https://huggingface.co/Aratako/T5Gemma-TTS-2b-2b
- Demo: https://huggingface.co/spaces/Aratako/T5Gemma-TTS-Demo

## Features

- parameters: 2B-2B
- voice_cloning: yes
- asr: no
- pronunciation: yes
- emotion_control: no
- languages: English, Chinese, Japanese
- streaming: no
- license: MIT
- vram: 7.6-10.6 GB

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English, Chinese, Japanese
- streaming: ❌
- license: MIT

## Innovation

PM-RoPE positional encoding with XCodec2 audio codec. Low-VRAM options with CPU offloading. Batch inference efficiency with single encoder pass.
