---
release_date: "September 9, 2026"
model_name: "AuK"
category: "tts"
summary: "Tencent — 1.5B open-source foundation model unifying speech generation and editing under natural-language instructions: zero-shot/instruct TTS, content/acoustic/paralinguistic editing, speech enhancement, and source separation."
slug: "auk"
---

# AuK

AuK is a 1.5B foundation model from Tencent for speech generation and editing, trained on millions of hours of diverse audio data. Through a single natural-language instruction interface it unifies an unusually broad task set: **zero-shot TTS** (speak text in the reference voice) and **instruct TTS** (voice from a description alone, no reference), **content editing** (rewrite what is said; even lyric editing that preserves melody and voice), **acoustic editing** (pitch by semitones, speed, volume), **paralinguistic editing** (emotion, timbre, de-accent, nonverbal sounds, whisper conversion), and **enhancement & separation** (denoise/dereverberate, speech separation, music/vocal separation, target-speaker extraction). Architecture: a diffusion transformer with layer-fusion weights, conditioned by a Qwen2.5-Omni-3B MLLM encoder and a separate VAE (loaded at runtime). Day-0 SGLang-Omni serving support, Gradio and ComfyUI integrations, and a task Cookbook are provided. Released under MIT.

## Links

- HuggingFace: https://huggingface.co/tencent/AuK
- GitHub: https://github.com/Tencent-Hunyuan/AuK
- arXiv: https://arxiv.org/abs/2609.08936
- Demo: https://huggingface.co/spaces/tencent/AuK

## Features

- voice_cloning: yes (zero-shot TTS from reference audio; instruct TTS from description alone)
- asr: no
- license: MIT
- parameters: 1.5B
- architecture: diffusion transformer + layer fusion, Qwen2.5-Omni-3B MLLM encoder, separate VAE
- variants: AuK (this, base) + [AuK-Flash](https://huggingface.co/tencent/AuK-Flash) (distilled, 4-step inference)
- editing: content, lyric, pitch, speed, volume, emotion, timbre, de-accent, nonverbal, whisper conversion
- enhancement_separation: speech enhancement, speech separation, music separation, target speaker extraction
- deployment: SGLang-Omni (day-0), Gradio, ComfyUI

## Comparison

- voice_cloning: ✅
- asr: ❌
- license: MIT

## Innovation

Unifies generation *and* the full editing/enhancement/separation spectrum in one instruction-following model — most systems pick one lane (TTS, or editing, or separation); AuK does zero-shot + instruct TTS, lyric rewriting with melody preservation, emotion/timbre/de-accent/whisper paralinguistic edits, and source separation through the same natural-language interface. A diffusion transformer with layer fusion, distilled into a 4-step AuK-Flash variant for fast inference.

## Additional Tools

| Tool | Type | Link |
|------|------|------|
| ComfyUI-AuK | ComfyUI node | https://github.com/Saganaki22/ComfyUI-AuK |
