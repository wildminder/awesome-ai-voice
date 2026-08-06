---
release_date: "May 19, 2026"
model_name: "Mega-ASR"
category: "asr"
summary: "Xie et al. (NTU / NUS / Shanghai AI Lab) — robust ASR targeting full-scenario in-the-wild acoustic conditions; Qwen3-ASR-1.7B base + Mega-ASR adapter + audio quality router, trained with A2S-SFT and DG-WGPO RL."
slug: "mega-asr"
---

# Mega-ASR

Mega-ASR is a robust ASR foundation model trained to withstand the full spectrum of real-world acoustic degradation: 7 atomic acoustic conditions (reverberation, echo, additive noise, far-field, frequency dropout, bandwidth limitation, clipping distortion) and 54 compound environmental scenarios built on top. The inference stack combines Qwen3-ASR-1.7B as backbone, Mega-ASR adaptation weights, and an audio-quality router that picks per-utterance between the robust Mega-ASR path and the base path to preserve clean-speech quality. Robustness is trained via A2S-SFT plus DG-WGPO reinforcement learning, with reported gains up to ~30 % over leading open- and closed-source SOTA models on adversarial acoustic samples.

## Links

- HuggingFace: https://huggingface.co/zhifeixie/Mega-ASR
- GitHub: https://github.com/xzf-thu/Mega-ASR
- Website: https://xzf-thu.github.io/Mega-ASR/
- Paper: https://arxiv.org/abs/2605.19833
- Demo: https://huggingface.co/spaces/zhifeixie/Mega-ASR

## Features

- parameters: 1.7B (Qwen3-ASR backbone) + Mega-ASR adapter + audio-quality router
- languages: English, Chinese
- streaming: no (greedy decoding, max_new_tokens=256 default)
- license: Apache-2.0
- architecture: Qwen3-ASR-1.7B base + adaptation weights + audio-quality router
- training_data: ~2.4M samples (Voices-in-the-Wild-2M)
- robustness_atoms: 7 (reverb, echo, additive noise, far-field, freq dropout, bandwidth limit, clipping)
- robustness_compound_scenarios: 54
- training: A2S-SFT + DG-WGPO RL
- base_model: Qwen/Qwen3-ASR-1.7B

## Comparison

- languages: English, Chinese
- streaming: ❌
- license: Apache-2.0

## Innovation

The first foundation ASR explicitly trained to handle **full-scenario in-the-wild** acoustic conditions (7 atomic effects, 54 compound scenarios, 2.4 M samples), combined with a routed inference path that switches between a robust Mega-ASR adapter and the base Qwen3-ASR backbone via an audio-quality classifier — delivering up to ~30 % WER gains over SOTA while staying fully open under Apache-2.0.
