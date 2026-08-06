---
release_date: "March 2026"
model_name: "Cohere Transcribe"
category: "asr"
summary: "Open-source automatic speech recognition (ASR) model developed by Cohere."
slug: "cohere-transcribe"
---

# Cohere Transcribe

Open-source automatic speech recognition (ASR) model developed by Cohere. A 2 billion parameter dedicated audio-in, text-out model that ranks #1 on the English ASR leaderboard.

## Links

- HuggingFace: https://huggingface.co/CohereLabs/cohere-transcribe-03-2026
- Demo: https://huggingface.co/spaces/CohereLabs/cohere-transcribe-03-2026
- Blog: https://cohere.com/blog/transcribe

## Features

- parameters: 2B
- architecture: Conformer-based encoder-decoder
- asr: yes
- languages: 14 (En, Fr, De, It, Es, Pt, Gr, Nl, Pl, Zh, Jp, Ko, Vi, Ar)
- streaming: yes
- license: Apache-2.0
- rtfx: Up to 3x faster than comparable models

## Comparison

- languages: 14
- streaming: ✅
- license: Apache-2.0

## Innovation

- Long-form transcription with automatic chunking (>35 seconds)
- Optional punctuation control
- Batched inference support
- vLLM integration for production serving
- Apple Silicon support via mlx-audio
- WebGPU browser deployment via transformers.js
