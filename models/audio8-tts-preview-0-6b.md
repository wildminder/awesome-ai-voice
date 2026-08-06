---
release_date: "July 28, 2026"
model_name: "Audio8-TTS-Preview-0.6b"
category: "tts"
summary: "Audio8 (AutoArk-AI) — Audio8 TTS Preview 0.6B: a 0.6B-parameter multilingual TTS with zero-shot voice cloning across 11 languages (Cantonese/Chinese/Dutch/English/French/German/Italian/Japanese/Korean/Polish/Spanish); DualAR architecture (slow AR semantic + fast AR codec) inspired by Fish Audio S2 Pro, 44.1 kHz bundled neural audio codec, 10 codebooks at ~21.5 frames/s."
slug: "audio8-tts-preview-0-6b"
---

# Audio8-TTS-Preview-0.6b

**Audio8 TTS Preview 0.6B** is a 0.6B-parameter multilingual
text-to-speech model with **zero-shot voice cloning**. It uses a
**DualAR architecture** inspired by
[Fish Audio S2 Pro](https://github.com/fishaudio/fish-speech): a
**slow AR transformer** predicts one semantic token per audio
frame, and a **fast AR transformer** predicts the frame's codec
codebooks conditioned on the slow hidden state and preceding
codebooks. The bundled **44.1 kHz neural audio codec** handles
both reference-audio encoding and waveform decoding — no
additional codec checkpoint is required. The model supports **11
recommended languages** (Cantonese, Chinese, Dutch, English, French,
German, Italian, Japanese, Korean, Polish, Spanish) with zero-shot
voice cloning from a reference audio clip + matching transcript.

This is a **preview release** — language coverage is intentionally
limited to the 11 recommended languages; broader multilingual
coverage and Chinese dialect support are planned for future
releases. The model uses custom Transformers code
(`trust_remote_code=True`).

## Links

- HuggingFace: https://huggingface.co/Audio8/Audio8-TTS-Preview-0.6b
- GitHub: https://github.com/Audio8-AI/Audio8_TTS
- Website: https://audio8-ai.github.io/Audio8_TTS/

## Features

- parameters: 601,159,424 (0.6B, excluding the codec)
- voice_cloning: yes (zero-shot; reference audio + matching transcript)
- asr: no
- languages: Cantonese, Chinese, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Spanish (11)
- streaming: no (full-utterance generation; packed text/audio context up to 2,048 positions)
- license: Apache-2.0
- architecture: DualAR (slow AR + fast AR), inspired by Fish Audio S2 Pro
- slow_ar: 24 layers, width 896, 14 attention heads, 2 KV heads
- fast_ar: 4 layers, width 896, 14 attention heads, 2 KV heads
- acoustic_tokens: 10 codebooks, 4,096 entries per codebook
- codec: 44.1 kHz, 2,048 samples per model frame (~21.5 frames/s), bundled (no external codec needed)
- context_length: up to 2,048 packed text/audio positions
- sample_rate: 44,100 Hz
- inference: transformers with trust_remote_code=True; CUDA-capable GPU recommended
- dependencies: torch>=2.5.0, torchaudio>=2.5.0, transformers>=4.57.0,<5, soundfile, safetensors
- preview_status: language coverage intentionally limited; broader multilingual + Chinese dialect support planned
- library_name: transformers (custom_code)
- pipeline_tag: text-to-speech
- createdAt: 2026-07-28T07:53:00Z

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Cantonese, Chinese, Dutch, English, French, German, Italian, Japanese, Korean, Polish, Spanish
- streaming: ❌
- license: Apache-2.0

## Innovation

The DualAR architecture is the technical centerpiece: rather than
a single autoregressive decoder predicting all codebook levels
sequentially (the standard codec-LLM TTS pattern), Audio8 splits
the work into a **slow AR** that predicts one semantic token per
audio frame and a **fast AR** that predicts the frame's remaining
codec codebooks conditioned on the slow hidden state. This
separation lets the semantic-level reasoning happen at the slow
AR's 24-layer depth while the acoustic codebook prediction stays
lightweight at 4 layers — reducing the total compute per frame
without sacrificing semantic quality. The **bundled 44.1 kHz
codec** (no external codec checkpoint needed) and the 10-codebook
/ 4,096-entry acoustic token design give the model self-contained
high-fidelity output at a compact 0.6B scale, making it one of
the smallest multilingual zero-shot-cloning TTS systems shipping
at 44.1 kHz.
