---
release_date: "June 2, 2026"
model_name: "Confucius4-TTS"
category: "tts"
summary: "NetEase Youdao — LLM-based multilingual and cross-lingual zero-shot TTS: speech encoder + LLM backbone with 14 languages, unconstrained voice cloning, and unaccented cross-lingual voice transfer."
slug: "confucius4-tts"
---

# Confucius4-TTS

Confucius4-TTS is an LLM-based text-to-speech system from NetEase Youdao designed for multilingual and cross-lingual synthesis. It uses a speech encoder + LLM (Text2Semantic) + flow-matching Semantic2Acoustic architecture that allows zero-shot voice cloning without a required reference transcript and explicit cross-lingual voice transfer with unaccented output across languages. Covers Chinese, English, Japanese, Korean, German, French, Spanish, Indonesian, Italian, Thai, Portuguese, Russian, Malay, and Vietnamese with code-switching and emotion transfer.

## Links

- HuggingFace: https://huggingface.co/netease-youdao/Confucius4-TTS
- GitHub: https://github.com/netease-youdao/Confucius4-TTS
- Demo: https://confucius4-tts.youdao.com/gradio

## Features

- voice_cloning: yes (zero-shot, no reference transcript required)
- asr: no
- emotion_control: yes (seamless emotion transfer)
- languages: 14 (zh, en, ja, ko, de, fr, es, id, vi, th, pt, it, ru, ms)
- streaming: no
- license: Apache-2.0 (code); Apache-2.0 (model per Hugging Face cardData)
- architecture: speech encoder + LLM (T2S) + flow-matching head (S2A)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 14
- streaming: ❌
- license: Apache-2.0

## Innovation

Cross-lingual voice transfer without accent drift: the same reference voice stays consistent when the speaker switches languages — backed by a speech encoder + LLM backbone pipeline (T2S) with a flow-matching acoustic decoder (S2A) and training that bundles 14 languages with code-switched, emotion-preserving decoding.
