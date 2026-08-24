---
release_date: "March 13, 2026"
model_name: "SILMA TTS"
category: "tts"
summary: "SILMA AI — lightweight 150M bilingual (Arabic/English) TTS pretrained from scratch on the F5-TTS diffusion architecture; instant voice cloning with <8s reference, full Tashkeel support, RTF ≈0.12."
slug: "silma-tts"
---

# SILMA TTS

SILMA TTS v1 is a high-performance, **150M-parameter** bilingual (Arabic/English) TTS model developed by SILMA AI. Built on the **F5-TTS diffusion architecture**, it was pretrained from scratch using tens of thousands of hours of high-quality public and proprietary data. It supports instant voice cloning with less than 8 seconds of reference audio (the reference transcript can also be left empty — it is transcribed on the fly), full support for Arabic **Tashkeel** (diacritics, auto-enriched via CATT when absent), NeMo-based text normalization, and an RTF around **0.12** on an RTX 4090. Released under a commercial-friendly license: code MIT, model weights Apache-2.0. The model is 100% compatible with F5-TTS v1.1.7 tooling for inference and fine-tuning.

## Links

- HuggingFace: https://huggingface.co/silma-ai/silma-tts
- GitHub: https://github.com/SILMA-AI/silma-tts
- Website: https://silma.ai/arabic-text-to-speech

## Features

- voice_cloning: yes (instant, <8s reference audio; ref text auto-transcribed if omitted)
- asr: no
- languages: 2 (Arabic MSA/Fusha + English)
- license: Apache-2.0
- parameters: 150M
- architecture: F5-TTS Diffusion Transformer with flow matching (pretrained from scratch, F5-TTS v1.1.7-compatible)
- pronunciation: yes (full Arabic Tashkeel support; CATT auto-diacritization fallback)
- cost: RTF ≈ 0.12 (RTX 4090)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Arabic, English
- license: Apache-2.0

## Innovation

Brings native-level Arabic synthesis to a 150M footprint: one of the smallest open F5-TTS-family models pretrained from scratch rather than fine-tuned, with first-class Arabic handling (Tashkeel-aware pronunciation via CATT enrichment, NeMo text normalization) alongside English, plus instant zero-shot cloning under fully permissive licensing (Apache-2.0 weights / MIT code).
