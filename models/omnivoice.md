---
release_date: "2026"
model_name: "OmniVoice"
category: "tts"
summary: "Massive multilingual zero-shot TTS model scaling to 600+ languages."
slug: "omnivoice"
---

# OmniVoice

Massive multilingual zero-shot TTS model scaling to 600+ languages. Uses diffusion language model-style discrete non-autoregressive architecture with single-stage text-to-acoustic mapping.

## Links

- Website: https://zhu-han.github.io/omnivoice/
- HuggingFace: https://huggingface.co/k2-fsa/OmniVoice

## Features

- parameters: -
- voice_cloning: yes
- asr: no
- pronunciation: yes (Pinyin/CMU)
- emotion_control: yes
- languages: 600+
- streaming: no
- license: Apache-2.0
- training-data: 581k hours

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 600+
- streaming: ❌
- license: Apache-2.0

## Innovation

Simplified single-stage architecture vs conventional two-stage pipelines. Full-codebook random masking strategy with LLM initialization for superior intelligibility. Noise-robust prompt processing.
