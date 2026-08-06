---
release_date: "July 13, 2026"
model_name: "GigaChat3.1-Audio"
category: "asr"
summary: "ai-sage (Sber) — audio-native MoE LLM (10B total, A1.8B active) built on GigaChat 3.1 Lightning: a Conformer speech encoder + modality adapter feeds audio embeddings directly into a Mixture-of-Experts decoder, giving speech question-answering, temporal grounding (timestamped event localization in long audio), emotion recognition, speech translation, and Russian ASR alongside text LLM quality."
slug: "gigachat3-audio"
---

# GigaChat3.1-Audio

`GigaChat Audio 10B` is an audio-native LLM built on top of the
GigaChat 3.1 Lightning text model (10B total parameters, A1.8B
active). A Conformer speech encoder and a modality adapter feed
audio embeddings directly into the existing Mixture-of-Experts
decoder, so the model retains the text quality of its base while
adding speech understanding. Capabilities include audio question
answering and classification, **temporal grounding** (event
localization in long audio with timestamped descriptions and
timestamped audio summarization), emotion recognition (Dusha
benchmarks), tool-use, and text-only tasks. The temporal-grounding
skills are trained on the purpose-built
[TimeGround-1M](https://huggingface.co/datasets/ai-sage/TimeGround-1M)
dataset of long-form audio paired with time-aligned annotations.
On Russian ASR (Golos crowd), the model reports WER ≈14.7 versus
Whisper-large-v3 ≈9.1; on temporal localization it scores
mIoU 40.3 / 48.3 on ≤10min / 20–60min clips — substantially above
Voxtral (3B) and Phi-4 (4B). Multiple HF Spaces (e.g.
`hugging-apps/gigaam-multilingual-asr`) host live demos of the
related GigaAM-Multilingual family.

## Links

- HuggingFace: https://huggingface.co/ai-sage/GigaChat3.1-Audio-10B-A1.8B
- Paper: https://arxiv.org/abs/2607.10387
- Demo: https://huggingface.co/spaces/hugging-apps/gigaam-multilingual-asr

## Features

- parameters: 10B total (A1.8B active, MoE)
- asr: yes (Russian ASR; Golos crowd WER ≈14.7)
- languages: Russian, English
- streaming: no (long-form offline inference)
- license: MIT
- architecture: audio-native MoE LLM — Conformer speech encoder + modality adapter + MoE decoder
- base_model: ai-sage/GigaChat3.1-10B-A1.8B (GigaChat 3.1 Lightning text model)
- capabilities: audio QA, classification, temporal grounding, emotion recognition, speech translation, tool-use, text-only
- temporal_grounding: yes (timestamped event localization in long audio)
- training_data_audio_grounding: ai-sage/TimeGround-1M (1M long-form audio + time-aligned annotations)
- evaluation_mmau: 62.2 (vs Voxtral 3B 59.8, Phi-4 4B 68.3)
- evaluation_mmlu_speech: 50.3
- evaluation_audio_math_mqa: 72.5
- evaluation_emotion_dusha_crowd: 90.0 acc
- evaluation_emotion_dusha_podcast: 92.4 acc
- evaluation_asr_ru_golos: WER 14.7
- evaluation_temporal_localization_10m: mIoU 40.3
- evaluation_temporal_localization_20_60m: mIoU 48.3

## Comparison

- languages: Russian, English
- streaming: ❌
- license: MIT

## Innovation

Two things make GigaChat3.1-Audio stand out among audio LLMs.
First, **modality-injection into an existing MoE**: rather than
training a smaller speech-text model from scratch, it taps a
10B-A1.8B MoE text LLM (GigaChat 3.1 Lightning) by inserting a
Conformer encoder + linear adapter that project audio embeddings
into the existing decoder sequence — so text quality is inherited
rather than re-learned. Second, **timestamped temporal grounding
on long audio**: trained on the TimeGround-1M dataset, the model
produces event-localization mIoU scores (40.3 / 48.3 on ≤10min /
20–60min clips) that are an order of magnitude above comparable
open models (Voxtral 3B 3.4 mIoU on ≤10min; 0.1 on 20–60min), and
its audio-summarization output is timestamped rather than just a
flat transcript.
