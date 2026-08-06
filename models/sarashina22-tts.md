---
release_date: "April 16, 2026"
model_name: "Sarashina2.2-TTS"
category: "tts"
summary: "SB Intuitions — Japanese-centric LLM-based TTS with bilingual ja+en support, zero-shot voice generation, diverse speaking styles, and responsibly-sourced training data."
slug: "sarashina22-tts"
---

# Sarashina2.2-TTS

Sarashina2.2-TTS is a Japanese-centric text-to-speech system from SB Intuitions built on a large language model. It supports both Japanese and English, delivers strong pronunciation accuracy on Japanese text through large-scale end-to-end training, and reproduces a speaker's voice, speaking style, and acoustic characteristics from a short reference clip (zero-shot). Training data is sourced exclusively from legitimately acquired, properly licensed speech archives per the Sarashina Model NonCommercial License Agreement v2.0 (released April 24, 2026).

## Links

- HuggingFace: https://huggingface.co/sbintuitions/sarashina2.2-tts
- GitHub: https://github.com/sbintuitions/sarashina2.2-tts
- Paper: https://arxiv.org/abs/2606.25369

## Features

- voice_cloning: yes (zero-shot, short reference clip, no fine-tuning)
- asr: no
- emotion_control: yes (diverse speaking styles — narration, broadcast, conversation, customer service)
- languages: Japanese, English
- streaming: no
- license: Research Only (Sarashina Model NonCommercial License Agreement v2.0 — non-commercial only)
- base_model: sbintuitions/sarashina2.2-0.5b-instruct-v0.1
- cross_lingual: yes (Japanese ↔ English, code switching)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Japanese, English
- streaming: ❌
- license: Research Only

## Innovation

Japanese-optimized TTS fine-tuned on responsibly-licensed Japanese training corpora with explicit cross-lingual code-switching to English in a single utterance; reference audio carries speaking style and speaker identity together, so the same prompt yields narration, broadcast, conversation, or customer-service delivery without separate style conditioning.
