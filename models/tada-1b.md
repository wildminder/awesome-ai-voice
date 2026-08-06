---
release_date: "January 12, 2026"
model_name: "TADA"
category: "tts"
summary: "Hume AI — Text-Acoustic Dual-Alignment unified speech-language model on Llama 3.2 1B; 1:1 token alignment, dynamic-duration autoregression; English."
slug: "tada-1b"
---

# TADA

TADA is a unified speech-language model from Hume AI built around a *Text-Acoustic Dual-Alignment* tokenizer: for every text/subword token there is exactly one corresponding speech vector, so the audio stream stays 1:1 aligned with text. As a TTS model, each autoregressive step covers one text token and dynamically determines the duration and prosody for that token, breaking the fixed-frames-per-second constraint that drives most modern TTS backbones. As a speech-language model, it generates a text token and the speech for the preceding token in the same dual step.

Built on Llama-3.2-1B (TADA-1B variant); larger variants exist in the same HumeAI collection. Targets English; under the community Llama 3.2 license.

## Links

- HuggingFace: https://huggingface.co/HumeAI/tada-1b
- GitHub: https://github.com/HumeAI/tada
- Demo: https://huggingface.co/spaces/HumeAI/tada
- PyPI: https://pypi.org/project/hume-tada/
- Paper: https://arxiv.org/abs/2602.23068
- Blog: https://www.hume.ai/blog/opensource-tada

## Features

- parameters: 1B (Llama 3.2 1B base)
- voice_cloning: no
- asr: no
- emotion_control: yes (per-token dynamic prosody)
- languages: English
- streaming: no
- license: Other (Llama 3.2 Community License)
- base_model: meta-llama/Llama-3.2-1B
- tokenization: 1:1 text–acoustic dual alignment (one speech vector per text token)
- dynamic_duration: yes (each autoregressive step covers one text token, duration is determined per-token)

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: English
- streaming: ❌
- license: Other

## Innovation

A dual-alignment speech–text tokenizer that decouples autoregression from a fixed audio frame rate: each text token owns exactly one speech vector, and the model synthesizes the *whole segment for that token* in one step, regardless of how long the spoken form is — eliminating transcript hallucination and the latency overhead of constant-frame-rate codecs while staying as compact as Llama 3.2 1B.
