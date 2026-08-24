---
release_date: "August 22, 2026"
model_name: "Rynsan TTS"
category: "tts"
summary: "Tynrai AI / Toiar — multilingual TTS extending k2-fsa/OmniVoice to the low-resource Khasic languages of Meghalaya (Khasi, Garo, Pnar) alongside English and Hindi."
slug: "rynsan-tts"
---

# Rynsan TTS

Rynsan TTS is a multilingual text-to-speech model that extends [k2-fsa/OmniVoice](https://huggingface.co/k2-fsa/OmniVoice) to support **Khasi, Garo, and Pnar** — languages of Meghalaya, India that have historically had limited representation in modern speech technology. Rather than building a system from scratch, Rynsan retains the multilingual capabilities of the base model while adding speech data for these low-resource Khasic languages. Developed under the **Tynrai AI** initiative, its broader goal is accessible speech technology for the diverse languages and dialects of Meghalaya, supporting their preservation and use in voice-based applications. A live demo is available at [ri.tynrai.in/demo](https://ri.tynrai.in/demo). The repository is gated (manual access approval).

## Links

- HuggingFace: https://huggingface.co/toiar/Rynsan-TTS
- Demo: https://ri.tynrai.in/demo

## Features

- asr: no
- languages: 5+ (English, Hindi + extension languages Khasi `kha`, Garo `grt`, Pnar `pbv`; base OmniVoice supports more)
- license: CC BY 4.0
- parameters: ~0.61B
- architecture: OmniVoice (k2-fsa) multilingual TTS, extended fine-tune
- base_model: k2-fsa/OmniVoice
- developer: Toiar / Tynrai AI

## Comparison

- asr: ❌
- languages: Khasi, Garo, Pnar, English, Hindi
- license: CC BY 4.0

## Innovation

Extends a modern multilingual TTS foundation to three substantially under-resourced Khasic languages — a rare production-oriented entry for indigenous-language speech tech, aimed at accessibility, education, and language preservation rather than benchmark leadership.
