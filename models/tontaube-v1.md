---
release_date: "August 26, 2026"
model_name: "TontaubeV1"
category: "tts"
summary: "TontaubeAI / craitech — ~2.87B multilingual TTS with a 4-stage Qwen3-derived codebook cascade (CB0–CB3), expressive zero-shot voice cloning, long-form generation, and low-latency streaming (~200 ms to first audio on RTX 5090)."
slug: "tontaube-v1"
---

# TontaubeV1

TontaubeV1 is a multilingual text-to-speech model from TontaubeAI (craitech) designed for expressive voice cloning, long-form generation, and low-latency streaming. Its release contains four causal codebook predictors: **CB0** generates semantic audio and duration from text, while progressively smaller **CB1–CB3** add acoustic detail. CB0 uses a Qwen3-1.7B-derived transformer trunk and CB1–CB3 progressively shallower Qwen3-0.6B-derived trunks, each with a two-layer audio-token head. The four output streams are decoded with DualCodec, and the inference path uses VibeVoice's acoustic encoder/decoder for continuous reconstruction and streaming. It ships bundled synthetic voices plus zero-shot cloning from up to 60 s of reference audio, with public speaking styles `audiobook`, `conversational`, and `agentic`. Released under the **Tontaube Community Model License 1.0**, which is explicitly not open-source.

## Links

- HuggingFace: https://huggingface.co/TontaubeAI/TontaubeV1
- GitHub: https://github.com/craitech/tontaube
- Demo: https://tontaube.ai/playground
- Paper: https://tontaube.ai/papers/tontaube-v1-technical-report.pdf

## Features

- voice_cloning: yes (bundled synthetic voices + zero-shot from 5–60 s reference)
- asr: no
- languages: 7 (English, German primary; Spanish, French, Italian, Dutch, Portuguese secondary)
- streaming: yes (~200 ms to first encoded audio on RTX 5090; low-latency MP3/Opus)
- license: Other
- parameters: ~2.87B (2,873,962,498; CB0 1.83B + CB1 449M + CB2 327M + CB3 269M)
- architecture: 4-stage Qwen3-derived codebook cascade (CB0–CB3) + DualCodec + VibeVoice decode
- styles: audiobook, conversational, agentic

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 7
- streaming: ✅
- license: Other

## Innovation

The four-stage codebook cascade (CB0 semantic+duration → CB1–CB3 progressive acoustic refinement) lets a single multilingual model deliver expressive, long-form, low-latency speech with strong zero-shot cloning. On the 1,088 English zero-shot Seed-TTS examples it posts 1.66% mean utterance-level WER (measured with Whisper large-v3 at semantic temperature 0.6), and the RTX-5090 streaming path reaches ~200 ms to first encoded audio.
