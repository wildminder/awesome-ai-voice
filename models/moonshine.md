---
release_date: "September 26, 2024"
model_name: "Moonshine"
category: "asr"
summary: "Useful Sensors — tiny (27M / 61M) English ASR designed for severely memory- and compute-constrained deployment; sequence-to-sequence architecture from 200k hours of internet + public HF audio."
slug: "moonshine"
---

# Moonshine

Moonshine is a tiny automatic-speech-recognition family from Useful Sensors, designed for real-time speech transcription on severely memory- and compute-constrained hardware. The release ships two checkpoints (tiny 27M, base 61M), both English-only ASR trained on 200,000 hours of audio + transcript pairs collected from the internet and open HuggingFace datasets. It is the smallest practical Wh-class model family for edge / microcontroller-class deployment among those with public benchmarks against standard ASR datasets.

## Links

- HuggingFace: https://huggingface.co/UsefulSensors/moonshine
- GitHub: https://github.com/usefulsensors/moonshine
- Blog: https://petewarden.com/2024/10/21/introducing-moonshine-the-new-state-of-the-art-for-speech-to-text/
- Paper: https://arxiv.org/abs/2410.15608

## Features

- parameters: 27M (tiny), 61M (base)
- asr: yes
- languages: English
- streaming: yes (real-time target)
- license: MIT
- architecture: sequence-to-sequence ASR
- training_data: 200,000 hours (internet + open HF datasets)
- target_hardware: low-cost / edge / MCU-class
- variants_english_only: yes

## Comparison

- languages: English
- streaming: ❌
- license: MIT

## Innovation

A purpose-built tiny ASR (27M–61M parameters) ranging far below the smallest Whisper-class models while remaining competitive on standard ASR datasets — built specifically so a microcontroller / low-cost hardware developer can run real-time English transcription with usable accuracy, rather than shipping a quantized-down Whisper clone.
