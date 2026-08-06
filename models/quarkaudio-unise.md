---
release_date: "December 22, 2025"
model_name: "QuarkAudio-UniSE"
category: "restoration"
summary: "Alibaba — unified, prompt-free decoder-only autoregressive LM-based speech enhancement: denoising, target-speaker extraction, separation, and packet-loss in a single model that infers the task from input context."
slug: "quarkaudio-unise"
---

# QuarkAudio-UniSE

**UniSE** is a unified, prompt-free autoregressive speech-enhancement
framework built on a decoder-only language model. A single model
performs multiple speech-enhancement tasks — speech restoration (SR /
denoising), target-speaker extraction (TSE), source separation (SS),
and acoustic echo cancellation (AEC, in development) — without
explicit task-specific instructions or prompt conditioning; the
language model infers the task from the input context. Stack: WavLM
as the feature extractor, BiCodec as the discrete codec, and a
decoder-only LM as the middle autoregressive backbone. Outputs
reconstructed waveform from predicted discrete token sequences.

## Links

- HuggingFace: https://huggingface.co/QuarkAudio/QuarkAudio-UniSE
- GitHub: https://github.com/alibaba/unified-audio/tree/main/QuarkAudio-UniSE
- Paper: https://arxiv.org/abs/2510.20441

## Features

- voice_cloning: no
- asr: no
- streaming: no (autoregressive, non-streaming)
- languages: English (paper demo)
- license: Apache-2.0
- tasks: Speech Restoration, Target Speaker Extraction, Source Separation, AEC (developing)
- architecture: WavLM (feature extractor) + BiCodec (discrete codec) + decoder-only AR-LM
- unified: yes (single model handles SE, SR, TSE, SS without explicit task prompts)
- prompt_free: yes (LM infers task from input context)
- dataset_signals: noise + reverb + packet-loss + clean (configurable per task)
- training: Speech-enhancement SFT, then multitask joint training

## Comparison

- type: Universal Speech Enhancement
- bandwidth_extension: ❌
- inpainting: ❌
- license: Apache-2.0

## Innovation

A single decoder-only LM that learns the speech-enhancement task
distribution and **infers which task to perform from the input
context** — eliminating the need for task-specific prompts, modules,
or fine-tuning when switching between denoising, target-speaker
extraction, and separation. Built as an autoregressive discrete-token
predictor over a WavLM-extracted / BiCodec-quantised representation,
it moves the speech-enhancement workflow from a zoo of specialist
models into one generalist.
