---
release_date: "February 27, 2026"
model_name: "Blue (Light Blue) TTS"
category: "tts"
summary: "BlueTTS — MIT-licensed multilingual text-to-speech (Hebrew, English, Spanish, Italian, German) via ONNX Runtime; CPU-first with optional OpenVINO / CUDA / TensorRT execution providers."
slug: "blue-tts"
---

# Blue (Light Blue) TTS

BlueTTS (project page: lightbluetts.com) is a multilingual text-to-speech library. Built around slim ONNX graphs that run on **ONNX Runtime** with first-class CPU support and optional accelerators — **OpenVINO** (Intel), **CUDA ORT** (NVIDIA), **TensorRT**, and **ONNX Runtime** stock CPU. Targets five languages — **Hebrew, English, Spanish, Italian, German** — including inline mixed-language with XML-style tags in the text prompt. Inference is deliverable as a PyPI package (`blue-onnx`), a Rust crate, or directly from the pinned ONNX graphs on the HF Hub; the v2 release ships a slimmed opset-17 ONNX bundle (notmax123/blue-onnx-v2) that's intended for both FP32 production and the experimental INT8 weight-only fallback.

## Links

- GitHub: https://github.com/maxmelichov/BlueTTS
- HuggingFace: https://huggingface.co/notmax123/blue-onnx-v2
- PyPI: https://pypi.org/project/blue-onnx/
- Website: https://lightbluetts.com/
- Demo: https://huggingface.co/spaces/notmax123/BlueV2

## Features

- voice_cloning: yes (zero-shot voice style from a short reference JSON)
- asr: no
- pronunciation: yes (Hebrew G2P via renikud)
- emotion_control: no
- languages: Hebrew, English, Spanish, Italian, German
- streaming: no
- license: MIT
- runtime: ONNX Runtime (stock CPU; OpenVINO / CUDA / TensorRT optional)
- speed: "fastest open-source TTS" (per project description)
- graph_format: ONNX opset 17 (slim, full-precision; experimental weight-only INT8 fallback)
- distribution: PyPI + HuggingFace + Rust

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Hebrew, English, Spanish, Italian, German
- streaming: ❌
- license: MIT

## Innovation

A **CPU-first multilingual TTS** that ships both slimmed ONNX graphs and a Python package where the same code path runs on **stock CPU ONNX Runtime** by default — *and* optionally accelerates on OpenVINO / CUDA ORT / TensorRT — so deployment doesn't gate on GPU availability. Languages include **Hebrew** (with explicit G2P normalization) — a comparatively rare open-source TTS target — plus standard European languages, all from MIT-licensed weights distributed via both Hugging Face and PyPI.
