---
release_date: "February 11, 2026"
model_name: "Ming-omni-tts"
category: "tts"
summary: "InclusionAI / Ant Ling — unified TTS with fine-grained vocal control, dialect-specific generation, voice design, and single-channel speech + ambience + music synthesis."
slug: "ming-omni-tts"
---

# Ming-omni-tts

Ming-omni-tts is a high-performance unified audio generation model in the Ming 2.0 series. It uses a custom 12.5 Hz continuous tokenizer and a Patch-by-Patch compression strategy that drives the LLM inference frame rate down to 3.1 Hz, enabling fine-grained control over speech rate, pitch, volume, emotion, and dialect (notably Cantonese at ~93 % accuracy). It supports 100+ premium built-in voices plus zero-shot voice design from natural-language prompts and is the first autoregressive model that jointly generates speech, ambient sound, and music in a single channel.

## Links

- HuggingFace: https://huggingface.co/inclusionAI/Ming-omni-tts-16.8B-A3B
- GitHub: https://github.com/inclusionAI/Ming-omni-tts
- Website: https://xqacmer.github.io/Ming-omni-tts/

## Features

- parameters: 16.8B (3B active, MoE; A3B)
- voice_cloning: yes (zero-shot)
- asr: no
- emotion_control: yes (command-driven, 76.7% on emotional sets)
- languages: Chinese, English, Cantonese
- streaming: no
- license: Apache-2.0

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Chinese, English
- streaming: ❌
- license: Apache-2.0

## Innovation

Patch-by-Patch compression drives the inference frame rate to 3.1 Hz, drastically cutting LLM-side latency for podcast-style audio while preserving naturalness. A custom 12.5 Hz continuous tokenizer plus a DiT head jointly produce speech, ambient sound, and music in a single output channel — an "in-the-scene" listening experience rather than TTS-on-top-of-a-track.
