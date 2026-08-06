---
release_date: "September 16, 2025"
model_name: "VibeVoice-Finetuning"
category: "tts"
summary: "voicepowered-ai — an unofficial WIP LoRA fine-tuning toolkit for VibeVoice (1.5B and 7B base): dual-loss training (masked CE on text tokens + diffusion MSE on acoustic latents) on 24 kHz audio datasets; targets ≥16 GB VRAM for 1.5B / ≥48 GB for 7B; tested on Transformers 4.51.3."
slug: "vibevoice-finetuning"
---

# VibeVoice-Finetuning

This is an **unofficial, work-in-progress LoRA fine-tuning toolkit**
for the VibeVoice TTS / speech model (1.5B-base and 7B-base
checkpoints). The base VibeVoice checkpoints are the same ones
covered in this list's
[a separate entry](#modelvibevoice-realtimemd): audio-conditioned
diffusion TTS for spoken dialogue, streaming, etc. This toolkit
takes **pretrained VibeVoice** weights + a paired (text, audio,
optional reference-audio) dataset and trains a **LoRA adapter**
against two losses simultaneously:

1. **Masked cross-entropy on text tokens** — the text-side of the
   LLM head still learns to autoregress over the transcription /
   prompt even when the diffusion head is being optimized.
2. **Diffusion MSE on acoustic latents** — the speech synthesis
   side is fine-tuned to predict the acoustic latents of the
   target waveform from text + (optional) voice prompt.

The dual-loss design preserves VibeVoice's text LLM capability
while specializing its acoustic generation to a new voice / accent
/ domain. Hardware requirements: at least **16 GB VRAM** for 1.5B
LoRA training; **at least 48 GB VRAM** for 7B LoRA training (longer
audios push those numbers up). Tested on Transformers 4.51.3
(other versions may break on the Qwen2 architecture); tested on
`runpod/pytorch:2.8.0-py3.11-cuda12.8.1-cudnn-devel-ubuntu22.04`.

## Links

- GitHub: https://github.com/voicepowered-ai/VibeVoice-finetuning

## Features

- parameters: 1.5B (LoRA-adapted) / 7B (LoRA-adapted)
- voice_cloning: no (this is a training toolkit; the base VibeVoice model itself supports cloning)
- asr: no (the toolkit trains TTS, not ASR)
- languages: inherits base VibeVoice coverage
- streaming: not directly (toolkit output is a LoRA adapter; the adapter inherits VibeVoice inference shape)
- license: MIT
- loss_text: masked cross-entropy on text tokens
- loss_acoustic: diffusion MSE on acoustic latents
- hardware_1_5b: ≥16 GB VRAM
- hardware_7b: ≥48 GB VRAM
- transformers_version: 4.51.3 (known-good; other versions may break on Qwen2 architecture)
- tested_docker_image: runpod/pytorch:2.8.0-py3.11-cuda12.8.1-cudnn-devel-ubuntu22.04
- audio_target_format: 24 kHz audio (paired dataset of target-audio + transcripts + optional reference-audio prompts)
- training_entrypoint: `python -m src.finetune_vibevoice_lora --model_name_or_path aoi-ot/VibeVoice-Large --processor_name_or_path src/vibevoice/processor --dataset_name <your/dataset> --text_column_name text [--voice_column_name audio_ref]`
- supports_hf_dataset_loader: yes
- output: LoRA adapter compatible with VibeVoice base

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: —
- streaming: ❌
- license: MIT

## Innovation

The dual-loss trick is the technical center of this toolkit. Naive
LoRA fine-tuning of a unified TTS model often specializes the
synthesis but **silently damages the text LLM capability** the
base inherited from its Qwen-class backbone; the
"masked CE on text tokens + diffusion MSE on acoustic latents"
two-headed loss preserves both competencies at training time. Pair
that with the careful pinning of Transformers 4.51.3 (other versions
break on the Qwen2 architecture) and a documented minimum-VRAM
budget per base size (16 GB for 1.5B, 48 GB for 7B), and you get a
reproducible recipe for **community fine-tuning of VibeVoice** —
something the official Microsoft VibeVoice release doesn't ship
out-of-the-box.
