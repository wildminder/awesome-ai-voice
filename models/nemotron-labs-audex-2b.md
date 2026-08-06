---
release_date: "July 6, 2026"
model_name: "Nemotron-Labs-Audex-2B"
category: "a2a"
summary: "NVIDIA — smaller SFT sibling of Nemotron-Labs-Audex-30B-A3B: a 2B unified audio-text LLM that both understands audio (audio QA, ASR, speech translation) and generates audio (text-to-speech, text-to-audio, speech-to-speech), preserving text-reasoning and agentic capabilities while gaining audio I/O."
slug: "nemotron-labs-audex-2b"
---

# Nemotron-Labs-Audex-2B

**Nemotron-Labs-Audex-2B** is NVIDIA's smaller sibling of the
Audex unified audio-text LLM. Like the **30B-A3B** flagship, the
2B is a single model family that both **understands audio** (audio
QA, speech recognition, speech translation) and **generates audio**
(text-to-speech, text-to-audio, speech-to-speech). It is built on
the same audio-vocabulary-extended transformer stack as the 30B-A3B
but at a **densely-parameterized 2B scale** (no MoE), so the
compute and memory footprint are lowered to a budget tractable on
more modest hardware. The 2B checkpoint is the project-tagged
**SFT variant** in the Audex collection — instruction-tuned and
ready for inference. Both sizes preserve text reasoning,
alignment, knowledge, long-context, and agentic capabilities of the
text backbone while adding discrete-token audio I/O.

The complete Audex collection (paper + 30B-A3B model + 2B model +
HF Space demo + arXiv 2607.05196 "Unified Audio Intelligence
Without Regressing on Text Intelligence") lives at the
[huggingface.co/collections/nvidia/nemotron-labs-audex](https://huggingface.co/collections/nvidia/nemotron-labs-audex)
page.

## Links

- HuggingFace: https://huggingface.co/nvidia/Nemotron-Labs-Audex-2B
- Paper: https://arxiv.org/abs/2607.05196
- Collection: https://huggingface.co/collections/nvidia/nemotron-labs-audex
- Demo: https://huggingface.co/spaces/nvidia/Nemotron-Labs-Audex

## Features

- parameters: 2B (dense; SFT fine-tune, instruct + reasoning-ready)
- text: yes (text LLM heads; text reasoning preserved)
- video: no
- audio: yes (input + output — audio understanding + audio generation)
- modalities: text + audio (input and output)
- max_duration: not stated
- sample_rate: not stated (decoder output)
- voice_cloning: no
- audio_understanding: yes (audio QA, classification)
- asr: yes (speech recognition)
- speech_translation: yes
- text_to_speech: yes
- text_to_audio: yes
- speech_to_speech_generation: yes
- reasoning_mode: yes (thinking + instruct modes inherited from text backbone)
- license: NVIDIA NC (NVIDIA OneWay NonCommercial License — matched with the 30B-A3B sibling)
- pipeline_tag: text-generation
- library_name: transformers
- derived_from: same family as Nemotron-Labs-Audex-30B-A3B
- companion_30b: nvidia/Nemotron-Labs-Audex-30B-A3B (MoE: 30B total, 3B active)
- spaces: nvidia/Nemotron-Labs-Audex, WaveCut/Nemotron-Labs-Audex, hugging-apps/nemotron-labs-audex-2b
- createdAt: 2026-07-06T16:21:07Z
- downloads: ~2.4k

## Comparison

- text: ✅
- video: ❌
- audio: ✅
- max_duration: —
- sample_rate: —
- license: NVIDIA NC

## Innovation

The 2B sibling matters because it preserves the *central thesis* of
the Audex paper — **unified audio-text LLM intelligence without
regressing on text intelligence** — while dropping the parameter
budget substantially. The 30B-A3B MoE hits a 1M-context, agentic
flagship tier; the 2B dense version is the same audio-aware
architecture extended down to a budget that doesn't require a
high-end MoE serving stack. The pair lets users choose on
deployment cost rather than on capability sub-selection: the 2B
ships the same audio-to-audio + text-to-audio + audio-understanding
+ ASR + speech-translation coverage as the MoE flagship, just at
the cost of longer-context / reasoning depth that the MoE was
specifically tuned for. Both share the **discrete-audio-token
vocabulary extension** of the text backbone so they can be reasoned
about interchangeably.
