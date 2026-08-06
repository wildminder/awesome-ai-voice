---
release_date: "April 26, 2026"
model_name: "Scenema Audio"
category: "tts"
summary: "ScenemaAI — zero-shot expressive voice cloning and speech generation built on an audio diffusion transformer extracted from LTX 2.3's 22B audiovisual model; 13 languages, action-tag-driven emotional arcs."
slug: "scenema-audio"
---

# Scenema Audio

Scenema Audio is a zero-shot expressive voice cloning and speech generation model from ScenemaAI. It is built on an audio diffusion transformer extracted from the audio branch of Lightricks' LTX 2.3 (a 22B audiovisual model) — keeping the in-the-wild acoustic quality the bigger model learned while specializing for speech output. Generation is **prompt-driven**: a `<speak>` tag carries a `voice` description, `gender`, optional `scene` (ambient audio around the voice), and `language`; an `<action>` tag shifts emotional state mid-generation. Action tags cover rage, grief, joy, fear, exhaustion; voice prompt can describe timbre/pitch/breathiness/rasp/resonance plus character archetypes ("Tony Soprano having a breakdown"). Supports zero-shot voice cloning from 10-20 seconds of reference audio with some emotional variability, automatic long-form narration by splitting text and maintaining voice continuity, and 13 multilingual built-ins.

## Links

- HuggingFace: https://huggingface.co/ScenemaAI/scenema-audio
- GitHub: https://github.com/ScenemaAI/scenema-audio
- Website: https://scenema.ai/audio

## Features

- parameters: (audio diffusion transformer of LTX 2.3, weights ~9.8 GB bf16 / ~4.9 GB INT8 + ~6.7 GB pipeline)
- voice_cloning: yes (zero-shot, 10-20 s reference audio with emotional variability)
- asr: no
- emotion_control: yes (action-tag-driven emotional arcs mid-generation)
- languages: 13 (en, de, fr, es, it, pt, ja, zh, ko, ru, ar, hi, sw)
- streaming: no
- license: Other (LTX-2 Community License)
- parent_model: Lightricks LTX-2.3 (audio branch)
- prompt_format: `<speak voice=… gender=… scene=… language=…>` XML with `<action>` tag for shifting emotion
- long_form_narration: yes (auto-splits text while preserving voice continuity)
- quantized: yes (INT8 weights at ~4.9 GB, identical quality)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English, German, French, Spanish, Italian, Portuguese, Japanese, Chinese, Korean, Russian, Arabic, Hindi, Swahili
- streaming: ❌
- license: Other

## Innovation

A standalone audio diffusion transformer extracted from a much bigger multimodal source: the model inherits how people actually sound in real scenes (angry, laughing, whispering, crying, exhausted, terrified) and exposes that capacity through a `<speak>` + `<action>` prompt interface — emotional state shifts within a single generation, instead of being a token-level or speaker-level conditioning problem.
