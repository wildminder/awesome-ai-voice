---
release_date: "April 20, 2026"
model_name: "Omni2Sound (Omni2Audio)"
category: "a2a"
summary: "Omni2Sound team (CVPR 2026 Highlight) — unified video-and-text-to-audio generation with decoupled semantic and temporal branches; same model handles VT2A, V2A, and T2A."
slug: "omni2sound"
---

# Omni2Sound (Omni2Audio)

Omni2Sound — also written **Omni2Audio** on the project page — is a unified VT2A / V2A / T2A framework and a CVPR 2026 Highlight. A single Diffusion Transformer (DiT) backbone with a decoupled two-branch conditioning design:

- **Semantic branch ("What")**: fuses text embeddings from Flan-T5 and visual features from CLIP via cross-attention; for unimodal tasks (V2A or T2A) the missing modality is simply omitted.
- **Temporal branch ("When")**: Synchformer extracts fine-grained visual-temporal features injected globally via Adaptive Layer Normalization for tight audio-visual sync.

Trained progressively: (1) large-scale T2A pretraining → (2) multi-task interleaved finetuning on SoundAtlas → (3) decoupled robustness finetuning with off-screen synthesis + text dropout augmentations. Surpasses both prior unified models (AudioX, MMAudio) and task-specific models (ThinkSound, HunyuanVideo-Foley) on VGGSound-Omni.

## Links

- HuggingFace: https://huggingface.co/Dalision/Omni2Sound
- GitHub: https://github.com/omni2sound/Omni2Sound
- Website: https://omni2sound.github.io/
- Paper: https://arxiv.org/abs/2601.02731
- Benchmark: https://huggingface.co/datasets/Dalision/Omni2Sound_Benchmark

## Features

- conditioning: Text / Video / Text+Video
- modalities: Video, Audio
- asr: no
- voice_cloning: no
- text: yes
- video: yes
- image: no (image not a direct modality — visual is via CLIP)
- audio: yes (output modality)
- license: CC BY-NC 4.0
- tasks: VT2A, V2A, T2A (single model)
- architecture: DiT + decoupled Semantic / Temporal branches + 3-stage progressive training
- pipeline_tag: text-to-audio

## Comparison

- text: ✅
- video: ✅
- audio: ✅
- license: CC BY-NC 4.0

## Innovation

One **single model** that is SOTA on three distinct tasks (VT2A, V2A, T2A) without a separate model per mode — decoupled semantic and temporal conditioning let the same DiT backbone handle text-only, video-only, and text+video conditioning by cleanly omitting the missing modality rather than padding it, which is what most prior unified VA models had to do.
