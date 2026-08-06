---
release_date: "2025 (ICLR 2026)"
model_name: "PrismAudio"
category: "a2a"
summary: "Video-to-Audio generation framework with Reinforcement Learning and specialized Chain-of-Thought (CoT) planning."
slug: "prismaudio"
---

# PrismAudio

Video-to-Audio generation framework with Reinforcement Learning and specialized Chain-of-Thought (CoT) planning. Decomposes reasoning into four specialized modules (Semantic, Temporal, Aesthetic, Spatial CoT) for comprehensive video understanding. Built upon ThinkSound.

## Links

- GitHub: https://github.com/FunAudioLLM/ThinkSound/tree/prismaudio
- HuggingFace: https://huggingface.co/FunAudioLLM/PrismAudio
- Demo: https://huggingface.co/spaces/FunAudioLLM/PrismAudio
- arXiv: https://arxiv.org/abs/2511.18833

## Features

- parameters: 518M
- video: yes
- license: Apache-2.0
- cot-planning: yes (4 modules)
- multi-dimensional-rl: yes
- fast-grpo: yes (Hybrid ODE-SDE)
- inference-time: 0.63 seconds

## Comparison

- video: ✅
- license: Apache-2.0

## Innovation

**Performance Benchmarks:**

| Metric | VGGSound | AudioCanvas |
|--------|----------|-------------|
| Semantic (CLAP) | 0.47 | 0.52 |
| Temporal (DeSync↓) | 0.41 | 0.36 |
| Aesthetic (MOS-Q) | 4.21±0.35 | 4.12±0.28 |
