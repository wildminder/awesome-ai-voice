---
release_date: "April 13, 2026"
model_name: "ControlFoley"
category: "a2a"
summary: "Xiaomi MiLM Plus — controllable video-to-audio (foley) generation across four conditioning modes (T2A, V2A, TV2A, AC-V2A) at 44.1 kHz; resolves cross-modal conflict by separating text semantics, reference-audio timbre, and video-driven temporal structure."
slug: "controlfoley"
---

# ControlFoley

**ControlFoley** (Xiaomi MiLM Plus) is a unified controllable
video-to-audio (foley) generation model. It supports four
conditioning combinations under one architecture:

- **T2A** — text-to-audio
- **V2A** — video-to-audio
- **TV2A / TC-V2A** — text-controlled video-to-audio
- **AC-V2A** — reference-audio-controlled video-to-audio (the
  prompt audio drives timbre and acoustic style)

It targets the **cross-modal conflict** problem — when the visual
content, the text prompt, and any reference audio disagree
(visually obvious, textually wrong). Rather than adding an explicit
inference-time routing module, ControlFoley separates control by
modality within a single unified framework:

- **Text** guides the **semantic content** of generated audio.
- **Reference audio** guides **timbre and acoustic style**.
- **Video** preserves **temporal structure and synchronization**.

This separation is enabled by joint visual encoding, temporal / timbre
decoupling for reference-audio control, unified multimodal
representation alignment, and modality-robust training with
all-modality dropout. The output is generated at **44.1 kHz**;
inference runs on `diffusers`. Project page, code, online inference
inference skill, paper, and a separate qualitative-comparison
demo page are linked below.

## Links

- HuggingFace: https://huggingface.co/YJX-Xiaomi/ControlFoley
- GitHub: https://github.com/xiaomi-research/controlfoley
- Demo: https://yjx-research.github.io/ControlFoley/
- Website: https://yjx-research.github.io/ControlFoley_web_page/
- arXiv: https://arxiv.org/abs/2604.15086
- Skill: https://clawhub.ai/yjx-research/controlfoley-audio-generator

## Features

- conditioning: Text / Video / Text + Video / Video + Reference Audio
- modalities: Video (visual), Audio (foley)
- asr: no
- voice_cloning: no
- text: yes (drives audio semantics)
- video: yes (drives temporal structure and synchronization)
- image: no
- audio: yes (reference-audio mode drives timbre and acoustic style)
- sample_rate: 44,100 Hz
- license: CC BY-NC 4.0
- pipeline_tag: text-to-audio
- library: diffusers
- cross_modal_conflict: handled via modality-specific control (no explicit router)
- inference_skill: ClawHub ControlFoley Audio Generator
- upcoming: ComfyUI nodes (in preparation, expanding to V2A / TV2A / TC-V2A / AC-V2A / T2A)

## Comparison

- text: ✅
- video: ✅
- audio: ✅
- license: CC BY-NC 4.0

## Innovation

**Modality-specific cross-modal conflict resolution** in a single
generative stack: text governs semantics, reference audio governs
timbre/acoustic style, and video governs temporal synchronization.
Rather than routing to a single user-trusted modality, the model
**decouples control axes** so an input disagreement (video shows a
dog barking, text asks for a cat) is decomposed into a coherent
output that respects each modality's responsibility. Trained with
all-modality dropout for modality-robustness, ControlFoley is the
first foley system that brings all four conditioning modes — T2A,
V2A, TV2A, AC-V2A — under one model.
