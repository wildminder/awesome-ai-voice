---
release_date: "October 20, 2026"
model_name: "Phonon 31m"
category: "tts"
summary: "English streaming TTS with 31M parameters and a Rust runtime for offline CPU, mobile and browser inference."
slug: "phonon-31m"
---

# Phonon 31m

Phonon 31m is Gradium's English text-to-speech model with Apache-2.0 weights. A flow-matching transformer predicts audio latents frame by frame, and a Mimi decoder produces mono 24 kHz speech. The Rust runtime runs offline after downloading the model and voice files, with Python, browser and mobile bindings and an OpenAI-compatible self-hosted server.

Custom voices can be cloned or designed in Gradium Studio and exported for local synthesis. Voice creation uses Gradium's service; the local runtime consumes the exported voice file.

## Links

- GitHub: https://github.com/gradium-ai/xn-ptts
- HuggingFace: https://huggingface.co/gradium/phonon-31m-en
- Demo: https://gradium.ai/phonon
- Release: https://gradium.ai/blog/release-phonon-open-weight

## Features

- parameters: 31M (excluding the audio tokenizer)
- architecture: flow-matching transformer and Mimi decoder
- asr: no
- languages: English
- streaming: yes
- audio_output: 24 kHz mono
- license: Apache-2.0 weights; MIT OR Apache-2.0 runtime
- voice_cloning: via Gradium Studio export, not local reference-audio encoding

## Comparison

- voice_cloning: via Gradium Studio
- asr: ❌
- languages: English
- streaming: ✅
- license: Apache-2.0
