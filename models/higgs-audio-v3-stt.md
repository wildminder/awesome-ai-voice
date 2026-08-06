---
release_date: "March 25, 2026"
model_name: "Higgs-Audio-v3-STT"
category: "asr"
summary: "Boson AI — Higgs Audio v3 STT: a speech-to-text model combining a Whisper-Large-v3 encoder with a Qwen3 decoder (2.68B total parameters); English ASR with custom architecture, fine-tuned on public AMI / VoxPopuli / SPGISpeech / LibriSpeech / TED-LIUM / GigaSpeech / Earnings22 train splits; on the Open ASR Leaderboard."
slug: "higgs-audio-v3-stt"
---

# Higgs-Audio-v3-STT

**Higgs Audio v3 STT** is a speech-to-text model from Boson AI
combining a **Whisper-Large-v3 encoder** with a **Qwen3 decoder**
(2.68B total parameters). It is the ASR sibling of the Higgs Audio
v3 TTS model (`higgs-audio-v3-tts-4b`), sharing the same Qwen3
decoder family but specialized for speech recognition rather than
speech synthesis. The model uses a custom architecture
(`trust_remote_code=True` required) and is fine-tuned on public
train splits of **AMI (IHM), VoxPopuli (en), SPGISpeech,
LibriSpeech, TED-LIUM, GigaSpeech, and Earnings22** — with all
rows from source recordings that appear in the ESB/Open-ASR test
sets excluded from training to prevent contamination.

An updated checkpoint (June 2026) refreshed the fine-tuning data
and added a **phrase-level repetition-loop collapse** alongside
the existing word-repetition cap in `transcribe.py` — both
deterministic and applied uniformly to every dataset. The model
appears on the **Open ASR Leaderboard** and the **FFASR**
leaderboard (treble-technologies).

## Links

- HuggingFace: https://huggingface.co/bosonai/higgs-audio-v3-stt
- Paper: https://arxiv.org/abs/2603.02641

## Features

- parameters: 2.68B (Whisper-Large-v3 encoder + Qwen3 decoder)
- asr: yes (custom architecture; trust_remote_code=True)
- languages: English
- streaming: no (offline utterance transcription)
- license: Apache-2.0
- architecture: Whisper-Large-v3 encoder + Qwen3 decoder (custom `higgs_audio_3` code)
- pipeline_tag: automatic-speech-recognition
- library_name: transformers (custom_code)
- training_data: AMI (IHM), VoxPopuli (en), SPGISpeech, LibriSpeech, TED-LIUM, GigaSpeech, Earnings22 (public train splits; ESB/Open-ASR test-set rows excluded)
- repetition_handling: word-repetition cap + phrase-level repetition-loop collapse (deterministic, uniform)
- leaderboard: Open ASR Leaderboard (hf-audio/open_asr_leaderboard), FFASR (treble-technologies/ffasr)
- companion_tts: bosonai/higgs-audio-v3-tts-4b (the TTS sibling)
- createdAt: 2026-03-25T18:39:22Z
- downloads: ~6,886
- checkpoint_update: June 2026 (refreshed fine-tuning data + repetition-loop collapse)

## Comparison

- languages: English
- streaming: ❌
- license: Apache-2.0

## Innovation

Higgs Audio v3 STT pairs a **Whisper-Large-v3 encoder** (proven
audio representation) with a **Qwen3 decoder** (strong text LLM)
at 2.68B total parameters — a smaller-scale sibling of the 8B
variant (`higgs-audio-v3-8b-stt-v2`). The June 2026 update added
a **phrase-level repetition-loop collapse** alongside the existing
word-repetition cap, addressing a common failure mode in
autoregressive ASR where the decoder gets stuck repeating a
phrase. Both corrections are deterministic and applied uniformly
to every dataset, so the leaderboard results are directly
comparable across the pre- and post-update checkpoints. The
contamination-prevention protocol (excluding ESB/Open-ASR test-set
source recordings from training) is a transparency measure that
ensures the Open ASR Leaderboard results are clean.
