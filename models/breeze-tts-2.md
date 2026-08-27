---
release_date: "August 25, 2026"
model_name: "Breeze TTS 2"
category: "tts"
summary: "BreezeBlue / RESONIA — 3B open-weight real-time TTS ranked #1 among open-weight models on the Artificial Analysis TTS leaderboard; natural-language instruction-following voice design and voice direction, ~3.1× real-time streaming on H100."
slug: "breeze-tts-2"
---

# Breeze TTS 2

Breeze TTS 2 is an open-weight text-to-speech model from BreezeBlue / RESONIA built for real-time interaction. It ranks #1 among open-weight models on the Artificial Analysis TTS leaderboard while outperforming frontier proprietary systems. Its open-ended natural-language instruction-following supports **reference-free voice design** (create a voice from a text description) and **reference-guided voice direction** (clone a voice while steering tone, emotion, pace, delivery), alongside standard reference-audio voice cloning. Ultra-low-latency streaming reaches 0.32 RTF (≈3.1× real time with the warmed-up fast path) and under 40 ms time-to-first-audio on an NVIDIA H100, emitting 24 kHz PCM. Source code is Apache-2.0; model weights are governed by the BreezeBlue Research and Non-Commercial License (commercial use needs written authorization from RESONIA).

## Links

- HuggingFace: https://huggingface.co/BreezeBlue/Breeze-TTS-2
- GitHub: https://github.com/breezeblue-ai/breeze-tts
- Blog: https://breezeblue.ai/breeze-tts-2
- Demo: https://huggingface.co/spaces/BreezeBlue/breeze-tts-2-demo

## Features

- voice_cloning: yes (voice clone + reference-free voice design + voice direction)
- asr: no
- languages: 2 (English, Chinese)
- streaming: yes (<40 ms TTFA, ~3.1× real time / 0.32 RTF on H100, 24 kHz PCM)
- license: Other
- parameters: 3B (3,466,363,713)
- architecture: seq2seq backbone + depth decoder + codec with CUDA-graph fast path (no named backbone disclosed)
- highlights: #1 open-weight on Artificial Analysis TTS leaderboard; vocal events inline (laugh/cough)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 2
- streaming: ✅
- license: Other

## Innovation

Pairs natural-language voice control with real-time streaming: a single model handles reference-free **voice design** (no reference audio needed) and **voice direction** (clone + steer prosody), and ships a CUDA-graph fast path that hits sub-40 ms TTFA at ~3.1× real time on H100 — open-weight quality that the authors claim exceeds frontier proprietary TTS.

## Additional Tools

| Tool | Type | Link |
|------|------|------|
| ComfyUI-Breeze-TTS-2 | ComfyUI node | https://github.com/Saganaki22/ComfyUI-Breeze-TTS-2 |
