---
release_date: "August 25, 2026"
model_name: "Sopro v2 Turbo"
category: "tts"
summary: "Haloneuro / samuel-vitorino — 120M open voice-cloning TTS that streams on a laptop CPU or in the browser via ONNX, reaching SOTA-level intelligibility against much larger systems at 0.21–0.24 RTF."
slug: "sopro-v2-turbo"
---

# Sopro v2 Turbo

Sopro (Portuguese for "breath") is a lightweight voice-cloning text-to-speech family. This repo ships **sopro-v2-turbo**, a 120M-parameter open model that streams and runs comfortably on a laptop CPU or in the browser (ONNX runtime), reaching SOTA-level intelligibility against much larger systems. It supports **zero-shot voice cloning** from 5–20 s of reference audio, four languages (English, European Portuguese, French, German), and a streaming path with ~300 ms time-to-first-audio on a laptop CPU (0.24 RTF offline / 0.21 RTF streaming on an M3 CPU, 0.07 RTF on H100). Released under Apache-2.0.

## Links

- HuggingFace: https://huggingface.co/samuel-vitorino/sopro-v2-turbo
- GitHub: https://github.com/samuel-vitorino/sopro
- Demo: https://samuel-vitorino.github.io/sopro/
- Blog: https://research.haloneuro.ai/posts/sopro-v2

## Features

- voice_cloning: yes (zero-shot, 5–20 s reference audio)
- asr: no
- languages: 4 (English, European Portuguese, French, German)
- streaming: yes (~300 ms TTFA on laptop CPU; 0.21 RTF streaming on M3, 0.07 RTF on H100)
- license: Apache-2.0
- parameters: 120M (121,574,193)
- deployment: in-browser ONNX runtime; int8 AR weights on CPU; causal vocoder
- architecture: autoregressive TTS + chunked-attention streaming path + causal vocoder (F5-TTS/CosyVoice/Vocos lineage acknowledged)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 4
- streaming: ✅
- license: Apache-2.0

## Innovation

Packs SOTA-level intelligibility into a 120M footprint that runs in the browser or on a laptop CPU, with a chunked-attention + causal-vocoder streaming path (~300 ms TTFA) — making zero-shot multilingual voice cloning practical for on-device and edge deployment rather than GPU-only serving.
