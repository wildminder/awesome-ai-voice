---
release_date: "September 9, 2026"
model_name: "AuK-Flash"
category: "tts"
summary: "Tencent — distilled AuK variant for fast 4-step speech generation and editing; same unified instruction interface (zero-shot/instruct TTS, editing, enhancement, separation) at a fraction of the inference cost."
slug: "auk-flash"
---

# AuK-Flash

AuK-Flash is the **distilled variant of AuK**, Tencent's 1.5B foundation model for speech generation and editing, optimized for **fast 4-step inference**. It exposes the same natural-language instruction interface as the base model: zero-shot TTS (reference voice) and instruct TTS (voice description, no reference), content and lyric editing, pitch/speed/volume acoustic edits, emotion/timbre/de-accent/nonverbal/whisper paralinguistic edits, plus speech enhancement and speech/music/target-speaker separation. Architecture matches the base: diffusion transformer with layer-fusion weights, Qwen2.5-Omni-3B MLLM encoder, and a separate runtime-loaded VAE. Released under MIT.

## Links

- HuggingFace: https://huggingface.co/tencent/AuK-Flash
- GitHub: https://github.com/Tencent-Hunyuan/AuK
- arXiv: https://arxiv.org/abs/2609.08936
- Demo: https://huggingface.co/spaces/tencent/AuK

## Features

- voice_cloning: yes (zero-shot TTS from reference audio; instruct TTS from description alone)
- asr: no
- license: MIT
- parameters: 1.5B
- architecture: diffusion transformer + layer fusion (distilled to 4 inference steps), Qwen2.5-Omni-3B MLLM encoder, separate VAE
- base_model: tencent/AuK
- editing: content, lyric, pitch, speed, volume, emotion, timbre, de-accent, nonverbal, whisper conversion
- enhancement_separation: speech enhancement, speech separation, music separation, target speaker extraction
- deployment: SGLang-Omni, Gradio, ComfyUI

## Comparison

- voice_cloning: ✅
- asr: ❌
- license: MIT

## Innovation

Distills the AuK foundation model's diffusion transformer down to **4 inference steps**, making the full generate-and-edit capability set (including enhancement and separation) practical for interactive use — traded against the base model's maximum quality, with the two variants loadable side-by-side from the same codebase.
