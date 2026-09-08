---
release_date: "September 6, 2026"
model_name: "rumik-oss 1"
category: "tts"
summary: "rumik ai — 3B multilingual TTS trained on under 70k hours, covering 22 Indic languages plus English with code-switching, description-conditioned delivery, and inline vocalization tags; 4 fixed voices, 24 kHz output."
slug: "rumik-oss-1"
---

# rumik-oss 1

rumik-oss 1 is a 3B multilingual text-to-speech model from rumik ai, trained on **fewer than 70,000 hours of speech** while performing competitively with existing TTS models. It covers **22 Indic languages in their native scripts and romanized forms plus English**, supporting both single-language and **code-switched** synthesis. Delivery is conditioned via `<description="...">` tags (tone, accent, pace), with inline vocalization control (`<laugh>`, `<chuckle>`, `<sigh>`). It extends CohereLabs/tiny-aya-fire with discrete speech tokens from the **mimi codec**: following the flattened codec-token formulation used in llama-mimi, text conditioning and audio generation share a single autoregressive sequence, predicting eight codebook tokens per frame before advancing, with the frozen mimi decoder reconstructing the 24 kHz waveform. The model ships with **4 fixed voices (Ira, Aisha, Siya, Zoya)** that perform equally well across all 22 languages; there is no zero-shot voice cloning. Licensed under Cohere's CC-BY-NC-4.0 with acceptable-use addendum (research and non-commercial use only).

## Links

- HuggingFace: https://huggingface.co/rumik-ai/rumik-oss-1
- Blog: https://rumik.ai/research/rumik-oss
- Demo: https://huggingface.co/spaces/rumik-ai/rumik-oss-1

## Features

- voice_cloning: no (4 fixed voices: Ira, Aisha, Siya, Zoya; speaker-conditioned base checkpoint released separately)
- asr: no
- languages: 22 Indic languages + English (native scripts and romanized; code-switching supported)
- license: Other
- parameters: 3B (3,381,533,697 BF16)
- architecture: CohereLabs/tiny-aya-fire backbone + flattened mimi codec tokens (8 codebooks/frame, llama-mimi formulation)
- audio_codec: kyutai/mimi (frozen decoder), 24 kHz output
- pronunciation: yes (native-script and romanized input forms)
- highlights: description-conditioned delivery (`<description>` tags), inline vocalizations (`<laugh>`/`<chuckle>`/`<sigh>`)
- variants: rumik-oss-1 (post-trained), rumik-oss-1-base (speaker-conditioned pre-post-training)

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: 22 Indic languages + English
- license: Other

## Innovation

Brings competitive multilingual TTS to 22 Indic languages with under 70k training hours, using a flattened mimi codec-token formulation (single autoregressive sequence for text conditioning + audio) on the tiny-aya-fire backbone. Code-switched synthesis, description-conditioned delivery, and inline vocalization tags are first-class capabilities, and its 4 voices perform equally well across all 22 languages — unusual, as most TTS voices are language-specific.
