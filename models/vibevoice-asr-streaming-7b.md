---
release_date: "September 2, 2026"
model_name: "VibeVoice-ASR-Streaming-7B"
category: "asr"
summary: "Microsoft — unified streaming ASR that transcribes Who (speaker) said What (content) with customized hotword boosting across 10 languages; 8.67B params, MIT."
slug: "vibevoice-asr-streaming-7b"
---

# VibeVoice-ASR-Streaming-7B

VibeVoice-ASR-Streaming is Microsoft's unified **streaming** speech-to-text model that transcribes **Who (Speaker)** said **What (Content)** continuously as speech arrives, with support for **customized hotwords** (names, technical terms) that improve recognition of domain-specific content. It covers 10 languages: Chinese, English, French, German, Italian, Japanese, Korean, Portuguese, Russian, and Spanish. The checkpoint weighs 8.67B parameters (BF16) and loads with transformers (`VibeVoiceForASRStreamingTraining`). A technical report is on arXiv (2609.02812). Released under the MIT License by Microsoft Research.

## Links

- HuggingFace: https://huggingface.co/microsoft/VibeVoice-ASR-Streaming-7B
- GitHub: https://github.com/microsoft/VibeVoice
- Demo: https://aka.ms/vibeasr
- arXiv: https://arxiv.org/abs/2609.02812

## Features

- languages: 10 (zh, en, fr, de, it, ja, ko, pt, ru, es)
- streaming: yes (continuous speaker-attributed transcription as speech arrives)
- license: MIT
- parameters: 8.67B (8,674,021,857 BF16)
- architecture: VibeVoice (transformers, VibeVoiceForASRStreamingTraining)
- highlights: speaker-attributed transcription; customized hotword boosting

## Comparison

- languages: 10
- streaming: ✅
- license: MIT

## Innovation

Unifies three streaming capabilities in one pass — speaker attribution ("who"), content transcription ("what"), and user-supplied hotword boosting for domain-specific vocabulary — instead of chaining diarization + ASR + post-correction, and does it continuously as audio arrives rather than in offline batches.
