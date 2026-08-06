---
release_date: "June 3, 2026"
model_name: "dots.tts"
category: "tts"
summary: "Rednote-HiLab — 2B-parameter fully continuous autoregressive TTS (semantic encoder + LLM + AR flow-matching head over 48 kHz AudioVAE)."
slug: "dots-tts"
---

# dots.tts

dots.tts is a 2B-parameter fully continuous, end-to-end autoregressive TTS system from Rednote-HiLab. The backbone pairs a semantic encoder, an LLM, and an autoregressive flow-matching acoustic head over a 48 kHz AudioVAE, with no discrete tokens anywhere in the pipeline. It achieves the best average performance on Seed-TTS-Eval (WER 0.94 / 1.30 / 6.60 on zh / en / zh-hard) and the highest speaker similarity on a 24-language MiniMax multilingual benchmark, with broad cross-lingual voice cloning.

## Links

- HuggingFace: https://huggingface.co/rednote-hilab/dots.tts-base
- GitHub: https://github.com/rednote-hilab/dots.tts
- Website: https://rednote-hilab.github.io/dots.tts-demo/
- Demo: https://huggingface.co/spaces/rednote-hilab/dots.tts

## Features

- parameters: 2B (semantic encoder + LLM + AR flow-matching acoustic head)
- voice_cloning: yes (zero-shot, monolingual and cross-lingual)
- asr: no
- languages: Multilingual (24+ languages; zh / en focus)
- streaming: no
- license: Apache-2.0
- sample_rate: 48 kHz
- tokenizer: 48 kHz AudioVAE (continuous, no discrete tokens)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Multilingual
- streaming: ❌
- license: Apache-2.0

## Innovation

A fully continuous autoregressive pipeline that keeps generation in waveform-latent space end-to-end (no discrete-code phase), pairing an LLM-side semantic encoder with an autoregressive flow-matching acoustic head over a 48 kHz AudioVAE — yielding SOTA seed-TTS-Eval scores and the strongest speaker-similarity number (83.9 avg) on the 24-language MiniMax multilingual benchmark.
