---
release_date: "June 4, 2026"
model_name: "Higgs Audio v3 TTS"
category: "tts"
summary: "Boson AI — spoken, expressive multilingual TTS with inline control tags and zero-shot voice cloning."
slug: "higgs-audio-v3-tts"
---

# Higgs Audio v3 TTS

Boson AI's flagship conversational TTS: an ~4B autoregressive decoder over interleaved text and audio tokens from the Higgs Tokenizer (8 codebooks at 25 fps / 24 kHz). Built for voice chat rather than narration, it covers 102 languages with zero-shot voice cloning and inline control over emotion, style, prosody, pauses, and sound effects.

## Links

- HuggingFace: https://huggingface.co/bosonai/higgs-audio-v3-tts-4b
- GitHub: https://github.com/sgl-project/sglang-omni
- Blog: https://www.boson.ai/blog/higgs-audio-v3-tts
- Demo: https://huggingface.co/spaces/multimodalart/higgs-audio-v3-tts

## Features

- parameters: 4B (BF16, 36 layers, hidden=2560, GQA 32/8)
- architecture: Autoregressive decoder (Qwen3-style)
- voice_cloning: yes (zero-shot, no reference fine-tune)
- asr: no
- pronunciation: yes (<|prosody:*> inline tags)
- emotion_control: yes
- languages: 102 (85 with WER/CER <5, 17 between 5-10)
- streaming: yes (25 fps token decoding (40 ms / frame))
- audio_output: 24 kHz
- license: Research Only

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 102
- streaming: ✅
- license: Research Only

## Innovation

Interleaved text/audio token modelling with a delay-pattern multi-codebook embedding/head: a single autoregressive stack emits both modalities and supports inline `<|category:value|>` control tags (emotion/style/sfx/prosody) inserted at any point in the target text.
