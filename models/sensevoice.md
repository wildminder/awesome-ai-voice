---
release_date: "July 3, 2024"
model_name: "SenseVoice"
category: "asr"
summary: "FunAudioLLM — non-autoregressive multilingual speech understanding (ASR + LID + emotion + audio event detection); 50+ languages with sub-100 ms inference."
slug: "sensevoice"
---

# SenseVoice

SenseVoice is a speech foundation model that combines automatic speech recognition (ASR), spoken-language identification (LID), speech-emotion recognition (SER), and audio-event detection (AED) in a single non-autoregressive architecture. The Small variant processes 10 s of audio in roughly 70 ms, runs CPU/edge via a llama.cpp-compatible GGUF runtime, and is trained on over 400 k hours of data spanning 50+ languages.

## Links

- HuggingFace: https://huggingface.co/FunAudioLLM/SenseVoiceSmall
- GitHub: https://github.com/FunAudioLLM/SenseVoice

## Features

- parameters: ~230M (SenseVoice-Small)
- languages: 50+ (multilingual)
- streaming: yes (real-time, low-latency inference)
- vad: yes (built-in via llama.cpp CPU runtime)
- punctuation: yes
- diarization: yes (added 2026/05)
- timestamps: yes
- emotion_recognition: yes
- audio_event_detection: yes
- license: Other

## Comparison

- languages: Multilingual
- streaming: ✅
- license: Other

## Innovation

A non-autoregressive end-to-end architecture that runs at 15× the speed of Whisper-Large while bundling ASR + LID + SER + AED in one model, plus a GGUF/llama.cpp path that brings the whole pipeline to CPU/edge devices without Python at runtime.
