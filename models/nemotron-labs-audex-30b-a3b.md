---
release_date: "July 6, 2026"
model_name: "Nemotron-Labs-Audex-30B-A3B"
category: "a2a"
summary: "NVIDIA — unified audio-text LLM (30B MoE / 3B active) with broad audio I/O (audio understanding, ASR, speech translation, TTS, audio generation, speech-to-speech), built on Nemotron-Cascade-2-30B-A3B."
slug: "nemotron-labs-audex-30b-a3b"
---

# Nemotron-Labs-Audex-30B-A3B

Nemotron-Labs-Audex-30B-A3B is NVIDIA's unified audio-text LLM — a single model that both **understands** audio (audio QA, speech recognition, speech translation) and **generates** audio (text-to-speech, text-to-audio, speech-to-speech). Built on Nemotron-Cascade-2-30B-A3B (text-only MoE: 30B parameters, 3B active), Audex extends the vocabulary with **discrete audio tokens** for speech / general-audio output and adds an **audio encoder** for speech / general-audio input. Runs in *thinking* and *instruct* (non-thinking) modes and supports up to a 1M-token context length — preserving text-reasoning, alignment, knowledge, long-context, and agentic capabilities of the backbone while gaining audio tasks.

## Links

- HuggingFace: https://huggingface.co/nvidia/Nemotron-Labs-Audex-30B-A3B
- Paper: https://arxiv.org/abs/2607.05196
- Collection: https://huggingface.co/collections/nvidia/nemotron-labs-audex

## Features

- parameters: 30B MoE (3B active)
- modalities: audio (input and output)
- audio_understanding: yes
- asr: yes (speech recognition)
- speech_translation: yes
- text_to_speech: yes
- text_to_audio: yes
- speech_to_speech_generation: yes
- voice_cloning: no
- license: NVIDIA NC (NVIDIA OneWay NonCommercial License)
- languages: English
- modes: thinking, instruct (non-thinking)
- context_length: 1M tokens
- template: ChatML (with `<think>…</think>` for thinking mode)
- inference: vLLM 0.20.0 (recommended) or transformers >= 4.53.0 (mamba-ssm + causal-conv1d required)

## Comparison

- text: ✅
- video: ❌
- audio: ✅
- license: NVIDIA OneWay NonCommercial License

## Innovation

First-class audio I/O for a 30B/3B-active text LLM: extended vocabulary with **discrete audio tokens** for outputting speech and general audio, plus an **audio encoder** for input — so the same backbone keeps its strong text reasoning (alignment, knowledge, long-context) and adds ASR + speech translation + TTS + audio generation + S2S without retraining. The MoE form (30B routes, 3B active) keeps inference tractable for a single pipeline that does both.
