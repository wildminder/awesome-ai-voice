---
release_date: "April 27, 2026"
model_name: "Higgs-Audio-v3-8B-STT-v2"
category: "asr"
summary: "Boson AI — Higgs Audio v3 8B STT v2: a speech-to-text model combining a Whisper-Large-v3 encoder with a Qwen3-8B decoder (8.91B total parameters, LoRA fine-tuned); English ASR with full Open ASR Leaderboard benchmark results — LibriSpeech clean WER 1.25%, GigaSpeech 8.47%, AMI 10.14%, average across 8 splits."
slug: "higgs-audio-v3-8b-stt-v2"
---

# Higgs-Audio-v3-8B-STT-v2

**Higgs Audio v3 8B STT v2** is the larger-scale speech-to-text
model from Boson AI, combining a **Whisper-Large-v3 encoder** with
a **Qwen3-8B decoder** (8.91B total parameters), fine-tuned with
**LoRA** on diverse ASR benchmarks. It is the larger sibling of
the 2.68B `higgs-audio-v3-stt` and shares the same custom
architecture (`trust_remote_code=True` required). The model ships
with full **model-index benchmark results** across 8 Open ASR
Leaderboard splits:

| Dataset | WER (%) |
|---|---|
| LibriSpeech (clean) | 1.25 |
| LibriSpeech (other) | 2.38 |
| SPGISpeech | 3.60 |
| TED-LIUM v3 | 3.09 |
| VoxPopuli | 5.92 |
| GigaSpeech | 8.47 |
| Earnings-22 | 8.73 |
| AMI (Meetings test) | 10.14 |

The model appears on the **Open ASR Leaderboard** and uses the
same Whisper-Large-v3 + Qwen3 decoder architecture as the base
STT, scaled up to the 8B Qwen3 backbone.

## Links

- HuggingFace: https://huggingface.co/bosonai/higgs-audio-v3-8b-stt-v2
- Paper: https://arxiv.org/abs/2603.02641

## Features

- parameters: 8.91B (Whisper-Large-v3 encoder + Qwen3-8B decoder, LoRA fine-tuned)
- asr: yes (custom architecture; trust_remote_code=True)
- languages: English
- streaming: no (offline utterance transcription)
- license: Apache-2.0
- architecture: Whisper-Large-v3 encoder + Qwen3-8B decoder (custom `higgs_audio_3` code)
- pipeline_tag: automatic-speech-recognition
- library_name: transformers (custom_code)
- fine_tuning: LoRA on diverse ASR benchmarks
- base_model: bosonai/higgs-audio-v3-8b
- eval_librispeech_clean: WER 1.25%
- eval_librispeech_other: WER 2.38%
- eval_spgispeech: WER 3.60%
- eval_tedlium_v3: WER 3.09%
- eval_voxpopuli: WER 5.92%
- eval_gigaspeech: WER 8.47%
- eval_earnings22: WER 8.73%
- eval_ami_ihm: WER 10.14%
- leaderboard: Open ASR Leaderboard (hf-audio/open_asr_leaderboard)
- companion_stt_small: bosonai/higgs-audio-v3-stt (2.68B variant)
- companion_tts: bosonai/higgs-audio-v3-tts-4b (the TTS sibling)
- createdAt: 2026-04-27T17:29:37Z
- downloads: ~1,133

## Comparison

- languages: English
- streaming: ❌
- license: Apache-2.0

## Innovation

The 8B STT v2 is the **scaled-up sibling** of the 2.68B base STT,
pairing the same Whisper-Large-v3 encoder with a **Qwen3-8B
decoder** (vs the base's smaller Qwen3 decoder) and fine-tuning
with **LoRA** rather than full fine-tuning — keeping the 8B
backbone's text capability while adapting the ASR head. The
full model-index benchmark results (LibriSpeech clean WER 1.25%,
GigaSpeech 8.47%) are published directly in the model card's
`model-index` metadata, making the evaluation transparent and
reproducible. The model shares the same custom `higgs_audio_3`
remote code as the base STT, so users can swap between the 2.68B
and 8.91B variants without changing their inference pipeline.
