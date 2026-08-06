---
release_date: "December 22, 2025"
model_name: "Soprano"
category: "tts"
summary: "ekwek — Soprano: an ultra-lightweight, on-device text-to-speech model with an 80M-parameter backbone; up to 20× real-time on CPU and 2000× real-time on GPU, lossless streaming with <250 ms CPU / <15 ms GPU latency, 32 kHz output, with OpenAI-compatible / ONNX / WebUI / CLI / ComfyUI inference surfaces."
slug: "soprano"
---

# Soprano

**Soprano** is an ultra-lightweight, on-device text-to-speech (TTS)
model designed for expressive, high-fidelity speech synthesis at
unprecedented speed. The 1.1 release ships an 80M-parameter
backbone that achieves up to **20× real-time generation on CPU**
and **2000× real-time on GPU**, with **lossless streaming**
(<250 ms latency on CPU, <15 ms on GPU), **<1 GB memory usage**
at inference, and **infinite generation length** (automatic text
splitting). Output sample rate is **32 kHz**, with widespread
device support (CUDA / CPU / MPS on Windows, Linux, and Mac).
Inference is production-ready through an OpenAI-compatible
endpoint, ONNX, WebUI, CLI, and ComfyUI nodes. The base 1.1 model
is `ekwek/Soprano-1.1-80M` on HuggingFace; a fine-tuning toolkit
(`soprano-factory`) was released January 13 2026 alongside the
1.1 weights — the 1.1 release reports **95% fewer hallucinations**
and a **63% preference rate** over 1.0 (Soprano-80M). A live demo
runs on `ekwek/Soprano-TTS` HF Space.

## Links

- HuggingFace: https://huggingface.co/ekwek/Soprano-1.1-80M
- GitHub: https://github.com/ekwek1/soprano
- Demo: https://huggingface.co/spaces/ekwek/Soprano-TTS

## Features

- parameters: 80M (Soprano-1.1-80M)
- voice_cloning: no (per-voice trained weights; soprano-factory enables custom finetuning)
- asr: no
- languages: English (US/UK family voices, per HF Space)
- streaming: yes (lossless; <250 ms CPU latency, <15 ms GPU latency)
- license: Apache-2.0
- sample_rate: 32,000 Hz
- inference_targets: OpenAI-compatible endpoint, ONNX, WebUI, CLI, ComfyUI
- performance_cpu: up to 20× real-time
- performance_gpu: up to 2000× real-time
- memory: <1 GB at inference
- text_length: infinite (automatic text splitting)
- devices: CUDA, CPU, MPS (Windows, Linux, Mac)
- training_toolkit: soprano-factory (https://github.com/ekwek1/soprano-factory)
- history_1_1: Soprano-1.1-80M released 2026-01-14 (95% fewer hallucinations; 63% preference over 1.0)
- history_1_0: Soprano-80M released 2025-12-22

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: English
- streaming: ✅
- license: Apache-2.0

## Innovation

The defining trade-off of this release is **extreme on-device
efficiency at sub-100M scale**: an 80M-parameter backbone hits
**<250 ms CPU latency** and **<15 ms GPU** for lossless streaming
while keeping inference within <1 GB of memory — well under the
multi-billion-parameter budget that newer conversational TTS
systems require. The release pairs the model with `soprano-factory`
(open-source training/fine-tuning toolkit) so users can build their
own voices on top of the same backbone, and one installation can
drive OpenAI-compatible / ONNX / WebUI / CLI / ComfyUI inference.
The 1.1 update is a measured iteration: 95% fewer hallucinations
and a 63% preference over 1.0 at the same parameter budget, so the
measurable quality jump ships with no added inference cost.
