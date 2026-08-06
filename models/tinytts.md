---
release_date: "2026"
model_name: "TinyTTS"
category: "tts"
summary: "The smallest English TTS model with only 1.6 million parameters."
slug: "tinytts"
---

# TinyTTS

The smallest English TTS model with only 1.6 million parameters. End-to-end neural network achieving ~53x real-time synthesis speed on CPU via ONNX optimization.

## Links

- GitHub: https://github.com/tronghieuit/tiny-tts
- HuggingFace: https://huggingface.co/backtracking/tiny-tts
- Demo: https://huggingface.co/spaces/backtracking/tiny-tts-demo

## Features

- parameters: ~3.4 MB (ONNX FP16)
- voice_cloning: no
- asr: no
- pronunciation: yes
- emotion_control: no
- languages: English
- streaming: yes (~53x RTF)
- license: Apache-2.0

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: English
- streaming: ✅
- license: Apache-2.0

## Innovation

Ultra-compact architecture optimized for CPU-only deployment. Multi-platform support via Python and Node.js APIs. Works on laptops, edge devices, and embedded systems.
