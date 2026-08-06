---
release_date: "May 16, 2026"
model_name: "OronTTS"
category: "tts"
summary: "btsee — F5-TTS (Flow Matching + DiT + Vocos) for Mongolian (Khalkha Cyrillic) and Kazakh (Cyrillic); non-autoregressive zero-shot synthesis trained on the mbspeech_mn Mongolian corpus."
slug: "oron-tts"
---

# OronTTS

OronTTS is a non-autoregressive text-to-speech model from `btsee`, an F5-TTS fork specialized for Mongolian (Khalkha Cyrillic) and Kazakh (Cyrillic). It uses Flow Matching + Diffusion Transformer + Vocos (dim 1024, depth 22, 16 heads, vocab 65, 24 kHz sample rate), trained on the btsee/mbspeech_mn corpus (3,846 Mongolian speech samples) and outputs zero-shot synthesis from a short reference audio + language tag.

## Links

- HuggingFace: https://huggingface.co/btsee/oron-tts

## Features

- parameters: (not stated)
- voice_cloning: yes (zero-shot, reference audio + language tag)
- asr: no
- languages: Mongolian (Khalkha Cyrillic), Kazakh (Cyrillic)
- streaming: no
- license: MIT
- architecture: F5-TTS (OT-CFM + DiT + Vocos)
- dim: 1024
- depth: 22
- heads: 16
- vocab_size: 65
- sample_rate: 24000 Hz
- mel_bins: 100
- training_data: btsee/mbspeech_mn (3,846 Mongolian speech samples)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Mongolian, Kazakh
- streaming: ❌
- license: MIT

## Innovation

F5-TTS re-purposed for low-resource Cyrillic languages (Mongolian + Kazakh) — non-autoregressive flow-matching DiT over a tight 65-word vocab. Trained on a small (~3.8k sample) Mongolian corpus; the architecture is small enough that Khalkha Cyrillic and Kazakh Cyrillic share the same checkpoint via the `lang` tag at inference time.
