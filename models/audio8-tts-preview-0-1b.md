---
release_date: "August 19, 2026"
model_name: "Audio8 TTS Preview 0.1B"
category: "tts"
summary: "Audio8 — ultra-compact (~0.17B) zero-shot multilingual TTS with voice cloning on a Falcon H1 DualAR slow/fast architecture and a bundled 44.1 kHz codec; Chinese + English primary, six more languages experimental."
slug: "audio8-tts-preview-0-1b"
---

# Audio8 TTS Preview 0.1B

Audio8 TTS Preview 0.1B is the smallest release in the Audio8 TTS family ("the smallest zero-shot TTS worth running"): a ~170M-parameter generative model plus a separate ~120M-parameter codec decoder, making the complete audio generation stack much smaller than most modern multilingual TTS systems. It supports speech generation and **zero-shot voice cloning** (reference audio + matching transcript). Primary languages are Chinese and English, with German, Spanish, French, Italian, Japanese, and Korean as experimental/multilingual-evaluation targets. Released under the custom Audio8 Community License v1.0: non-commercial use is free, and commercial use is free only for entities with annual revenue under US$2M.

## Links

- HuggingFace: https://huggingface.co/Audio8/Audio8-TTS-Preview-0.1b
- GitHub: https://github.com/Audio8-AI/Audio8_TTS

## Features

- voice_cloning: yes (zero-shot, reference audio + transcript)
- asr: no
- languages: 8 (Chinese + English primary; de/es/fr/it/ja/ko experimental)
- license: Other
- parameters: ~0.17B main model (+ ~120M codec decoder)
- architecture: Audio8 Falcon H1 DualAR — slow AR (semantic tokens) + fast AR (codec codebooks), 10 codebooks × 4096 entries
- audio_codec: bundled 44.1 kHz neural codec (~21.5 frames/s)
- context: up to 2,048 packed text/audio positions
- variants: 0.1B (this), [0.6B](https://huggingface.co/Audio8/Audio8-TTS-Preview-0.6b)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 8
- license: Other

## Innovation

Packs practical zero-shot cloning into a ~170M-parameter model using an Falcon-H1-derived DualAR design (slow AR predicts semantic tokens per frame; fast AR predicts the frame's 10 codebooks conditioned on the slow hidden state). On Seed-TTS it posts EN WER 1.662 at only ~0.17B — within reach of 4B+ systems — and ships with its own 44.1 kHz codec so no external codec checkpoint is needed.
