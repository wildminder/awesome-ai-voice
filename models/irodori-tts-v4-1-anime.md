---
release_date: "September 4, 2026"
model_name: "Irodori-TTS-v4.1-Anime"
category: "tts"
summary: "phasefield-audio — Japanese anime-style TTS fine-tuned from Aratako/Irodori-TTS-v4.1-Small on independently annotated anime speech data; 0.8B params, MIT, with int8/int4/fp8 quantized variants."
slug: "irodori-tts-v4-1-anime"
---

# Irodori-TTS-v4.1-Anime

Irodori-TTS-v4.1-Anime is a Japanese text-to-speech model fine-tuned from [Aratako/Irodori-TTS-v4.1-Small](https://huggingface.co/Aratako/Irodori-TTS-v4.1-Small) using anime-style speech data. Because the base model's annotation pipeline is not publicly documented, the fine-tuning data was annotated independently — so caption conditioning and emoji controls may behave differently from the base model. The full-precision checkpoint (0.8B params, F32) ships at the repository root, with quantized variants (`int8-weight-only`, `int8-dynamic`, `int4-weight-only`, `float8-weight-only`, `float8-dynamic`) in subdirectories. It follows the base model's MIT License and ethical restrictions; inference uses the original [Irodori-TTS repository](https://github.com/Aratako/Irodori-TTS).

## Links

- HuggingFace: https://huggingface.co/phasefield-audio/Irodori-TTS-v4.1-Anime
- GitHub: https://github.com/Aratako/Irodori-TTS
- Demo: https://huggingface.co/spaces/hugging-apps/irodori-tts-anime-demo

## Features

- voice_cloning: —
- asr: no
- languages: Japanese
- license: MIT
- parameters: ~0.8B (766,052,385 F32)
- architecture: Irodori-TTS (Aratako) fine-tune; caption-conditioned with emoji controls
- base_model: Aratako/Irodori-TTS-v4.1-Small
- variants: int8-weight-only, int8-dynamic, int4-weight-only, float8-weight-only, float8-dynamic

## Comparison

- asr: ❌
- languages: Japanese
- license: MIT

## Innovation

A community fine-tune that ports the Irodori-TTS line into the anime-voice domain using an independently built annotation pipeline (since the base model's is undocumented), and ships the result with five ready-made quantization variants (int4/int8/fp8) for efficient inference.
