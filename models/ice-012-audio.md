---
release_date: "August 29, 2026"
model_name: "ICE-012 Audio"
category: "tts"
summary: "DarkPs — multilingual TTS covering 590 language names/variants with reference-based voice cloning, streaming output, and rich voice controls (gender, age, pitch, accent, style, speed) via an active acoustic adapter."
slug: "ice-012-audio"
---

# ICE-012 Audio

ICE-012 Audio is a multilingual text-to-speech model from DarkPs (a FanuonAI organization) with streaming output and reference-based voice cloning. Its defining trait is breadth of language coverage — **590 language names/variants** are accepted (name or 2–3-letter ID, with a language-agnostic fallback), including 13 Arabic dialects ("Lahgtna" variants) alongside the full ISO list. It introduces an **active acoustic adapter** — conditioning codec embeddings before the backbone and refining hidden states after it. Voice is controllable along six axes: gender (male/female), age (child → elderly), pitch (5 levels), accent (10 English accents), style (e.g. whisper), and speed (0.5–2.0×), plus an `--auto-voice` mode where the model picks a voice automatically. The checkpoint is ~714M parameters (F16) and runs via `transformers` with `trust_remote_code=True`. Released under CC BY-NC 4.0.

## Links

- HuggingFace: https://huggingface.co/darkps/ice-012-audio
- Website: https://dark.ps
- Demo: https://huggingface.co/spaces/hugging-apps/ice-012-audio-tts

## Features

- voice_cloning: yes (reference-audio based; reference transcript improves quality)
- asr: no
- languages: 590 names/variants (incl. 13 Arabic Lahgtna dialects; language-agnostic fallback)
- streaming: yes (streaming WAV output, *_stream.wav)
- license: CC BY-NC 4.0
- parameters: ~714M (714,409,993 F16)
- architecture: causal LM with active acoustic adapter (conditions codec embeddings pre-backbone, refines hidden states post-backbone)
- voice_controls: gender, age, pitch, accent, style, speed; auto-voice mode

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 590
- streaming: ✅
- license: CC BY-NC 4.0

## Innovation

The active acoustic adapter wraps the backbone on both sides — conditioning codec embeddings before it and refining hidden states after — while a six-axis voice-control space (gender/age/pitch/accent/style/speed plus auto-voice) and 590-language coverage make it one of the broadest single-checkpoint TTS releases for dialect and minority-language synthesis.
