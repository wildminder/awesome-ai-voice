---
release_date: "November 8, 2025"
model_name: "PASE"
category: "restoration"
summary: "Cisco — Phonologically Anchored Speech Enhancer: low-hallucination generative speech enhancement using WavLM's phonological prior + dual-stream vocoder (phonetic + acoustic reconstruction)."
slug: "pase"
---

# PASE

PASE (Phonologically Anchored Speech Enhancer) is a generative speech-enhancement model from Cisco Collaboration AI that removes noise and reverberation while preserving linguistic content and speaker identity. It uses two fine-tuned WavLM-derived components:

- **Denoising WavLM (DeWavLM)** — WavLM-Large fine-tuned with denoising representation distillation (DRD); uses the phonological prior from self-supervised WavLM to suppress noise while mitigating linguistic hallucinations.
- **Dual-Stream Vocoder** — reconstructs audio from two streams of DeWavLM features: a phonetic stream (linguistic structure) and an acoustic stream (speaker identity + prosody).

Operates on 16 kHz mono. Accepted to AAAI 2026. A follow-up variant, **StuPASE** (studio-quality enhancement), was released and accepted to Interspeech 2026. Both live in the same repo.

## Links

- HuggingFace: https://huggingface.co/Xiaobin-Rong/pase
- GitHub: https://github.com/cisco-open/pase
- Demo: https://xiaobin-rong.github.io/pase_demo/
- Paper: https://arxiv.org/abs/2511.13300

## Features

- type: Speech Enhancement
- bandwidth_extension: no (16 kHz mono)
- inpainting: no
- sample_rate: 16 kHz mono
- architecture: Denoising WavLM (DRD from WavLM-Large) + Dual-Stream Vocoder (phonetic + acoustic)
- finetuned_from: WavLM-Large
- training_data: DN5/DNS5 challenge clean + noise, LibriTTS, VCTK, OpenSLR26+28 RIRs
- license: Apache-2.0

## Comparison

- type: Speech Enhancement
- bandwidth_extension: ❌
- inpainting: ❌
- license: Apache-2.0

## Innovation

Anchors enhancement to phonology instead of spectrum: by reconstructing from a **phonetic** stream and a separate **acoustic** stream (per DeWavLM's two representations), PASE keeps the words intact even when the spectrum is severely degraded — substantially lowering hallucinations while still regaining perceptual quality.
