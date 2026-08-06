---
release_date: "June 22, 2026"
model_name: "Gepard"
category: "tts"
summary: "nineninesix.ai — prosody-aware autoregressive streaming TTS on Qwen3.5-14B (≈556M params total) with FSQ-codec single-pass frames, ~50 ms TTFA, and zero-shot voice cloning from a short reference clip."
slug: "gepard"
---

# Gepard

**GE**nerative, **P**rosody-aware, **A**utoregressive text-to-speech
model for **R**ealtime **D**ialogue. Gepard is built for low-latency,
high-throughput streaming conversation: the model starts speaking the
moment text begins arriving, generating audio piece by piece instead
of waiting for a full sentence. It is a single decoder-only
autoregressive language model built on Qwen3.5 (14 layers, hidden
1024, 8 heads) with ≈556M total parameters (backbone + audio
interface + voice-cloning compressor). Audio is produced through
NVIDIA NeMo NanoCodec — Finite Scalar Quantization at 22.05 kHz,
21.5 frames/s, 1.89 kbps — with the full 32-channel FSQ frame
sampled in one step. Reports ~25× real time on a single RTX 5090
with first-audio-chunk latency around 50 ms; a 96 GB Blackwell card
serves up to 256 concurrent conversations. CFG refinement is baked
into the weights so quality gain comes at no extra two-pass cost at
inference, though the two-pass mode is still selectable as a quality
dial.

## Links

- HuggingFace: https://huggingface.co/nineninesix/gepard-1.0
- Demo: https://huggingface.co/spaces/nineninesix/gepard
- Paper: https://huggingface.co/nineninesix/gepard-1.0/resolve/main/gepard_techreport.pdf
- Website: https://www.nineninesix.ai/

## Features

- parameters: ~556M (Qwen3.5-14 backbone + audio interface + voice-cloning compressor)
- voice_cloning: yes (short reference clip, up-front capture, no per-word cost)
- asr: no
- pronunciation: yes (autoregressive language model keeps content natural)
- emotion_control: no (prosody-aware, not controllably expressive)
- languages: English (US/UK), Spanish (es-MX), Portuguese (pt-BR), Dutch (NL)
- streaming: yes (TTFA ~50 ms, ~25× real time on RTX 5090)
- license: Research Only (CODEC NVIDIA Open Model License; Apache 2.0 for model weights)
- audio_codec: NVIDIA NeMo NanoCodec (FSQ, 22.05 kHz, 21.5 fps, 1.89 kbps)
- sample_rate: 22,050 Hz
- backbone: Qwen3.5 full-attention transformer (14 layers, hidden 1024, 8 heads; ~500M params)
- inference: vLLM
- throughput: 256 conversations on one 96 GB Blackwell (RTX Pro 6000) GPU

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English, Spanish, Portuguese, Dutch
- streaming: ✅
- license: Apache-2.0

## Innovation

A prosody-aware autoregressive single-pass frame generator: the whole
32-channel FSQ audio frame is sampled in one step (no depth transformer),
and CFG quality refinement is **baked into the weights** rather than
incurred at inference as a two-pass cost — so the publicly reported TTFA
of ~50 ms and 25× real time on a single RTX 5090 represent the
quality-on path, not a cheap-fast preview. Voice cloning is decoupled
into a separate up-front compressor, which means cloning is "free" at
run-time once the reference clip is encoded — a structural choice that
supports serving hundreds of conversations per GPU.
