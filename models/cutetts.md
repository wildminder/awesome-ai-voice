---
release_date: "August 24, 2026"
model_name: "CuteTTS"
category: "tts"
summary: "OPPO — lightweight ~230M continuous-autoregressive TTS with zero-shot voice cloning across 5 languages; ~40 ms first-chunk latency and ~9× real-time on RTX 4090, efficient on GPU/CPU/Apple silicon."
slug: "cutetts"
---

# CuteTTS

CuteTTS is a lightweight (~230M-parameter) **continuous autoregressive** TTS model from OPPO that models continuous latents rather than discrete codec tokens, running efficiently on GPUs, CPUs, and Apple silicon. It delivers ultra-low latency — ~40 ms to the first audio chunk and ~9× real-time throughput on an RTX 4090 — with strong speech quality and zero-shot voice cloning (best-in-comparison 78.9 SIM on LibriSpeech test-clean). Multilingual support covers English, Chinese, French, German, and Spanish. A distilled variant (`CuteTTS-distill`) trades slight quality for further efficiency. Ships with a web demo, Python API, and CLI.

## Links

- HuggingFace: https://huggingface.co/OPPOer/CuteTTS
- GitHub: https://github.com/OPPO-Mente-Lab/CuteTTS
- arXiv: https://arxiv.org/abs/2608.08638

## Features

- voice_cloning: yes (zero-shot; 78.9 SIM on LibriSpeech test-clean)
- asr: no
- languages: 5 (English, Chinese, French, German, Spanish)
- streaming: yes (~40 ms to first audio chunk, ~9× real time on RTX 4090)
- license: Apache-2.0
- parameters: ~230M
- architecture: continuous autoregressive modeling of latents + speaker encoder + audio VAE (discrete-codec-free design)
- variants: CuteTTS, CuteTTS-distill

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 5
- streaming: ✅
- license: Apache-2.0

## Innovation

Autoregressively models *continuous* latent audio representations instead of discrete codec tokens, eliminating codebook-related artifacts and quantization loss at only ~230M parameters. Combined with a lightweight speaker encoder and audio VAE, this yields best-of-class speaker similarity among compared open models and ~40 ms first-chunk latency while remaining practical for CPU/Apple-silicon inference.
