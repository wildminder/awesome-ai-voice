---
release_date: "October 12, 2024"
model_name: "ZipEnhancer"
category: "restoration"
summary: "Alibaba (DAMO Academy / iic) — ZipEnhancer speech_zipenhancer_ans_multiloss_16k_base: next-generation single-channel speech intelligent denoising; reduces or fully removes noise from any acoustic environment, improves audio quality of any source, extracts vocals from any background; 16 kHz input → 16 kHz denoised output; dual-path architecture."
slug: "zipenhancer"
---

# ZipEnhancer

**ZipEnhancer** (`speech_zipenhancer_ans_multiloss_16k_base`) is
Alibaba DAMO Academy's next-generation **single-channel speech
intelligent denoising** model. It is a 16 kHz-in → 16 kHz-out
acoustic-noise-suppression (ANS) system that:

* **Reduces noise impact in noisy acoustic environments** — from
  ambient room noise to active background interference — even to the
  point of full noise elimination;
* **Improves acoustic quality of audio of any origin** — not just
  microphone capture, but post-recorded speech, calls, streaming
  audio, etc.;
* **Extracts vocals from arbitrary background audio** — isolating
  the speech signal wherever it sits in the soundscape.

The model is built around a **dual-path** architecture (per
ModelScope metadata) and is trained with a **multi-loss**
objective (per the model id `..._multiloss_...`). Input and
output are both **16 kHz single-channel speech time-domain
waveforms**; the input can come straight from a single microphone
in real time. A live online demo is available via the ModelScope
Space widget.

## Links

- ModelScope: https://modelscope.cn/models/iic/speech_zipenhancer_ans_multiloss_16k_base

## Features

- type: Acoustic Noise Suppression / Speech Enhancement (single-channel denoising)
- bandwidth_extension: no (16 kHz in → 16 kHz out, not a bandwidth extender)
- inpainting: no (denoise for the full waveform, not segment-level inpainting)
- license: Apache-2.0
- model_type: dual-path (per ModelScope metadata)
- training_objective: multi-loss (per model id `..._multiloss_...`)
- input_sample_rate: 16,000 Hz
- output_sample_rate: 16,000 Hz
- channels: single-channel (mono)
- task: acoustic-noise-suppression (ANS)
- use_cases: denoise any audio source; improve acoustic quality; vocal extraction from background
- host_org: Alibaba DAMO Academy (iic on ModelScope)
- ecosystem: ModelScope; Hugging Face Spaces not hosted on HF, demo available through ModelScope's widget
- release_date_evidence: ModelScope CreatedTime = unix 1728713079 = 2024-10-12 06:04 UTC

## Comparison

- type: Acoustic Noise Suppression
- bandwidth_extension: ❌
- inpainting: ❌
- license: Apache-2.0

## Innovation

Alibaba's ZipEnhancer is among the few open **single-channel speech
denoising** models that ships both an explicit **dual-path
architecture** and a published **multi-loss training objective** at
the 16 kHz single-channel baseline. The dual-path split — a common
modern architectural pattern in speech enhancement — separates
the model's processing path for short-time-frame local acoustic
features from its longer-context path, which lets the system keep
a sharp response to sudden transient noise while still modeling
the slow envelope of stationary backgrounds. Combined with the
multi-loss objective (the model id suffix `_multiloss` indicates
multiple supervision signals during training, e.g. spectral /
waveform / perceptual losses), the result is one of the few openly
hosted ANS checkpoints that handles **arbitrary-source audio
quality improvement**, not just narrow-band microphone cleanup —
the documented use case extends to vocal extraction from full
mixes, which most ANS-only pipelines can't do without a separate
source-separation model.
