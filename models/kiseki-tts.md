---
release_date: "August 15, 2026"
model_name: "Kiseki-TTS"
category: "tts"
summary: "telecomadm1145 — a small, fast Japanese TTS with a Mamba2 state-space decoder (O(1) per-frame cost, no KV cache) built on the Qwen3-TTS-Tokenizer-12Hz codec; the same checkpoint also does Japanese ASR."
slug: "kiseki-tts"
---

# Kiseki-TTS

Kiseki-TTS is a small, fast Japanese text-to-speech model from telecomadm1145 built on top of `Qwen/Qwen3-TTS-Tokenizer-12Hz`. It generates discrete neural audio codec tokens at **12.5 Hz** (4–6× fewer autoregressive steps than 50–75 Hz codecs) and decodes them to waveform with the Qwen3 TTS codec. The acoustic decoder is a linear-time **Mamba2 SSM** rather than a self-attention stack, so generation cost is constant per frame — memory does not grow with utterance length and there is no KV cache to manage. Because TTS and ASR were trained jointly in a single multi-task run, the same checkpoint also performs **ASR** (Japanese speech → text, reading only codec layer 0). It is a **single-domain voice** (ASMR-style Japanese training data) with no speaker conditioning or voice cloning.

## Links

- HuggingFace: https://huggingface.co/telecomadm1145/Kiseki-TTS

## Features

- voice_cloning: no (single fixed ASMR-style Japanese voice, no speaker conditioning)
- asr: yes (auxiliary, Japanese speech → text, codec layer 0 only)
- languages: Japanese only (ja)
- license: MIT
- parameters: ~0.41B (0.33B backbone + 78M audio branch)
- architecture: Transformer encoder (12 layers, bidirectional self-attention) + cross-attention → Mamba2 SSM decoder (6 layers, no causal self-attention)
- audio_codec: Qwen3-TTS-Tokenizer-12Hz (12.5 Hz, 16 quantizer layers)
- base_model: Kiseki-1.1-0.3B (seq2seq translation model)
- training_data: telecomadm1145/asmr_archive_qwentts_encoded

## Comparison

- voice_cloning: ❌
- asr: ✅
- languages: Japanese
- license: MIT

## Innovation

The decoder deliberately omits causal self-attention — temporal context is carried entirely by the Mamba2 recurrent state while text conditioning enters through cross-attention whose K/V are computed once during prefill. This yields O(1) state per frame (a fixed SSM tensor plus a 3-frame conv window) instead of an O(T) KV cache, so long-form synthesis degrades gracefully past the ~41 s training ceiling instead of hitting a memory cliff. Combined with the 12.5 Hz codec and a shared multi-token-prediction head that resolves all 16 codebook layers in one trunk pass, the model is both compute- and memory-bandwidth-bound rather than quadratic in length.
