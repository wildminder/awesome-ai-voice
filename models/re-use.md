---
release_date: "March 17, 2026"
model_name: "RE-USE"
category: "restoration"
summary: "NVIDIA — Multilingual Universal Speech Enhancement (Mamba-SSM backbone) robust to noise, reverberation, clipping, bandwidth limitation, codec artifacts, packet loss, low-quality mics; supports 8/16/22.05/24/32/44.1/48 kHz input sampling rates; language-agnostic."
slug: "re-use"
---

# RE-USE

RE-USE (RE-…), NVIDIA's multilingual universal speech enhancement model, targets distortion–perception trade-off by training a single model that balances listening quality against fidelity to the underlying linguistic / speaker / emotional content. Designed to restore diverse degraded speech while leaving everything else (content, identity, prosody, accent, paralinguistic attributes) intact.

Robust to a broad menu of degradations: additive noise, reverberation, clipping, bandwidth limitation, codec artifacts, packet loss, and low-quality microphones. Backend is Mamba (Mamba-SSM) for efficient long-sequence inference, and the model is genuinely **language-agnostic** — it works across many languages, not just one. Operates on 7 input sample rates (8, 16, 22.05, 24, 32, 44.1, 48 kHz) with optional bandwidth extension enabled per call.

## Links

- HuggingFace: https://huggingface.co/nvidia/RE-USE
- GitHub: https://github.com/NVIDIA/diffusion-audio-restoration
- Demo: https://huggingface.co/spaces/nvidia/RE-USE
- Paper: https://arxiv.org/abs/2603.02641

## Features

- type: Universal Speech Enhancement
- bandwidth_extension: yes (optional BWE per inference call)
- inpainting: no
- sample_rate: 8 / 16 / 22.05 / 24 / 32 / 44.1 / 48 kHz (multi-rate input)
- architecture: Mamba-SSM backbone
- degradation_coverage: additive noise, reverberation, clipping, bandwidth limit, codec artifacts, packet loss, low-quality mics
- language_agnostic: yes
- license: NVIDIA NC (NVIDIA OneWay NonCommercial License)

## Comparison

- type: Universal Speech Enhancement
- bandwidth_extension: ✅
- inpainting: ❌
- license: NVIDIA OneWay NonCommercial License

## Innovation

A **single Mamba-SSM model** that handles seven different input sample rates (no resampling pre-step), covers a broad degradation menu in one checkpoint, stays language-agnostic without per-language training, and explicitly balances distortion reduction against fidelity to the input speech — addressing the universal-SE trade-off that earlier single-purpose enhancers couldn't.
