---
release_date: "May 25, 2026"
model_name: "MOSS-TTS"
category: "tts"
summary: "OpenMOSS Team / MOSI.AI — production-grade TTS foundation model; v1.5 extends the 20-language MOSS-TTS 1.0 baseline to 31 languages with stronger multilingual synthesis, more stable voice cloning, and explicit inline pause control."
slug: "moss-tts"
---

# MOSS-TTS

MOSS-TTS is a production-grade Text-to-Speech foundation model developed by the OpenMOSS Team and MOSI.AI. The current public v1.5 release preserves the original 1.0 capabilities — zero-shot voice cloning, long-form speech generation, token-level duration control, Pinyin/IPA pronunciation supervision, multilingual synthesis, and code-switching — and extends multilingual continued training from 20 languages to **31 languages** including Cantonese, Dutch, Finnish, Hindi, Macedonian, Malay, Romanian, Swahili, Tagalog, Thai, and Vietnamese. v1.5 improves speaker similarity, reduces cloning variance on long-reference / short-text scenarios, follows punctuation-driven prosody more reliably, and adds explicit inline pause markers (e.g., `[pause 3.2s]`).

## Links

- HuggingFace: https://huggingface.co/OpenMOSS-Team/MOSS-TTS-v1.5
- HuggingFace: https://huggingface.co/OpenMOSS-Team/MOSS-TTS-Local-Transformer-v1.5
- GitHub: https://github.com/OpenMOSS/MOSS-TTS
- Website: https://mosi.cn/#models
- Paper: https://arxiv.org/abs/2603.18090
- Demo: https://studio.mosi.cn

## Features

- parameters: 8B (Delay), 1.7B (Local)
- voice_cloning: yes (zero-shot; v1.5 improves similarity + variance)
- asr: no
- pronunciation: yes (Pinyin/Phoneme-level)
- emotion_control: yes
- languages: 31 (extended from v1.0's 20)
- streaming: yes
- license: Apache-2.0
- max_duration: 1 hour
- pause_control: yes (inline markers like `[pause 3.2s]`)
- lang_tag_control: yes (set `language=` in user message)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 31
- streaming: ✅
- license: Apache-2.0

## Innovation

v1.5 widens MOSS-TTS from 20 → 31 languages with stronger per-language multilingual synthesis (control via a language tag in the user message), more stable cloning under long-reference / short-text conditions, punctuation-driven prosody that holds up across long sentences, and explicit inline pause tokens (`[pause 3.2s]`) for scripted narration control.
