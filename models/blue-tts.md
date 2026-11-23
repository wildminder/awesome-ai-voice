---
release_date: "November 18, 2026"
model_name: "BlueTTS (BlueV3)"
category: "tts"
summary: "BlueV3 — MIT-licensed multilingual text-to-speech (Hebrew, English, German, Spanish, Italian, Russian, Yiddish) via ONNX Runtime; CPU-first, 44.1 kHz, zero-shot voice cloning from a short reference clip, streaming."
slug: "blue-tts"
---

# BlueTTS (BlueV3)

BlueTTS is a multilingual, Hebrew-first text-to-speech library. **BlueV3** (v3.0.1) is a new flow-matching checkpoint that replaces the v2 release, with more natural and expressive speech and much better voice cloning. It runs as slim ONNX graphs on **ONNX Runtime**, CPU by default, with optional **CUDA**, **OpenVINO** and **TensorRT** paths. It outputs **44.1 kHz** audio in seven languages: **Hebrew, English, German, Spanish, Italian, Russian and Yiddish**. Languages can be mixed inline with XML-style tags, e.g. `<en>…</en>` inside Hebrew text. Hebrew is read without niqqud through the RenikudPlus G2P. A voice is cloned zero-shot from a 3–10 s reference clip, or picked from 15 built-in voices. `stream()` yields audio chunk by chunk, and the repo ships an OpenAI-compatible server (`/v1/audio/speech`) plus the training code.

## Links

- GitHub: https://github.com/maxmelichov/BlueTTS
- HuggingFace: https://huggingface.co/notmax123/BlueV3-onnx
- HuggingFace (PyTorch): https://huggingface.co/notmax123/BlueV3
- Website: https://bluetts.com
- Demo: https://huggingface.co/spaces/notmax123/BlueV3

## Features

- voice_cloning: yes (zero-shot from a 3–10 s reference clip; 15 built-in voices)
- asr: no
- pronunciation: yes (Hebrew G2P via RenikudPlus, no niqqud needed; polyg2p for the European languages)
- emotion_control: no
- languages: Hebrew, English, German, Spanish, Italian, Russian, Yiddish
- streaming: yes (`stream()`; OpenAI-compatible server with chunked audio / SSE)
- license: MIT
- runtime: ONNX Runtime (CPU default; CUDA / OpenVINO / TensorRT optional)
- sample_rate: 44.1 kHz
- serving: OpenAI-compatible `/v1/audio/speech` server included
- training: training code for all three stages included

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Hebrew, English, German, Spanish, Italian, Russian, Yiddish
- streaming: ✅
- license: MIT

## Innovation

A **CPU-first multilingual TTS** with MIT-licensed code and weights. The same ONNX code path runs on stock CPU ONNX Runtime and optionally on CUDA, OpenVINO or TensorRT, so you don't need a GPU to deploy it. It's one of the few open TTS models that target **Hebrew** and **Yiddish** natively, alongside five European languages, with code-switching inside a single prompt.
