---
release_date: "August 12, 2026"
model_name: "MiDashengLM-Gen"
category: "a2a"
summary: "Xiaomi — end-to-end unified audio-scene generation that blends speech, music, SFX and ambience from structured text captions, using a Qwen3-1.7B LLM backbone coupled with per-token conditional flow matching."
slug: "midashenglm-gen"
---

# MiDashengLM-Gen

MiDashengLM-Gen (MiDasheng Language Model for Generation) is an end-to-end framework for unified audio-scene generation from Xiaomi. Built on a pre-trained LLM and the Dasheng audio tokenizer, it couples per-token conditional flow matching with autoregressive generation to produce coherent 16 kHz audio that simultaneously blends speech, music, sound effects and environmental acoustics from a structured text description. It supports 9 languages with emotion control and approaches dedicated TTS intelligibility on speech (Seed-TTS English WER drops from 12.15% to 2.79%) while retaining mixed-audio scene capability, and extends competitively to multilingual settings.

## Links

- Demo: https://xingws.github.io/midashenglm-gen-demo/
- HuggingFace: https://huggingface.co/mispeech/midashenglm-gen
- GitHub: https://github.com/xiaomi-research/midashenglm-gen
- arXiv: https://arxiv.org/abs/2608.11804

## Features

- text: yes (structured multi-view text captions)
- video: no
- image: no
- audio: no
- sample_rate: 16 kHz
- languages: 9
- emotion_control: yes
- license: Apache-2.0
- parameters: 1.7B (Qwen3-1.7B backbone)
- architecture: DashengTokenizer (768-dim @25Hz) + Qwen3-1.7B + flow-matching DiT (16 layers, hidden 2048)

## Comparison

- text: ✅
- video: ❌
- audio: ❌
- sample_rate: 16 kHz
- license: Apache-2.0

## Innovation

LLM-conditioned high-dimensional (768-dim @25Hz) audio latents generated without quantization artifacts; audio-text alignment pre-training maps latents into the LLM token space before generation; a learned stop head enables variable-length truncation. First end-to-end trained model for general text-to-audio-scene generation.
