---
release_date: "December 15, 2025"
model_name: "Fun-ASR"
category: "asr"
summary: "FunAudioLLM / Tongyi Lab — end-to-end LLM-ASR large model trained on tens of millions of hours; 31 languages, dialects, accents, lyrics, hotwords, timestamps, and speaker diarization."
slug: "fun-asr"
---

# Fun-ASR

Fun-ASR (Fun-ASR-Nano-2512) is an end-to-end speech recognition large model from Tongyi Lab / FunAudioLLM, trained on tens of millions of hours of real speech data. The Nano variant covers 31 languages including Chinese with multiple dialects (Wu, Cantonese, Min, Hakka, Gan, Xiang, Jin) and 26 regional accents plus English/Japanese, with optional lyric / rap recognition. vLLM-based batch inference is 3-5× faster than baseline, and a llama.cpp / GGUF runtime brings the model to CPU/edge with built-in VAD.

## Links

- HuggingFace: https://huggingface.co/FunAudioLLM/Fun-ASR-Nano-2512
- GitHub: https://github.com/FunAudioLLM/Fun-ASR

## Features

- parameters: 800M
- languages: 31
- streaming: yes (vLLM WebSocket real-time streaming SDK)
- vad: yes (built-in)
- punctuation: yes
- diarization: yes (added 2026/05)
- timestamps: yes
- hotwords: yes
- quant: GGUF (~484MB q-form)
- license: Apache-2.0

## Comparison

- languages: 31
- streaming: ✅
- license: Apache-2.0

## Innovation

Far-field, high-noise end-to-end ASR (conference rooms, in-vehicle, industrial) without the "hallucination" generation and language confusion common to Whisper-class models, plus a vLLM WebSocket streaming SDK that delivers sub-second transcription at scale and a llama.cpp / GGUF edge runtime.
