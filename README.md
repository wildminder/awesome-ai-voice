# Awesome TTS & Voice Generation Models

A curated list of open-source Text-to-Speech (TTS) and voice cloning models. Models are sorted by release date (newest first).

![logo-tts2](https://github.com/user-attachments/assets/132b105b-b894-4150-bace-e84ef70ed2be)

---

## Table of Contents

- [Text-to-Speech (TTS) Models](#text-to-speech-tts-models)
- [Anything to Audio](#anything-to-audio)
- [Audio Restoration & Enhancement](#audio-restoration--enhancement)
- [Speech Recognition (ASR)](#speech-recognition-asr)
- [Audio Codecs & Tokenizers](#audio-codecs--tokenizers)
- [Audio Transcription Models](#audio-transcription-models)
- [Additional Resources](#additional-resources)

---

## Text-to-Speech (TTS) Models

### TTS Quick Comparison

| Model | Voice Cloning | ASR | Languages | Streaming | License |
| :--- | :---: | :---: | :--- | :---: | :--- |
| [Higgs Audio v3 TTS](#higgs-audio-v3-tts) | ✅ | ❌ | 102 | ✅ | ![Research Only][license-research-only] |
| [dots.tts](#dots-tts) | ✅ | ❌ | Multilingual | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Confucius4-TTS](#confucius4-tts) | ✅ | ❌ | 14 | ❌ | ![Apache 2.0][license-apache-2.0] |
| [WavTTS](#wavtts) | ✅ | ❌ | English, Chinese | ❌ | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [MOSS-TTS](#moss-tts) | ✅ | ❌ | 31 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Miso TTS](#misotts) | ✅ | ❌ | English | ❌ | ![MIT][license-mit] |
| [OronTTS](#oron-tts) | ✅ | ❌ | Mongolian, Kazakh | ❌ | ![MIT][license-mit] |
| [Supertonic 3](#supertonic-3) | ✅ | ❌ | 31 | ✅ | ![OpenRAIL-M][license-openrail-m] |
| [Scenema Audio](#scenema-audio) | ✅ | ❌ | English, German, French, Spanish, Italian, Portuguese, Japanese, Chinese, Korean, Russian, Arabic, Hindi, Swahili | ❌ | ![Unknown][license-unknown] |
| [Dramabox](#dramabox) | ✅ | ❌ | English | ❌ | ![Unknown][license-unknown] |
| [Sarashina2.2-TTS](#sarashina22-tts) | ✅ | ❌ | Japanese, English | ❌ | ![Research Only][license-research-only] |
| [LongCat-AudioDiT](#longcat-audiodit) | ✅ | ❌ | Chinese, English | ❌ | ![MIT][license-mit] |
| [Fish Audio S2 Pro](#fish-audio-s2-pro) | ✅ | ❌ | 80+ | ✅ | ![Research Only][license-research-only] |
| [LongCat-Next](#longcat-next) | ✅ | ✅ | Chinese, English | ✅ | ![MIT][license-mit] |
| [Voxtral-4B-TTS](#voxtral-4b-tts) | ✅ | ❌ | 9 | ✅ | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [Blue (Light Blue) TTS](#blue-tts) | ✅ | ❌ | Hebrew, English, Spanish, Italian, German | ❌ | ![MIT][license-mit] |
| [KittenTTS](#kittenTTS) | ✅ | ❌ | English, Multiple | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Ming-omni-tts](#ming-omni-tts) | ✅ | ❌ | Chinese, English | ❌ | ![Apache 2.0][license-apache-2.0] |
| [SoulX-Singer](#soulx-singer) | ✅ | ❌ | Mandarin, English, Cantonese | ✅ | ![Apache 2.0][license-apache-2.0] |
| [SoproTTS](#soprotts) | ✅ | ❌ | English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Qwen3-TTS](#qwen3-tts) | ✅ | ❌ | 10 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [TADA](#tada-1b) | ❌ | ❌ | English | ❌ | ![Unknown][license-unknown] |
| [Irodori-TTS-500M-v2](#irodori-tts-500m-v2) | ✅ | ❌ | Japanese | ❌ | ![MIT][license-mit] |
| [KugelAudio](#kugelaudio) | ✅ | ❌ | 23 European languages | ✅ | ![MIT][license-mit] |
| [LEMAS-TTS](#lemas-tts) | ✅ | ❌ | 10 | ❌ | ![Apache 2.0][license-apache-2.0] |
| [MioTTS-2.6B](#miotts-26b) | ✅ | ❌ | English, Japanese | ✅ | ![LFM][license-lfm] |
| [MOSS-TTS-Nano](#moss-tts-nano) | ✅ | ❌ | 20 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [NeuTTS](#neutts) | ✅ | ❌ | English, Spanish, German, French | ✅ | ![Apache 2.0][license-apache-2.0] |
| [OmniVoice](#omnivoice) | ✅ | ❌ | 600+ | ❌ | ![Apache 2.0][license-apache-2.0] |
| [T5Gemma-TTS](#t5gemma-tts) | ✅ | ❌ | English, Chinese, Japanese | ❌ | ![MIT][license-mit] |
| [TinyTTS](#tinytts) | ❌ | ❌ | English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [VoxCPM2](#voxcpm2) | ✅ | ❌ | 30 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [GLM-TTS](#glm-tts) | ✅ | ❌ | Chinese, English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [VibeVoice-Realtime](#vibevoice-realtime) | ✅ | ❌ | Multilingual | ✅ | ![MIT][license-mit] |
| [Fun-CosyVoice 3.0](#fun-cosyvoice-30) | ✅ | ❌ | 9 + 18+ Chinese dialects | ✅ | ![Apache 2.0][license-apache-2.0] |
| [LFM2-Audio-1.5B](#lfm2-audio-15b) | ✅ | ✅ | English | ✅ | ![LFM][license-lfm] |
| [IndexTTS2](#indextts2) | ✅ | ❌ | Chinese, English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Maya1](#maya1) | ✅ | ❌ | English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Step-Audio-EditX](#step-audio-editx) | ✅ | ❌ | Mandarin, English, Sichuanese, Cantonese, Japanese, Korean | ✅ | ![Apache 2.0][license-apache-2.0] |
| [VoxCPM](#voxcpm) | ✅ | ❌ | Chinese, English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [FireRedTTS2](#fireredtts2) | ✅ | ❌ | EN, ZH, JP, KO, FR, DE, RU | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Audio Flamingo 3 (AF3) / Audio Flamingo Next](#audio-flamingo-3) | ❌ | ✅ | Multi-lingual | ✅ | ![Apache 2.0][license-apache-2.0] |
| [ZipVoice](#zipvoice) | — | — | Chinese, English | — | ![Apache 2.0][license-apache-2.0] |
| [Fish Speech](#fish-speech) | ✅ | ❌ | 8 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Chatterbox](#chatterbox) | ✅ | ❌ | 23+ | ❌ | ![MIT][license-mit] |
| [Orpheus-TTS](#orpheus-tts) | ✅ | ❌ | Multilingual | ✅ | ![Apache 2.0][license-apache-2.0] |
| [MegaTTS3](#megatts3) | ✅ | ❌ | Chinese, English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Spark-TTS](#spark-tts) | ✅ | ❌ | Chinese, English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Step-Audio](#step-audio) | ✅ | ✅ | Chinese, English, Japanese | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Kokoro-82M](#kokoro-82m) | ✅ | ❌ | 8 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [KokoClone](#kokoclone) | ✅ | ❌ | 7 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [LuxTTS](#luxtts) | ✅ | ❌ | - | ✅ | ![Apache 2.0][license-apache-2.0] |
| [MiMo-Audio](#mimo-audio) | ✅ | ✅ | Multi-lingual | ✅ | ![Apache 2.0][license-apache-2.0] |
| [SoulX-Podcast](#soulx-podcast) | ✅ | ❌ | Mandarin, English, Cantonese, Sichuanese, Henanese | ✅ | ![Apache 2.0][license-apache-2.0] |
| [VieNeu-TTS](#vieneu-tts) | ✅ | ❌ | Vietnamese | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Dia](#dia) | ✅ | ❌ | English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [MeloTTS](#melotts) | ❌ | ❌ | English, Spanish, French, Chinese, Japanese, Korean | ❌ | ![MIT][license-mit] |
| [Kimi-Audio](#kimi-audio) | ✅ | ✅ | Multi-lingual | ✅ | ![MIT][license-mit]<br>![Apache 2.0][license-apache-2.0] |

<!-- MODEL:higgs-audio-v3-tts.md -->
<details id="higgs-audio-v3-tts">
<summary>Higgs Audio v3 TTS</summary>

### Higgs Audio v3 TTS

**Description:** Boson AI's flagship conversational TTS: an ~4B autoregressive decoder over interleaved text and audio tokens from the Higgs Tokenizer (8 codebooks at 25 fps / 24 kHz). Built for voice chat rather than narration, it covers 102 languages with zero-shot voice cloning and inline control over emotion, style, prosody, pauses, and sound effects.

**Release Date:** June 4, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 4B (BF16, 36 layers, hidden=2560, GQA 32/8) |
| **Architecture** | Autoregressive decoder (Qwen3-style) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 102 (85 with WER/CER <5, 17 between 5-10) |
| **Streaming** | ✅ |
| **Audio Output** | 24 kHz |
| **License** | ![Research Only][license-research-only] |

**Features:** Interleaved text/audio token modelling with a delay-pattern multi-codebook embedding/head: a single autoregressive stack emits both modalities and supports inline `<|category:value|>` control tags (emotion/style/sfx/prosody) inserted at any point in the target text.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/bosonai/higgs-audio-v3-tts-4b)

[![GitHub][link-github]](https://github.com/sgl-project/sglang-omni)

[![Blog][link-blog]](https://www.boson.ai/blog/higgs-audio-v3-tts)

[![Demo][link-demo]](https://huggingface.co/spaces/multimodalart/higgs-audio-v3-tts)


</details>
<!-- /MODEL:higgs-audio-v3-tts.md -->
<!-- MODEL:dots-tts.md -->
<details id="dots-tts">
<summary>dots.tts</summary>

### dots.tts

**Description:** dots.tts is a 2B-parameter fully continuous, end-to-end autoregressive TTS system from Rednote-HiLab. The backbone pairs a semantic encoder, an LLM, and an autoregressive flow-matching acoustic head over a 48 kHz AudioVAE, with no discrete tokens anywhere in the pipeline. It achieves the best average performance on Seed-TTS-Eval (WER 0.94 / 1.30 / 6.60 on zh / en / zh-hard) and the highest speaker similarity on a 24-language MiniMax multilingual benchmark, with broad cross-lingual voice cloning.

**Release Date:** June 3, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2B (semantic encoder + LLM + AR flow-matching acoustic head) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Languages** | Multilingual (24+ languages; zh / en focus) |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Sample Rate** | 48 kHz |
| **Tokenizer** | 48 kHz AudioVAE (continuous, no discrete tokens) |

**Features:** A fully continuous autoregressive pipeline that keeps generation in waveform-latent space end-to-end (no discrete-code phase), pairing an LLM-side semantic encoder with an autoregressive flow-matching acoustic head over a 48 kHz AudioVAE — yielding SOTA seed-TTS-Eval scores and the strongest speaker-similarity number (83.9 avg) on the 24-language MiniMax multilingual benchmark.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/rednote-hilab/dots.tts-base)

[![GitHub][link-github]](https://github.com/rednote-hilab/dots.tts)

[![Website][link-website]](https://rednote-hilab.github.io/dots.tts-demo/)

[![Demo][link-demo]](https://huggingface.co/spaces/rednote-hilab/dots.tts)


</details>
<!-- /MODEL:dots-tts.md -->
<!-- MODEL:confucius4-tts.md -->
<details id="confucius4-tts">
<summary>Confucius4-TTS</summary>

### Confucius4-TTS

**Description:** Confucius4-TTS is an LLM-based text-to-speech system from NetEase Youdao designed for multilingual and cross-lingual synthesis. It uses a speech encoder + LLM (Text2Semantic) + flow-matching Semantic2Acoustic architecture that allows zero-shot voice cloning without a required reference transcript and explicit cross-lingual voice transfer with unaccented output across languages. Covers Chinese, English, Japanese, Korean, German, French, Spanish, Indonesian, Italian, Thai, Portuguese, Russian, Malay, and Vietnamese with code-switching and emotion transfer.

**Release Date:** June 2, 2026

| Feature | Value |
|---------|-------|
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | 14 (zh, en, ja, ko, de, fr, es, id, vi, th, pt, it, ru, ms) |
| **Streaming** | ❌ |
| **License** | ![Unknown][license-unknown] |
| **Architecture** | speech encoder + LLM (T2S) + flow-matching head (S2A) |

**Features:** Cross-lingual voice transfer without accent drift: the same reference voice stays consistent when the speaker switches languages — backed by a speech encoder + LLM backbone pipeline (T2S) with a flow-matching acoustic decoder (S2A) and training that bundles 14 languages with code-switched, emotion-preserving decoding.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/netease-youdao/Confucius4-TTS)

[![GitHub][link-github]](https://github.com/netease-youdao/Confucius4-TTS)

[![Demo][link-demo]](https://confucius4-tts.youdao.com/gradio)


</details>
<!-- /MODEL:confucius4-tts.md -->
<!-- MODEL:wavtts.md -->
<details id="wavtts">
<summary>WavTTS</summary>

### WavTTS

**Description:** WavTTS is an end-to-end zero-shot TTS framework that synthesizes speech directly in the raw waveform space — explicitly skipping the intermediate mel-spectrogram, VAE-latent, or codec-token representations that most modern TTS stacks use. It is built on a flow-matching diffusion transformer (DiT) with waveform patchification, multi-scale mel-spectrogram supervision, and an optimized noise schedule. Forked from F5-TTS at the codebase level but replaces the whole acoustic pipeline.

**Release Date:** May 28, 2026

| Feature | Value |
|---------|-------|
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Languages** | English, Chinese |
| **Streaming** | ❌ |
| **License** | ![CC BY-NC 4.0][license-cc-by-nc-4.0]<br>![MIT][license-mit] |
| **Sample Rate** | 16 kHz |
| **Training Data** | Emilia |
| **Architecture** | Flow-matching DiT, raw waveform patchification, multi-scale mel supervision |
| **Training Steps** | 1.2M |

**Features:** Skip every intermediate waveform representation (no mel, no VAE, no codec tokens): a flow-matching DiT produces raw-waveform patches directly, supervised at multiple mel scales and an optimized noise schedule — yielding high-quality zero-shot TTS at 16 kHz from a single end-to-end stack.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/worstchan/WavTTS)

[![GitHub][link-github]](https://github.com/cwx-worst-one/WavTTS)

[![Demo][link-demo]](https://wavtts.github.io/)

[![Paper][link-paper]](https://arxiv.org/abs/2606.03455)


</details>
<!-- /MODEL:wavtts.md -->
<!-- MODEL:moss-tts.md -->
<details id="moss-tts">
<summary>MOSS-TTS</summary>

### MOSS-TTS

**Description:** MOSS-TTS is a production-grade Text-to-Speech foundation model developed by the OpenMOSS Team and MOSI.AI. The current public v1.5 release preserves the original 1.0 capabilities — zero-shot voice cloning, long-form speech generation, token-level duration control, Pinyin/IPA pronunciation supervision, multilingual synthesis, and code-switching — and extends multilingual continued training from 20 languages to **31 languages** including Cantonese, Dutch, Finnish, Hindi, Macedonian, Malay, Romanian, Swahili, Tagalog, Thai, and Vietnamese. v1.5 improves speaker similarity, reduces cloning variance on long-reference / short-text scenarios, follows punctuation-driven prosody more reliably, and adds explicit inline pause markers (e.g., `[pause 3.2s]`).

**Release Date:** May 25, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 8B (Delay), 1.7B (Local) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 31 (extended from v1.0's 20) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Max Duration** | 1 hour |
| **Pause Control** | yes (inline markers like `[pause 3.2s]`) |
| **Lang Tag Control** | yes (set `language=` in user message) |

**Features:** v1.5 widens MOSS-TTS from 20 → 31 languages with stronger per-language multilingual synthesis (control via a language tag in the user message), more stable cloning under long-reference / short-text conditions, punctuation-driven prosody that holds up across long sentences, and explicit inline pause tokens (`[pause 3.2s]`) for scripted narration control.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/OpenMOSS-Team/MOSS-TTS-v1.5)

[![GitHub][link-github]](https://github.com/OpenMOSS/MOSS-TTS)

[![Website][link-website]](https://mosi.cn/#models)

[![Paper][link-paper]](https://arxiv.org/abs/2603.18090)

[![Demo][link-demo]](https://studio.mosi.cn)


</details>
<!-- /MODEL:moss-tts.md -->
<!-- MODEL:misotts.md -->
<details id="misotts">
<summary>Miso TTS</summary>

### Miso TTS

**Description:** Miso TTS 8B is a text-to-speech model from Miso Labs built on the Sesame Conversational Speech Model (CSM) architecture. A large Llama-3.2-style backbone consumes text/audio-frame embeddings and predicts codebook 0 of the Mimi audio token stream, while a smaller 300M autoregressive audio decoder predicts codebooks 1–31 in codebook depth. The model is designed for high-quality conversational speech and voice continuation from a short prompt audio clip.

**Release Date:** May 21, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 8B (backbone llama-3.2-style) + 300M (audio decoder) = 8.3B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Languages** | English |
| **Streaming** | ❌ |
| **License** | ![Unknown][license-unknown] |
| **Architecture** | Sesame-style CSM (two transformer stack: backbone + audio decoder) |
| **Audio Tokenizer** | Mimi (32 codebooks, vocab 2051, max seq 2048) |
| **Library** | pytorch |

**Features:** A two-transformer Sesame-style CSM (Llama 8B backbone consumes text + audio frames and produces backbone codebook-0 prediction; a 300M audio decoder autoregresses over codebook depth via Mimi's 32-codebook stack) — letting the larger backbone spend capacity on linguistic / speaker conditioning while a leaner decoder handles fine-grained codebook-by-codebook generation.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/MisoLabs/MisoTTS)

[![GitHub][link-github]](https://github.com/MisoLabsAI/MisoTTS)

[![Website][link-website]](https://misolabs.ai)


</details>
<!-- /MODEL:misotts.md -->
<!-- MODEL:oron-tts.md -->
<details id="oron-tts">
<summary>OronTTS</summary>

### OronTTS

**Description:** OronTTS is a non-autoregressive text-to-speech model from `btsee`, an F5-TTS fork specialized for Mongolian (Khalkha Cyrillic) and Kazakh (Cyrillic). It uses Flow Matching + Diffusion Transformer + Vocos (dim 1024, depth 22, 16 heads, vocab 65, 24 kHz sample rate), trained on the btsee/mbspeech_mn corpus (3,846 Mongolian speech samples) and outputs zero-shot synthesis from a short reference audio + language tag.

**Release Date:** May 16, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | (not stated) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Languages** | Mongolian (Khalkha Cyrillic), Kazakh (Cyrillic) |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |
| **Architecture** | F5-TTS (OT-CFM + DiT + Vocos) |
| **Dim** | 1024 |
| **Depth** | 22 |
| **Heads** | 16 |
| **Vocab Size** | 65 |
| **Sample Rate** | 24000 Hz |
| **Mel Bins** | 100 |
| **Training Data** | btsee/mbspeech_mn (3,846 Mongolian speech samples) |

**Features:** F5-TTS re-purposed for low-resource Cyrillic languages (Mongolian + Kazakh) — non-autoregressive flow-matching DiT over a tight 65-word vocab. Trained on a small (~3.8k sample) Mongolian corpus; the architecture is small enough that Khalkha Cyrillic and Kazakh Cyrillic share the same checkpoint via the `lang` tag at inference time.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/btsee/oron-tts)


</details>
<!-- /MODEL:oron-tts.md -->
<!-- MODEL:supertonic-3.md -->
<details id="supertonic-3">
<summary>Supertonic 3</summary>

### Supertonic 3

**Description:** Supertonic 3 is the third-generation open-weight release from Supertone. It is a lightweight, on-device text-to-speech system that runs with ONNX Runtime entirely on the user's machine (no network, no API call) and ships as a Python SDK (`pip install supertonic`). Compared with the Supertonic 2 base (5 languages, 66 M params), v3 expands to **31 languages** and adds expression tags (`<laugh>`, `<breath>`, `<sigh>`), more stable reading on long utterances, and higher speaker similarity across the core language set.

**Release Date:** May 6, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | (not stated on card; Supertonic 2 baseline 66 M — likely similar or smaller weight class) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | 31 (expanded from Supertonic 2's 5) |
| **Streaming** | ✅ |
| **License** | ![OpenRAIL-M][license-openrail-m] |
| **On Device** | yes (ONNX Runtime, no cloud call) |
| **Expression Tags** | yes (`<laugh>`, `<breath>`, `<sigh>`) |

**Features:** A more compact on-device multilingual TTS: ONNX-Runtime inference everywhere, 31 languages from a single small open-weight encoder, and discrete expression tags that the decoder interprets inline — without a separate speaker-emotion control path or a cloud-rendered audio round-trip.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/Supertone/supertonic-3)

[![GitHub][link-github]](https://github.com/supertone-inc/supertonic)

[![Demo][link-demo]](https://huggingface.co/spaces/Supertone/supertonic-3)

[![PyPI][link-pypi]](https://pypi.org/project/supertonic/)


</details>
<!-- /MODEL:supertonic-3.md -->
<!-- MODEL:scenema-audio.md -->
<details id="scenema-audio">
<summary>Scenema Audio</summary>

### Scenema Audio

**Description:** Scenema Audio is a zero-shot expressive voice cloning and speech generation model from ScenemaAI. It is built on an audio diffusion transformer extracted from the audio branch of Lightricks' LTX 2.3 (a 22B audiovisual model) — keeping the in-the-wild acoustic quality the bigger model learned while specializing for speech output. Generation is **prompt-driven**: a `<speak>` tag carries a `voice` description, `gender`, optional `scene` (ambient audio around the voice), and `language`; an `<action>` tag shifts emotional state mid-generation. Action tags cover rage, grief, joy, fear, exhaustion; voice prompt can describe timbre/pitch/breathiness/rasp/resonance plus character archetypes ("Tony Soprano having a breakdown"). Supports zero-shot voice cloning from 10-20 seconds of reference audio with some emotional variability, automatic long-form narration by splitting text and maintaining voice continuity, and 13 multilingual built-ins.

**Release Date:** April 26, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | (audio diffusion transformer of LTX 2.3, weights ~9.8 GB bf16 / ~4.9 GB INT8 + ~6.7 GB pipeline) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | 13 (en, de, fr, es, it, pt, ja, zh, ko, ru, ar, hi, sw) |
| **Streaming** | ❌ |
| **License** | ![Unknown][license-unknown] |
| **Parent Model** | Lightricks LTX-2.3 (audio branch) |
| **Prompt Format** | `<speak voice=… gender=… scene=… language=…>` XML with `<action>` tag for shifting emotion |
| **Long Form Narration** | yes (auto-splits text while preserving voice continuity) |
| **Quantized** | yes (INT8 weights at ~4.9 GB, identical quality) |

**Features:** A standalone audio diffusion transformer extracted from a much bigger multimodal source: the model inherits how people actually sound in real scenes (angry, laughing, whispering, crying, exhausted, terrified) and exposes that capacity through a `<speak>` + `<action>` prompt interface — emotional state shifts within a single generation, instead of being a token-level or speaker-level conditioning problem.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/ScenemaAI/scenema-audio)

[![GitHub][link-github]](https://github.com/ScenemaAI/scenema-audio)

[![Website][link-website]](https://scenema.ai/audio)


</details>
<!-- /MODEL:scenema-audio.md -->
<!-- MODEL:dramabox.md -->
<details id="dramabox">
<summary>Dramabox</summary>

### Dramabox

**Description:** Dramabox is Resemble AI's expressive TTS, distributed under the LTX-2 Community License. It is an IC-LoRA fine-tune of the LTX-2.3 3.3B audio-only branch (Diffusion Transformer + flow matching), conditioned on Gemma 3 12B text embeddings. Generation is **prompt-driven**: speaker identity, emotion, delivery, laughs, sighs, breaths, pauses, and transitions are all expressed inside a natural-language description, with an optional 10-second voice reference that clones the target timbre.

**Release Date:** April 17, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 3.3B (LTX-2.3 audio backbone, IC-LoRA fine-tune) + 12B Gemma 3 text encoder (conditioning only) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | English |
| **Streaming** | ❌ |
| **License** | ![Unknown][license-unknown] |
| **Base Model** | Lightricks/LTX-2.3 (audio branch) |
| **Architecture** | DiT + flow matching, IC-LoRA fine-tune, Gemma 3 12B text embeddings |
| **Inference Time** | ~2.5 s / generation (warm server) |

**Features:** IC-LoRA fine-tune of LTX-2.3's audio branch leaves the heavy text-understanding work to Gemma 3 12B and lets the DiT do the expressive rendering — so what's normally multimodal-stage orchestration collapses into a single prompt-driven TTS where speaker identity, emotion, and delivery are encoded in the prompt itself, and the timbre comes from a 10-second voice reference when present.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/ResembleAI/Dramabox)

[![GitHub][link-github]](https://github.com/resemble-ai/DramaBox)

[![Demo][link-demo]](https://huggingface.co/spaces/ResembleAI/Dramabox)

[![Website][link-website]](https://www.resemble.ai/learn/models/dramabox)


</details>
<!-- /MODEL:dramabox.md -->
<!-- MODEL:sarashina22-tts.md -->
<details id="sarashina22-tts">
<summary>Sarashina2.2-TTS</summary>

### Sarashina2.2-TTS

**Description:** Sarashina2.2-TTS is a Japanese-centric text-to-speech system from SB Intuitions built on a large language model. It supports both Japanese and English, delivers strong pronunciation accuracy on Japanese text through large-scale end-to-end training, and reproduces a speaker's voice, speaking style, and acoustic characteristics from a short reference clip (zero-shot). Training data is sourced exclusively from legitimately acquired, properly licensed speech archives per the Sarashina Model NonCommercial License Agreement v2.0 (released April 24, 2026).

**Release Date:** April 16, 2026

| Feature | Value |
|---------|-------|
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | Japanese, English |
| **Streaming** | ❌ |
| **License** | ![Research Only][license-research-only] |
| **Base Model** | sbintuitions/sarashina2.2-0.5b-instruct-v0.1 |
| **Cross Lingual** | yes (Japanese ↔ English, code switching) |

**Features:** Japanese-optimized TTS fine-tuned on responsibly-licensed Japanese training corpora with explicit cross-lingual code-switching to English in a single utterance; reference audio carries speaking style and speaker identity together, so the same prompt yields narration, broadcast, conversation, or customer-service delivery without separate style conditioning.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/sbintuitions/sarashina2.2-tts)

[![GitHub][link-github]](https://github.com/sbintuitions/sarashina2.2-tts)

[![Paper][link-paper]](https://arxiv.org/abs/2606.25369)


</details>
<!-- /MODEL:sarashina22-tts.md -->
<!-- MODEL:longcat-audiodit.md -->
<details id="longcat-audiodit">
<summary>LongCat-AudioDiT</summary>

### LongCat-AudioDiT

**Description:** State-of-the-art diffusion-based TTS model operating directly in waveform latent space. Developed by Meituan's LongCat team, it requires only a Waveform VAE and Diffusion backbone, effectively mitigating compounding errors.

**Release Date:** March 30, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 1B / 3.5B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | Chinese, English |
| **Streaming** | ❌ |
| **Audio Output** | 24000 Hz |
| **License** | ![MIT][license-mit] |

**Features:** Adaptive Projection Guidance (APG) replaces traditional classifier-free guidance for elevated generation quality. Outperforms Seed-TTS on zero-shot voice cloning benchmarks.

**Links:**
[![GitHub][link-github]](https://github.com/meituan-longcat/LongCat-AudioDiT)

[![HuggingFace][link-huggingface]](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-1B)

[![HuggingFace][link-huggingface]](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-3.5B)


</details>
<!-- /MODEL:longcat-audiodit.md -->
<!-- MODEL:fish-audio-s2-pro.md -->
<details id="fish-audio-s2-pro">
<summary>Fish Audio S2 Pro</summary>

### Fish Audio S2 Pro

**Description:** Fish Audio S2 Pro is a leading text-to-speech model with fine-grained inline control of prosody and emotion. It combines reinforcement learning alignment with a dual-autoregressive architecture for high-quality speech synthesis.

**Release Date:** March 10, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | ~10 GB (BF16) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 80+ (Tier 1: En, Zh, Jp) |
| **Streaming** | ✅ |
| **License** | ![Research Only][license-research-only] |

**Links:**
[![GitHub][link-github]](https://github.com/fishaudio/fish-speech)

[![HuggingFace][link-huggingface]](https://huggingface.co/fishaudio/s2-pro)


</details>
<!-- /MODEL:fish-audio-s2-pro.md -->
<!-- MODEL:longcat-next.md -->
<details id="longcat-next">
<summary>LongCat-Next</summary>

### LongCat-Next

**Description:** Native multimodal foundation model by Meituan LongCat Team processing text, vision, and audio under a single autoregressive objective. Industrial-strength model with strong speech synthesis and voice cloning.

**Release Date:** March 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 3B (MoE A3B) |
| **Voice Cloning** | ✅ |
| **Asr** | ✅ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **Audio Output** | 24 kHz |
| **License** | ![MIT][license-mit] |

**Features:** Discrete Native Autoregression Paradigm (DiNA) unifying modalities in shared discrete token space. Combines visual understanding, generation, and audio processing in single model.

**Links:**
[![GitHub][link-github]](https://github.com/meituan-longcat/LongCat-Next)

[![HuggingFace][link-huggingface]](https://huggingface.co/meituan-longcat/LongCat-Next)


</details>
<!-- /MODEL:longcat-next.md -->
<!-- MODEL:voxtral-4b-tts.md -->
<details id="voxtral-4b-tts">
<summary>Voxtral-4B-TTS</summary>

### Voxtral-4B-TTS

**Description:** Frontier, open-weights text-to-speech model developed by Mistral AI. Designed to be fast, instantly adaptable, and produces lifelike speech with natural prosody and emotional range.

**Release Date:** March 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 4B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | 9 (En, Fr, Es, De, It, Pt, Nl, Ar, Hi) |
| **Streaming** | ✅ |
| **Audio Output** | 24 kHz |
| **License** | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/mistralai/Voxtral-4B-TTS-2603)

[![Demo][link-demo]](https://console.mistral.ai/build/audio/text-to-speech)

[![Blog][link-blog]](https://mistral.ai/news/voxtral-tts)


</details>
<!-- /MODEL:voxtral-4b-tts.md -->
<!-- MODEL:blue-tts.md -->
<details id="blue-tts">
<summary>Blue (Light Blue) TTS</summary>

### Blue (Light Blue) TTS

**Description:** BlueTTS (project page: lightbluetts.com) is a multilingual text-to-speech library. Built around slim ONNX graphs that run on **ONNX Runtime** with first-class CPU support and optional accelerators — **OpenVINO** (Intel), **CUDA ORT** (NVIDIA), **TensorRT**, and **ONNX Runtime** stock CPU. Targets five languages — **Hebrew, English, Spanish, Italian, German** — including inline mixed-language with XML-style tags in the text prompt. Inference is deliverable as a PyPI package (`blue-onnx`), a Rust crate, or directly from the pinned ONNX graphs on the HF Hub; the v2 release ships a slimmed opset-17 ONNX bundle (notmax123/blue-onnx-v2) that's intended for both FP32 production and the experimental INT8 weight-only fallback.

**Release Date:** February 27, 2026

| Feature | Value |
|---------|-------|
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ❌ |
| **Languages** | Hebrew, English, Spanish, Italian, German |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |
| **Runtime** | ONNX Runtime (stock CPU; OpenVINO / CUDA / TensorRT optional) |
| **Speed** | "fastest open-source TTS" (per project description) |
| **Graph Format** | ONNX opset 17 (slim, full-precision; experimental weight-only INT8 fallback) |
| **Distribution** | PyPI + HuggingFace + Rust |

**Features:** A **CPU-first multilingual TTS** that ships both slimmed ONNX graphs and a Python package where the same code path runs on **stock CPU ONNX Runtime** by default — *and* optionally accelerates on OpenVINO / CUDA ORT / TensorRT — so deployment doesn't gate on GPU availability. Languages include **Hebrew** (with explicit G2P normalization) — a comparatively rare open-source TTS target — plus standard European languages, all from MIT-licensed weights distributed via both Hugging Face and PyPI.

**Links:**
[![GitHub][link-github]](https://github.com/maxmelichov/BlueTTS)

[![HuggingFace][link-huggingface]](https://huggingface.co/notmax123/blue-onnx-v2)

[![PyPI][link-pypi]](https://pypi.org/project/blue-onnx/)

[![Website][link-website]](https://lightbluetts.com/)

[![Demo][link-demo]](https://huggingface.co/spaces/notmax123/BlueV2)


</details>
<!-- /MODEL:blue-tts.md -->
<!-- MODEL:kittenTTS.md -->
<details id="kittenTTS">
<summary>KittenTTS</summary>

### KittenTTS

**Description:** KittenTTS is an open-source realistic text-to-speech model designed for lightweight deployment. It is a state-of-the-art TTS model under 25MB with just 15 million parameters, running without GPU on any device.

**Release Date:** February 24, 2026 (v0.8.1)

| Feature | Value |
|---------|-------|
| **Parameters** | 15M-80M |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | English, Multiple |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/KittenML/KittenTTS)

[![HuggingFace][link-huggingface]](https://huggingface.co/spaces/KittenML/KittenTTS-Demo)


</details>
<!-- /MODEL:kittenTTS.md -->
<!-- MODEL:ming-omni-tts.md -->
<details id="ming-omni-tts">
<summary>Ming-omni-tts</summary>

### Ming-omni-tts

**Description:** Ming-omni-tts is a high-performance unified audio generation model in the Ming 2.0 series. It uses a custom 12.5 Hz continuous tokenizer and a Patch-by-Patch compression strategy that drives the LLM inference frame rate down to 3.1 Hz, enabling fine-grained control over speech rate, pitch, volume, emotion, and dialect (notably Cantonese at ~93 % accuracy). It supports 100+ premium built-in voices plus zero-shot voice design from natural-language prompts and is the first autoregressive model that jointly generates speech, ambient sound, and music in a single channel.

**Release Date:** February 11, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 16.8B (3B active, MoE; A3B) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English, Cantonese |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Features:** Patch-by-Patch compression drives the inference frame rate to 3.1 Hz, drastically cutting LLM-side latency for podcast-style audio while preserving naturalness. A custom 12.5 Hz continuous tokenizer plus a DiT head jointly produce speech, ambient sound, and music in a single output channel — an "in-the-scene" listening experience rather than TTS-on-top-of-a-track.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/inclusionAI/Ming-omni-tts-16.8B-A3B)

[![GitHub][link-github]](https://github.com/inclusionAI/Ming-omni-tts)

[![Website][link-website]](https://xqacmer.github.io/Ming-omni-tts/)


</details>
<!-- /MODEL:ming-omni-tts.md -->
<!-- MODEL:soulx-singer.md -->
<details id="soulx-singer">
<summary>SoulX-Singer</summary>

### SoulX-Singer

**Description:** SoulX-Singer is a high-fidelity, zero-shot singing voice synthesis model for generating realistic singing voices for unseen singers without fine-tuning.

**Release Date:** February 6, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Mandarin, English, Cantonese |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/Soul-AILab/SoulX-Singer)

[![HuggingFace][link-huggingface]](https://huggingface.co/spaces/Soul-AILab/SoulX-Singer)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2602.07803)


</details>
<!-- /MODEL:soulx-singer.md -->
<!-- MODEL:soprotts.md -->
<details id="soprotts">
<summary>SoproTTS</summary>

### SoproTTS

**Description:** SoproTTS is a lightweight English text-to-speech model with zero-shot voice cloning. It uses dilated convolutions (WaveNet-style) and lightweight cross-attention layers instead of the common Transformer architecture.

**Release Date:** February 4, 2026 (v1.5)

| Feature | Value |
|---------|-------|
| **Parameters** | 135M |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | English |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Rtf** | 0.05 (CPU M3) |
| **Training-Cost** | ~$100 |

**Links:**
[![GitHub][link-github]](https://github.com/samuel-vitorino/sopro)

[![HuggingFace][link-huggingface]](https://huggingface.co/samuel-vitorino/sopro)


</details>
<!-- /MODEL:soprotts.md -->
<!-- MODEL:qwen3-tts.md -->
<details id="qwen3-tts">
<summary>Qwen3-TTS</summary>

### Qwen3-TTS

**Description:** Qwen3-TTS is an open-source series of Text-to-Speech models developed by Alibaba Cloud. Supports stable, expressive, and streaming speech generation with free-form voice design.

**Release Date:** January 22, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 0.6B-1.7B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 10 (Chinese, English, Japanese, Korean, German, French, Russian, Portuguese, Spanish, Italian) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/QwenLM/Qwen3-TTS)

[![HuggingFace][link-huggingface]](https://huggingface.co/collections/Qwen/qwen3-tts)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2601.15621)


</details>
<!-- /MODEL:qwen3-tts.md -->
<!-- MODEL:tada-1b.md -->
<details id="tada-1b">
<summary>TADA</summary>

### TADA

**Description:** TADA is a unified speech-language model from Hume AI built around a *Text-Acoustic Dual-Alignment* tokenizer: for every text/subword token there is exactly one corresponding speech vector, so the audio stream stays 1:1 aligned with text. As a TTS model, each autoregressive step covers one text token and dynamically determines the duration and prosody for that token, breaking the fixed-frames-per-second constraint that drives most modern TTS backbones. As a speech-language model, it generates a text token and the speech for the preceding token in the same dual step.

**Release Date:** January 12, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 1B (Llama 3.2 1B base) |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | English |
| **Streaming** | ❌ |
| **License** | ![Unknown][license-unknown] |
| **Base Model** | meta-llama/Llama-3.2-1B |
| **Tokenization** | 1:1 text–acoustic dual alignment (one speech vector per text token) |
| **Dynamic Duration** | yes (each autoregressive step covers one text token, duration is determined per-token) |

**Features:** A dual-alignment speech–text tokenizer that decouples autoregression from a fixed audio frame rate: each text token owns exactly one speech vector, and the model synthesizes the *whole segment for that token* in one step, regardless of how long the spoken form is — eliminating transcript hallucination and the latency overhead of constant-frame-rate codecs while staying as compact as Llama 3.2 1B.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/HumeAI/tada-1b)

[![GitHub][link-github]](https://github.com/HumeAI/tada)

[![Demo][link-demo]](https://huggingface.co/spaces/HumeAI/tada)

[![PyPI][link-pypi]](https://pypi.org/project/hume-tada/)

[![Paper][link-paper]](https://arxiv.org/abs/2602.23068)

[![Blog][link-blog]](https://www.hume.ai/blog/opensource-tada)


</details>
<!-- /MODEL:tada-1b.md -->
<!-- MODEL:irodori-tts-500m-v2.md -->
<details id="irodori-tts-500m-v2">
<summary>Irodori-TTS-500M-v2</summary>

### Irodori-TTS-500M-v2

**Description:** Japanese Text-to-Speech model based on Rectified Flow Diffusion Transformer. Features emoji-based style and sound effect control by embedding emojis in input text for expressive speech generation.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 500M |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | Japanese |
| **Streaming** | ❌ |
| **Audio Output** | 48kHz waveform |
| **License** | ![MIT][license-mit] |

**Features:** **Key Feature:** Emoji annotation control - insert specific emojis into text to control speaking styles, emotions, and sound effects.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/Aratako/Irodori-TTS-500M-v2)

[![GitHub][link-github]](https://github.com/Aratako/Irodori-TTS)

[![Demo][link-demo]](https://huggingface.co/spaces/Aratako/Irodori-TTS-500M-v2-Demo)


</details>
<!-- /MODEL:irodori-tts-500m-v2.md -->
<!-- MODEL:kugelaudio.md -->
<details id="kugelaudio">
<summary>KugelAudio</summary>

### KugelAudio

**Description:** Open-source TTS for European languages with 7B parameters. Outperformed ElevenLabs in human preference testing.

**Release Date:** Early 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 23 European languages |
| **Streaming** | ✅ |
| **License** | ![MIT][license-mit] |

**Links:**
[![GitHub][link-github]](https://github.com/Kugelaudio/kugelaudio-open)

[![HuggingFace][link-huggingface]](https://huggingface.co/kugelaudio/kugelaudio-0-open)

[![Website][link-website]](https://kugelaudio.com)


</details>
<!-- /MODEL:kugelaudio.md -->
<!-- MODEL:lemas-tts.md -->
<details id="lemas-tts">
<summary>LEMAS-TTS</summary>

### LEMAS-TTS

**Description:** Part of the LEMAS (Large-scale Extensible Multilingual Audio Suite) project. Zero-shot multilingual TTS with 0.3B parameters supporting 10 languages with word-level precise editing capabilities.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 0.3B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 10 (zh/en/de/fr/es/pt/it/ru/id/vi) |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Special-Feature** | Word-level editing (LEMAS-Edit) |

**Features:** Built on 150,000+ hours of multilingual speech data with word-level timestamps. Includes LEMAS-Edit for precise word-level speech editing via masked token infilling.

**Links:**
[![Website][link-website]](https://lemas-project.github.io/LEMAS-Project/)

[![HuggingFace][link-huggingface]](https://huggingface.co/LEMAS-Project/LEMAS-TTS)

[![HuggingFace][link-huggingface]](https://huggingface.co/LEMAS-Project/LEMAS-Edit)


</details>
<!-- /MODEL:lemas-tts.md -->
<!-- MODEL:miotts-26b.md -->
<details id="miotts-26b">
<summary>MioTTS-2.6B</summary>

### MioTTS-2.6B

**Description:** Lightweight, high-speed LLM-based TTS model for English and Japanese with minimal resource usage.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2.6B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | English, Japanese |
| **Streaming** | ✅ |
| **License** | ![LFM][license-lfm] |
| **Rtf** | 0.135-0.145 |

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/Aratako/MioTTS-2.6B)

[![GitHub][link-github]](https://github.com/Aratako/MioTTS-Inference)


</details>
<!-- /MODEL:miotts-26b.md -->
<!-- MODEL:moss-tts-nano.md -->
<details id="moss-tts-nano">
<summary>MOSS-TTS-Nano</summary>

### MOSS-TTS-Nano

**Description:** Ultra-lightweight open-source multilingual speech generation model with only 0.1B parameters. Designed for realtime speech generation that runs directly on CPU without GPU.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 0.1B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | 20 |
| **Streaming** | ✅ |
| **Audio Output** | 48 kHz Stereo |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Features:** Pure autoregressive architecture with MOSS-Audio-Tokenizer-Nano. Compresses audio to 12.5 Hz token stream using RVQ with 16 codebooks. Runs on 4-core CPU.

**Links:**
[![GitHub][link-github]](https://github.com/OpenMOSS/MOSS-TTS-Nano)

[![HuggingFace][link-huggingface]](https://huggingface.co/OpenMOSS-Team/MOSS-TTS-Nano-100M)

[![Demo][link-demo]](https://huggingface.co/spaces/OpenMOSS-Team/MOSS-TTS-Nano)


</details>
<!-- /MODEL:moss-tts-nano.md -->
<!-- MODEL:neutts.md -->
<details id="neutts">
<summary>NeuTTS</summary>

### NeuTTS

**Description:** NeuTTS is a collection of open-source on-device TTS models with instant voice cloning. Built off LLM backbones with GGUF format quantizations for efficient on-device deployment.

**Release Date:** Early 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 360M (Air), 120M (Nano) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | English, Spanish, German, French |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **On-Device** | yes (GGUF quantizations) |

**Links:**
[![GitHub][link-github]](https://github.com/neuphonic/neutts)

[![HuggingFace][link-huggingface]](https://huggingface.co/neuphonic/neutts-air)

[![HuggingFace][link-huggingface]](https://huggingface.co/neuphonic/neutts-nano)


</details>
<!-- /MODEL:neutts.md -->
<!-- MODEL:omnivoice.md -->
<details id="omnivoice">
<summary>OmniVoice</summary>

### OmniVoice

**Description:** Massive multilingual zero-shot TTS model scaling to 600+ languages. Uses diffusion language model-style discrete non-autoregressive architecture with single-stage text-to-acoustic mapping.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 600+ |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Training-Data** | 581k hours |

**Features:** Simplified single-stage architecture vs conventional two-stage pipelines. Full-codebook random masking strategy with LLM initialization for superior intelligibility. Noise-robust prompt processing.

**Links:**
[![Website][link-website]](https://zhu-han.github.io/omnivoice/)

[![HuggingFace][link-huggingface]](https://huggingface.co/k2-fsa/OmniVoice)


</details>
<!-- /MODEL:omnivoice.md -->
<!-- MODEL:t5gemma-tts.md -->
<details id="t5gemma-tts">
<summary>T5Gemma-TTS</summary>

### T5Gemma-TTS

**Description:** Multilingual TTS model with voice cloning and duration control, built on the T5Gemma encoder-decoder LLM architecture. Supports batch generation for multiple audio variations.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2B-2B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ❌ |
| **Languages** | English, Chinese, Japanese |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |
| **Vram** | 7.6-10.6 GB |

**Features:** PM-RoPE positional encoding with XCodec2 audio codec. Low-VRAM options with CPU offloading. Batch inference efficiency with single encoder pass.

**Links:**
[![GitHub][link-github]](https://github.com/Aratako/T5Gemma-TTS)

[![HuggingFace][link-huggingface]](https://huggingface.co/Aratako/T5Gemma-TTS-2b-2b)

[![Demo][link-demo]](https://huggingface.co/spaces/Aratako/T5Gemma-TTS-Demo)


</details>
<!-- /MODEL:t5gemma-tts.md -->
<!-- MODEL:tinytts.md -->
<details id="tinytts">
<summary>TinyTTS</summary>

### TinyTTS

**Description:** The smallest English TTS model with only 1.6 million parameters. End-to-end neural network achieving ~53x real-time synthesis speed on CPU via ONNX optimization.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | ~3.4 MB (ONNX FP16) |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ❌ |
| **Languages** | English |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Features:** Ultra-compact architecture optimized for CPU-only deployment. Multi-platform support via Python and Node.js APIs. Works on laptops, edge devices, and embedded systems.

**Links:**
[![GitHub][link-github]](https://github.com/tronghieuit/tiny-tts)

[![HuggingFace][link-huggingface]](https://huggingface.co/backtracking/tiny-tts)

[![Demo][link-demo]](https://huggingface.co/spaces/backtracking/tiny-tts-demo)


</details>
<!-- /MODEL:tinytts.md -->
<!-- MODEL:voxcpm2.md -->
<details id="voxcpm2">
<summary>VoxCPM2</summary>

### VoxCPM2

**Description:** OpenBMB's next-generation tokenizer-free diffusion autoregressive TTS model with 2 billion parameters. Supports 30 languages with automatic detection, voice design from text descriptions, and high-fidelity voice cloning.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 30 (+ 9 Chinese dialects) |
| **Streaming** | ✅ |
| **Audio Output** | 48 kHz |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Features:** Tokenizer-free design with LocEnc → TSLM → RALM → LocDiT pipeline. Built-in super-resolution via AudioVAE V2 for 48kHz output.

**Links:**
[![GitHub][link-github]](https://github.com/OpenBMB/VoxCPM)

[![HuggingFace][link-huggingface]](https://huggingface.co/openbmb/VoxCPM2)

[![Demo][link-demo]](https://huggingface.co/spaces/OpenBMB/VoxCPM-Demo)


</details>
<!-- /MODEL:voxcpm2.md -->
<!-- MODEL:glm-tts.md -->
<details id="glm-tts">
<summary>GLM-TTS</summary>

### GLM-TTS

**Description:** High-quality TTS synthesis system based on LLMs from ZhipuAI, supporting zero-shot voice cloning with Multi-Reward Reinforcement Learning.

**Release Date:** December 11, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/zai-org/GLM-TTS)

[![HuggingFace][link-huggingface]](https://huggingface.co/zai-org/GLM-TTS)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2512.14291)


</details>
<!-- /MODEL:glm-tts.md -->
<!-- MODEL:vibevoice-realtime.md -->
<details id="vibevoice-realtime">
<summary>VibeVoice-Realtime</summary>

### VibeVoice-Realtime

**Description:** Real-time TTS model from Microsoft with streaming text input and ultra-low latency (~300ms).

**Release Date:** December 3, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.5B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Multilingual |
| **Streaming** | ✅ |
| **License** | ![MIT][license-mit] |
| **Max Duration** | ~10 minutes |

**Links:**
[![GitHub][link-github]](https://github.com/microsoft/VibeVoice)

[![HuggingFace][link-huggingface]](https://huggingface.co/microsoft/VibeVoice-Realtime-0.5B)


</details>
<!-- /MODEL:vibevoice-realtime.md -->
<!-- MODEL:fun-cosyvoice-30.md -->
<details id="fun-cosyvoice-30">
<summary>Fun-CosyVoice 3.0</summary>

### Fun-CosyVoice 3.0

**Description:** Advanced TTS system based on LLMs for zero-shot multilingual speech synthesis from FunAudioLLM.

**Release Date:** December 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.5B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 9 + 18+ Chinese dialects |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/FunAudioLLM/CosyVoice)

[![HuggingFace][link-huggingface]](https://huggingface.co/FunAudioLLM/Fun-CosyVoice3-0.5B-2512)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2505.17589)


</details>
<!-- /MODEL:fun-cosyvoice-30.md -->
<!-- MODEL:lfm2-audio-15b.md -->
<details id="lfm2-audio-15b">
<summary>LFM2-Audio-1.5B</summary>

### LFM2-Audio-1.5B

**Description:** Liquid AI's first end-to-end audio foundation model with low latency and real-time conversation.

**Release Date:** November 28, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 1.5B |
| **Voice Cloning** | ✅ |
| **Asr** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | English |
| **Streaming** | ✅ |
| **License** | ![LFM][license-lfm] |

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/LiquidAI/LFM2-Audio-1.5B)

[![Website][link-website]](https://docs.liquid.ai/lfm)


</details>
<!-- /MODEL:lfm2-audio-15b.md -->
<!-- MODEL:indextts2.md -->
<details id="indextts2">
<summary>IndexTTS2</summary>

### IndexTTS2

**Description:** AI-Enhanced Text-to-Speech System with Intelligent Optimization and self-learning capabilities.

**Release Date:** November 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Multi-Speaker** | yes (1-4 speakers) |

**Links:**
[![GitHub][link-github]](https://github.com/xuchenxu168/Comfyui-Index-TTS2)

[![HuggingFace][link-huggingface]](https://huggingface.co/IndexTeam/IndexTTS-2)


</details>
<!-- /MODEL:indextts2.md -->
<!-- MODEL:maya1.md -->
<details id="maya1">
<summary>Maya1</summary>

### Maya1

**Description:** State-of-the-art speech model for expressive voice generation with natural language voice control.

**Release Date:** November 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 3B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | English (Multi-accent) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/maya-research/maya1)

[![Website][link-website]](https://mayaresearch.ai)


</details>
<!-- /MODEL:maya1.md -->
<!-- MODEL:step-audio-editx.md -->
<details id="step-audio-editx">
<summary>Step-Audio-EditX</summary>

### Step-Audio-EditX

**Description:** 3B-parameter LLM-based RL audio model specialized in expressive and iterative audio editing.

**Release Date:** November 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 3B (4B BF16) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Mandarin, English, Sichuanese, Cantonese, Japanese, Korean |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/stepfun-ai/Step-Audio-EditX)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2511.03601)


</details>
<!-- /MODEL:step-audio-editx.md -->
<!-- MODEL:voxcpm.md -->
<details id="voxcpm">
<summary>VoxCPM</summary>

### VoxCPM

**Description:** Tokenizer-free TTS system for context-aware speech generation and true-to-life voice cloning.

**Release Date:** September 16, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 640M-800M |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/OpenBMB/VoxCPM)

[![HuggingFace][link-huggingface]](https://huggingface.co/openbmb/VoxCPM-0.5B)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2509.24650)


</details>
<!-- /MODEL:voxcpm.md -->
<!-- MODEL:fireredtts2.md -->
<details id="fireredtts2">
<summary>FireRedTTS2</summary>

### FireRedTTS2

**Description:** Long-form streaming TTS system for multi-speaker dialogue generation with stable, natural speech.

**Release Date:** September 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | EN, ZH, JP, KO, FR, DE, RU |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Multi-Speaker** | yes (4 speakers) |
| **Max Duration** | 3 minutes |

**Links:**
[![GitHub][link-github]](https://github.com/FireRedTeam/FireRedTTS2)

[![HuggingFace][link-huggingface]](https://huggingface.co/FireRedTeam/FireRedTTS2)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2509.02020)


</details>
<!-- /MODEL:fireredtts2.md -->
<!-- MODEL:audio-flamingo-3.md -->
<details id="audio-flamingo-3">
<summary>Audio Flamingo 3 (AF3) / Audio Flamingo Next</summary>

### Audio Flamingo 3 (AF3) / Audio Flamingo Next

**Description:** NVIDIA ADLR's fully open-source Large Audio Language Model with state-of-the-art audio understanding. Audio Flamingo Next (AF-Next) is the latest generation featuring stronger general audio understanding, longer context support, and timestamp-grounded reasoning.

**Release Date:** July 2025 (AF3), 2026 (AF-Next)

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Voice Cloning** | ❌ |
| **Asr** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Multi-lingual |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Context** | Up to 30 minutes |

**Features:** **Key Innovation (AF-Next):** Staged curriculum training with GRPO-based RL post-training. Three specialized checkpoints: Instruct, Think (reasoning), and Captioner. Temporal Audio Chain-of-Thought grounding intermediate reasoning to timestamps.

**Links:**
[![GitHub][link-github]](https://github.com/NVIDIA/audio-flamingo)

[![HuggingFace][link-huggingface]](https://huggingface.co/nvidia/audio-flamingo-3)

[![Website][link-website]](https://afnext-umd-nvidia.github.io/)


</details>
<!-- /MODEL:audio-flamingo-3.md -->
<!-- MODEL:zipvoice.md -->
<details id="zipvoice">
<summary>ZipVoice</summary>

### ZipVoice

**Description:** Fast and high-quality zero-shot TTS models based on flow matching.

**Release Date:** June 16, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 123M |
| **Languages** | Chinese, English |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Zero-Shot-Cloning** | yes |
| **Dialogue** | yes |

**Links:**
[![GitHub][link-github]](https://github.com/k2-fsa/ZipVoice)

[![Website][link-website]](https://zipvoice.github.io/)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2506.13053)


</details>
<!-- /MODEL:zipvoice.md -->
<!-- MODEL:fish-speech.md -->
<details id="fish-speech">
<summary>Fish Speech</summary>

### Fish Speech

**Description:** State-of-the-art open source TTS and voice cloning model that generates natural, realistic, and emotionally rich speech.

**Release Date:** May 31, 2025 (v1.5.1)

| Feature | Value |
|---------|-------|
| **Parameters** | 4B (S1), 0.5B (S1-mini) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 8 (EN, JP, KO, ZH, FR, DE, AR, ES) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Rtf** | ~1:7 |

**Links:**
[![GitHub][link-github]](https://github.com/fishaudio/fish-speech)

[![Website][link-website]](https://fish.audio/)


</details>
<!-- /MODEL:fish-speech.md -->
<!-- MODEL:chatterbox.md -->
<details id="chatterbox">
<summary>Chatterbox</summary>

### Chatterbox

**Description:** Family of SOTA open-source TTS models by Resemble AI, covering a single-language English line plus a multilingual V3 release that brings broader language coverage, more consistent speaker similarity, reduced hallucinations, and more natural conversational speech across 23+ languages.

**Release Date:** April 24, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 500M (Llama backbone, 0.5B) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 23+ |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |

**Features:** First open-source TTS model with explicit **emotion exaggeration control**, plus an alignment-informed inference pipeline and a watermarked decoder. Multilingual V3 narrows the quality gap to closed systems like ElevenLabs on cross-language voice cloning while staying under 1B parameters.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/ResembleAI/chatterbox)

[![GitHub][link-github]](https://github.com/resemble-ai/chatterbox)

[![Website][link-website]](https://resemble.ai/)

[![Demo][link-demo]](https://huggingface.co/spaces/ResembleAI/Chatterbox-Multilingual-TTS-V3)


</details>
<!-- /MODEL:chatterbox.md -->
<!-- MODEL:orpheus-tts.md -->
<details id="orpheus-tts">
<summary>Orpheus-TTS</summary>

### Orpheus-TTS

**Description:** SOTA open-source TTS built on Llama-3b backbone demonstrating emergent capabilities of LLMs for speech synthesis.

**Release Date:** April 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 3B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Multilingual |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/canopyai/Orpheus-TTS)

[![Website][link-website]](https://canopylabs.ai/model-releases)


</details>
<!-- /MODEL:orpheus-tts.md -->
<!-- MODEL:megatts3.md -->
<details id="megatts3">
<summary>MegaTTS3</summary>

### MegaTTS3

**Description:** Advanced zero-shot speech synthesis with Sparse Alignment Enhanced Latent Diffusion Transformer.

**Release Date:** March 22, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.45B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/bytedance/MegaTTS3)

[![HuggingFace][link-huggingface]](https://huggingface.co/spaces/ByteDance/MegaTTS3)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2502.18924)


</details>
<!-- /MODEL:megatts3.md -->
<!-- MODEL:spark-tts.md -->
<details id="spark-tts">
<summary>Spark-TTS</summary>

### Spark-TTS

**Description:** Efficient LLM-Based TTS Model with Single-Stream Decoupled Speech Tokens, built on Qwen2.5.

**Release Date:** March 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.5B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/SparkAudio/Spark-TTS)

[![HuggingFace][link-huggingface]](https://huggingface.co/SparkAudio/Spark-TTS-0.5B)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2503.01710)


</details>
<!-- /MODEL:spark-tts.md -->
<!-- MODEL:step-audio.md -->
<details id="step-audio">
<summary>Step-Audio</summary>

### Step-Audio

**Description:** Production-ready open-source framework for intelligent speech interaction with unified speech comprehension and generation.

**Release Date:** February 17, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 130B (Chat), 3B (TTS) |
| **Voice Cloning** | ✅ |
| **Asr** | ✅ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English, Japanese |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/stepfun-ai/Step-Audio)

[![HuggingFace][link-huggingface]](https://huggingface.co/stepfun-ai)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2502.11946)


</details>
<!-- /MODEL:step-audio.md -->
<!-- MODEL:kokoro-82m.md -->
<details id="kokoro-82m">
<summary>Kokoro-82M</summary>

### Kokoro-82M

**Description:** Kokoro is an open-weight Text-to-Speech model with 82 million parameters. Despite its lightweight architecture, it delivers comparable quality to larger models while being significantly faster and more cost-efficient. With Apache-licensed weights, Kokoro can be deployed anywhere from production environments to personal projects.

**Release Date:** January 27, 2025 (v1.0)

| Feature | Value |
|---------|-------|
| **Parameters** | 82M |
| **Architecture** | StyleTTS 2, ISTFTNet |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 8 (54 voices) |
| **Streaming** | ✅ |
| **Cost** | <$0.06 per hour of audio |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/hexgrad/kokoro)

[![HuggingFace][link-huggingface]](https://huggingface.co/hexgrad/Kokoro-82M)

[![Demo][link-demo]](https://hf.co/spaces/hexgrad/Kokoro-TTS)


</details>
<!-- /MODEL:kokoro-82m.md -->
<!-- MODEL:kokoclone.md -->
<details id="kokoclone">
<summary>KokoClone</summary>

### KokoClone

**Description:** KokoClone is a fast, real-time compatible multilingual voice cloning system built on top of Kokoro-ONNX. It enables users to type text in multiple languages, provide a short 3-10 second reference audio clip, and instantly generate speech in that same voice.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 82M (Base: Kokoro-ONNX) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | 7 (En, Hi, Fr, Ja, Zh, It, Pt, Es) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/Ashish-Patnaik/kokoclone)

[![HuggingFace][link-huggingface]](https://huggingface.co/PatnaikAshish/kokoclone)

[![Demo][link-demo]](https://huggingface.co/spaces/PatnaikAshish/kokoclone)


</details>
<!-- /MODEL:kokoclone.md -->
<!-- MODEL:luxtts.md -->
<details id="luxtts">
<summary>LuxTTS</summary>

### LuxTTS

**Description:** Lightweight ZipVoice-based TTS model for high quality voice cloning at speeds exceeding 150x realtime.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | - |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Rtf** | 150x |
| **Vram** | 1GB |

**Links:**
[![GitHub][link-github]](https://github.com/ysharma3501/LuxTTS)

[![HuggingFace][link-huggingface]](https://huggingface.co/YatharthS/LuxTTS)


</details>
<!-- /MODEL:luxtts.md -->
<!-- MODEL:mimo-audio.md -->
<details id="mimo-audio">
<summary>MiMo-Audio</summary>

### MiMo-Audio

**Description:** Audio Language Model by Xiaomi functioning as a Few-Shot Learner with SOTA audio understanding.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Voice Cloning** | ✅ |
| **Asr** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Multi-lingual |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/XiaomiMiMo/MiMo-Audio)

[![HuggingFace][link-huggingface]](https://huggingface.co/collections/XiaomiMiMo/mimo-audio-68cc7202692c27dae881cce0)


</details>
<!-- /MODEL:mimo-audio.md -->
<!-- MODEL:soulx-podcast.md -->
<details id="soulx-podcast">
<summary>SoulX-Podcast</summary>

### SoulX-Podcast

**Description:** SOTA Multi-Speaker TTS model for generating realistic long-form podcasts with dialectal diversity.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Mandarin, English, Cantonese, Sichuanese, Henanese |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Max Duration** | 90+ minutes |

**Links:**
[![GitHub][link-github]](https://github.com/Soul-AILab/SoulX-Podcast)

[![HuggingFace][link-huggingface]](https://huggingface.co/collections/Soul-AILab/soulx-podcast)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2510.23541)


</details>
<!-- /MODEL:soulx-podcast.md -->
<!-- MODEL:vieneu-tts.md -->
<details id="vieneu-tts">
<summary>VieNeu-TTS</summary>

### VieNeu-TTS

**Description:** Advanced on-device Vietnamese TTS model with instant voice cloning from 3-5 seconds of reference audio.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.3B-0.6B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ❌ |
| **Languages** | Vietnamese |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/pnnbao-ump/VieNeu-TTS)

[![GitHub][link-github]](https://github.com/pnnbao97/VieNeu-TTS)


</details>
<!-- /MODEL:vieneu-tts.md -->
<!-- MODEL:dia.md -->
<details id="dia">
<summary>Dia</summary>

### Dia

**Description:** 1.6B parameter TTS model by Nari Labs for generating ultra-realistic dialogue in one pass.

**Release Date:** June 27, 2024

| Feature | Value |
|---------|-------|
| **Parameters** | 1.6B |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | English |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/nari-labs/dia)

[![HuggingFace][link-huggingface]](https://huggingface.co/nari-labs/Dia-1.6B-0626)


</details>
<!-- /MODEL:dia.md -->
<!-- MODEL:melotts.md -->
<details id="melotts">
<summary>MeloTTS</summary>

### MeloTTS

**Description:** MeloTTS is a high-quality multi-lingual text-to-speech library from MyShell.ai in collaboration with MIT, supporting English (American, British, Indian, Australian, and a default accent), Spanish, French, Chinese (with mixed Chinese–English capability), Japanese, and Korean. Built on VITS / VITS2 / Bert-VITS2 family work and packaged with both a Python API and a Web UI, it runs fast enough for CPU real-time inference.

**Release Date:** February 19, 2024

| Feature | Value |
|---------|-------|
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Languages** | English (American, British, Indian, Australian, Default), Spanish, French, Chinese, Japanese, Korean |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |
| **Base** | VITS / VITS2 / Bert-VITS2 family |
| **Mixed Chinese English** | yes |

**Features:** A multi-accent multilingual TTS library that ships both a Python API and a Web UI on top of the VITS-style architecture, with explicit English-accent coverage (American, British, Indian, Australian, Default) and mixed Chinese–English output — designed for fast CPU real-time inference without requiring GPU servers.

**Links:**
[![GitHub][link-github]](https://github.com/myshell-ai/MeloTTS)

[![HuggingFace][link-huggingface]](https://huggingface.co/myshell-ai)


</details>
<!-- /MODEL:melotts.md -->
<!-- MODEL:kimi-audio.md -->
<details id="kimi-audio">
<summary>Kimi-Audio</summary>

### Kimi-Audio

**Description:** Open-source audio foundation model by Moonshot AI for audio understanding, generation, and conversation.

**Release Date:** 2024

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Voice Cloning** | ✅ |
| **Asr** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Multi-lingual |
| **Streaming** | ✅ |
| **License** | ![MIT][license-mit]<br>![Apache 2.0][license-apache-2.0] |

**Links:**
[![GitHub][link-github]](https://github.com/MoonshotAI/Kimi-Audio)

[![HuggingFace][link-huggingface]](https://huggingface.co/moonshotai/Kimi-Audio-7B)


</details>
<!-- /MODEL:kimi-audio.md -->

---

## Anything to Audio

Models that can generate audio from multiple input modalities (video, text, image, audio). These are unified frameworks for multimodal audio synthesis.

### Anything to Audio Quick Comparison

| Model | Text | Video | Audio | Max Duration | Sample Rate | License |
| :--- | :---: | :---: | :---: | :--- | :--- | :--- |
| [Nemotron-Labs-Audex-30B-A3B](#nemotron-labs-audex-30b-a3b) | ✅ | ❌ | ✅ | — | — | ![NVIDIA NC][license-nvidia-noncommercial] |
| [MOSS-SoundEffect](#moss-soundeffect) | ✅ | — | — | 30 s | 48 kHz | ![Apache 2.0][license-apache-2.0] |
| [Omni2Sound (Omni2Audio)](#omni2sound) | ✅ | ✅ | ✅ | — | — | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [ControlFoley](#controlfoley) | ✅ | ✅ | ✅ | — | (not stated) | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [Woosh](#woosh) | ✅ | ✅ | — | — | — | ![Apache 2.0][license-apache-2.0] |
| [Uni-MoE (Audio)](#uni-moe-audio-any2audio) | ✅ | ✅ | — | — | — | ![Apache 2.0][license-apache-2.0] |
| [AudioX / Audio-Omni](#audiox) | ✅ | ✅ | ✅ | — | — | ![Apache 2.0][license-apache-2.0]<br>![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [HunyuanVideo-Foley](#hunyuanvideo-foley) | ✅ | ✅ | — | — | 48 kHz | ![Unknown][license-unknown] |
| [PrismAudio](#prismaudio) | — | ✅ | — | — | — | ![Apache 2.0][license-apache-2.0] |
| [ThinkSound](#thinksound) | ✅ | — | ✅ | — | — | ![Apache 2.0][license-apache-2.0] |
| [MMAudio](#mmaudio) | ✅ | ✅ | — | — | — | ![Apache 2.0][license-apache-2.0] |

<!-- MODEL:nemotron-labs-audex-30b-a3b.md -->
<details id="nemotron-labs-audex-30b-a3b">
<summary>Nemotron-Labs-Audex-30B-A3B</summary>

### Nemotron-Labs-Audex-30B-A3B

**Description:** Nemotron-Labs-Audex-30B-A3B is NVIDIA's unified audio-text LLM — a single model that both **understands** audio (audio QA, speech recognition, speech translation) and **generates** audio (text-to-speech, text-to-audio, speech-to-speech). Built on Nemotron-Cascade-2-30B-A3B (text-only MoE: 30B parameters, 3B active), Audex extends the vocabulary with **discrete audio tokens** for speech / general-audio output and adds an **audio encoder** for speech / general-audio input. Runs in *thinking* and *instruct* (non-thinking) modes and supports up to a 1M-token context length — preserving text-reasoning, alignment, knowledge, long-context, and agentic capabilities of the backbone while gaining audio tasks.

**Release Date:** July 6, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 30B MoE (3B active) |
| **Modalities** | audio (input and output) |
| **Audio Understanding** | yes |
| **Asr** | ✅ |
| **Speech Translation** | yes |
| **Text To Speech** | yes |
| **Text To Audio** | yes |
| **Speech To Speech Generation** | yes |
| **Voice Cloning** | ❌ |
| **License** | ![NVIDIA NC][license-nvidia-noncommercial] |
| **Languages** | English |
| **Modes** | thinking, instruct (non-thinking) |
| **Context Length** | 1M tokens |
| **Template** | ChatML (with `<think>…</think>` for thinking mode) |
| **Inference** | vLLM 0.20.0 (recommended) or transformers >= 4.53.0 (mamba-ssm + causal-conv1d required) |

**Features:** First-class audio I/O for a 30B/3B-active text LLM: extended vocabulary with **discrete audio tokens** for outputting speech and general audio, plus an **audio encoder** for input — so the same backbone keeps its strong text reasoning (alignment, knowledge, long-context) and adds ASR + speech translation + TTS + audio generation + S2S without retraining. The MoE form (30B routes, 3B active) keeps inference tractable for a single pipeline that does both.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/nvidia/Nemotron-Labs-Audex-30B-A3B)

[![Paper][link-paper]](https://arxiv.org/abs/2607.05196)

[![Collection][link-collection]](https://huggingface.co/collections/nvidia/nemotron-labs-audex)


</details>
<!-- /MODEL:nemotron-labs-audex-30b-a3b.md -->
<!-- MODEL:moss-soundeffect.md -->
<details id="moss-soundeffect">
<summary>MOSS-SoundEffect</summary>

### MOSS-SoundEffect

**Description:** MOSS-SoundEffect is the dedicated **text-to-sound** model in the OpenMOSS / MOSI.AI MOSS-TTS family. It turns natural-language captions into high-fidelity non-speech audio (ambience, urban scenes, creatures, human actions, and short music-like clips).

**Release Date:** May 25, 2026

| Feature | Value |
|---------|-------|
| **Type** | Text-to-Sound / SFX generation |
| **Conditioning** | Text |
| **Max Duration** | 30 seconds |
| **Sample Rate** | 48 kHz |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Architecture** | DiT + Flow Matching + DAC VAE + Qwen3 text encoder |
| **Parameters** | 1.3B (DiT variant 1.3B) |
| **Languages** | English, Chinese |
| **Inference Defaults** | 100 flow-match steps, cfg 4.0, sigma_shift 5.0 |
| **Library** | diffusers |

**Features:** Replaces the discrete-token autoregressive v1 (which bottlenecked on vocabulary) with a continuous-latent DiT + Flow Matching paired with a DAC VAE — yielding **30 s** stable audio, bilingual English + Chinese prompts, and a clean CFG/sigma-shift inference schedule (cfg 4.0, shift 5.0) that works straight out of the box on the `diffusers` library.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/OpenMOSS-Team/MOSS-SoundEffect-v2.0)

[![HuggingFace][link-huggingface]](https://huggingface.co/OpenMOSS-Team/MOSS-SoundEffect (legacy v1 checkpoint))

[![GitHub][link-github]](https://github.com/OpenMOSS/MOSS-TTS/tree/main/moss_soundeffect_v2)


</details>
<!-- /MODEL:moss-soundeffect.md -->
<!-- MODEL:omni2sound.md -->
<details id="omni2sound">
<summary>Omni2Sound (Omni2Audio)</summary>

### Omni2Sound (Omni2Audio)

**Description:** Omni2Sound — also written **Omni2Audio** on the project page — is a unified VT2A / V2A / T2A framework and a CVPR 2026 Highlight. A single Diffusion Transformer (DiT) backbone with a decoupled two-branch conditioning design:

**Release Date:** April 20, 2026

| Feature | Value |
|---------|-------|
| **Conditioning** | Text / Video / Text+Video |
| **Modalities** | Video, Audio |
| **Asr** | ❌ |
| **Voice Cloning** | ❌ |
| **Text** | ✅ |
| **Video** | ✅ |
| **Image** | ❌ |
| **Audio** | ✅ |
| **License** | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| **Tasks** | VT2A, V2A, T2A (single model) |
| **Architecture** | DiT + decoupled Semantic / Temporal branches + 3-stage progressive training |
| **Pipeline Tag** | text-to-audio |

**Features:** One **single model** that is SOTA on three distinct tasks (VT2A, V2A, T2A) without a separate model per mode — decoupled semantic and temporal conditioning let the same DiT backbone handle text-only, video-only, and text+video conditioning by cleanly omitting the missing modality rather than padding it, which is what most prior unified VA models had to do.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/Dalision/Omni2Sound)

[![GitHub][link-github]](https://github.com/omni2sound/Omni2Sound)

[![Website][link-website]](https://omni2sound.github.io/)

[![Paper][link-paper]](https://arxiv.org/abs/2601.02731)

[![Benchmark][link-benchmark]](https://huggingface.co/datasets/Dalision/Omni2Sound_Benchmark)


</details>
<!-- /MODEL:omni2sound.md -->
<!-- MODEL:controlfoley.md -->
<details id="controlfoley">
<summary>ControlFoley</summary>

### ControlFoley

**Description:** ControlFoley (Xiaomi MiLM Plus) is a unified video-to-audio generation model built to handle the *cross-modal conflict* problem — the situation where a video shows a dog barking but the text prompt asks for a cat — by routing which modality controls what at inference time. It supports text-controlled video→audio, audio-controlled video→audio, and text+video→audio conditioning. Built on `diffusers` / DiT; trained and released in April 2026 with a project page, code, and online demo.

**Release Date:** April 13, 2026

| Feature | Value |
|---------|-------|
| **Conditioning** | Text / Video / Text+Video |
| **Modalities** | Video (visual), Audio (foley) |
| **Asr** | ❌ |
| **Voice Cloning** | ❌ |
| **Text** | ✅ |
| **Video** | ✅ |
| **Image** | ❌ |
| **Audio** | ✅ |
| **Sample Rate** | (not stated) |
| **License** | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| **Pipeline Tag** | text-to-audio |
| **Library** | diffusers |

**Features:** Cross-modal conflict handling: when a video and a text prompt disagree (visually obvious but textually wrong), the model routes control to the modality the user explicitly trusts so the wrong modality doesn't dominate the generated foley. Unifies three conditioning modes (text-controlled VA, audio-controlled VA, and text+video VA) under one generative stack.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/YJX-Xiaomi/ControlFoley)

[![GitHub][link-github]](https://github.com/xiaomi-research/controlfoley)

[![Website][link-website]](https://yjx-research.github.io/ControlFoley/)

[![Demo][link-demo]](https://yjx-research.github.io/ControlFoley_web_page/)

[![Paper][link-paper]](https://arxiv.org/abs/2604.15086)


</details>
<!-- /MODEL:controlfoley.md -->
<!-- MODEL:woosh.md -->
<details id="woosh">
<summary>Woosh</summary>

### Woosh

**Description:** Sony AI's sound effect foundation model for text-to-audio and video-to-audio generation. Includes Woosh-AE (audio encoder/decoder), Woosh-Flow/DFlow (T2A), and Woosh-VFlow/DVFlow (V2A) with distilled fast inference variants.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Architecture** | Flow-based generative models |
| **Text** | ✅ |
| **Video** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Audio-Encoding** | yes |
| **Fast-Inference** | yes (Distilled models) |

**Features:** Optimized for sound effects (not general audio) with both public and private model versions. Video-conditioned generation without requiring captions. Competitive with Stable Audio Open and TangoFlux.

**Links:**
[![GitHub][link-github]](https://github.com/SonyResearch/Woosh-SFX)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2604.01929)


</details>
<!-- /MODEL:woosh.md -->
<!-- MODEL:uni-moe-audio-any2audio.md -->
<details id="uni-moe-audio-any2audio">
<summary>Uni-MoE (Audio)</summary>

### Uni-MoE (Audio)

**Description:** MoE-based omnimodal model with voice cloning, TTS, T2M (text-to-music), and V2M (video-to-music).

**Release Date:** October 16, 2025 (Uni-MoE-Audio)

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Voice Cloning** | ✅ |
| **Text** | ✅ |
| **Video** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Dynamic-Routing** | yes |

**Links:**
[![GitHub][link-github]](https://github.com/HITsz-TMG/Uni-MoE)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2510.13344)


</details>
<!-- /MODEL:uni-moe-audio-any2audio.md -->
<!-- MODEL:audiox.md -->
<details id="audiox">
<summary>AudioX / Audio-Omni</summary>

### AudioX / Audio-Omni

**Description:** Audio-Omni is the first end-to-end framework unifying understanding, generation, and editing across general sound, music, and speech domains. Presented at SIGGRAPH 2026. AudioX is a unified framework integrating text, video, image, and audio conditions.

**Release Date:** March 2025 (AudioX), 2026 (Audio-Omni)

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Text** | ✅ |
| **Video** | ✅ |
| **Audio** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0]<br>![CC BY-NC 4.0][license-cc-by-nc-4.0] |

**Features:** First unified framework covering all three audio domains. Combines frozen multimodal LLM (Qwen2.5-Omni) with trainable Diffusion Transformer for high-fidelity synthesis. Any-to-any audio processing.

**Links:**
[![GitHub][link-github]](https://github.com/ZeyueT/AudioX)

[![GitHub][link-github]](https://github.com/ZeyueT/Audio-Omni)

[![HuggingFace][link-huggingface]](https://huggingface.co/collections/HKUSTAudio/audiox)

[![HuggingFace][link-huggingface]](https://huggingface.co/HKUSTAudio/Audio-Omni)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2503.10522)


</details>
<!-- /MODEL:audiox.md -->
<!-- MODEL:hunyuanvideo-foley.md -->
<details id="hunyuanvideo-foley">
<summary>HunyuanVideo-Foley</summary>

### HunyuanVideo-Foley

**Description:** Tencent's end-to-end video sound effect generation model for professional-grade AI Foley sound generation. Analyzes footage and creates immersive audio that matches the visual content perfectly.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Sample Rate** | 48 kHz |
| **Text** | ✅ |
| **Video** | ✅ |
| **License** | ![Unknown][license-unknown] |
| **High-Quality-Foley** | yes |
| **Context-Aware** | yes |

**Links:**
[![GitHub][link-github]](https://github.com/Tencent-Hunyuan/HunyuanVideo-Foley)

[![Demo][link-demo]](https://huggingface.co/spaces/tencent/HunyuanVideo-Foley)

[![Website][link-website]](https://www.hunyuanvideofoley.org/)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2508.16930)


</details>
<!-- /MODEL:hunyuanvideo-foley.md -->
<!-- MODEL:prismaudio.md -->
<details id="prismaudio">
<summary>PrismAudio</summary>

### PrismAudio

**Description:** Video-to-Audio generation framework with Reinforcement Learning and specialized Chain-of-Thought (CoT) planning. Decomposes reasoning into four specialized modules (Semantic, Temporal, Aesthetic, Spatial CoT) for comprehensive video understanding. Built upon ThinkSound.

**Release Date:** 2025 (ICLR 2026)

| Feature | Value |
|---------|-------|
| **Parameters** | 518M |
| **Video** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Cot-Planning** | yes (4 modules) |
| **Multi-Dimensional-Rl** | yes |
| **Fast-Grpo** | yes (Hybrid ODE-SDE) |
| **Inference-Time** | 0.63 seconds |

**Features:** **Performance Benchmarks:**

| Metric | VGGSound | AudioCanvas |
|--------|----------|-------------|
| Semantic (CLAP) | 0.47 | 0.52 |
| Temporal (DeSync↓) | 0.41 | 0.36 |
| Aesthetic (MOS-Q) | 4.21±0.35 | 4.12±0.28 |

**Links:**
[![GitHub][link-github]](https://github.com/FunAudioLLM/ThinkSound/tree/prismaudio)

[![HuggingFace][link-huggingface]](https://huggingface.co/FunAudioLLM/PrismAudio)

[![Demo][link-demo]](https://huggingface.co/spaces/FunAudioLLM/PrismAudio)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2511.18833)


</details>
<!-- /MODEL:prismaudio.md -->
<!-- MODEL:thinksound.md -->
<details id="thinksound">
<summary>ThinkSound</summary>

### ThinkSound

**Description:** Unified Any2Audio generation framework with flow matching guided by Chain-of-Thought (CoT) reasoning. Supports generating or editing audio from video, text, audio, or their combinations. Accepted to NeurIPS 2025.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Text** | ✅ |
| **Audio** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0]<br>![Research Only][license-research-only] |
| **Cot-Driven-Reasoning** | yes |
| **Interactive-Object-Centric-Editing** | yes |

**Links:**
[![GitHub][link-github]](https://github.com/FunAudioLLM/ThinkSound)

[![HuggingFace][link-huggingface]](https://huggingface.co/liuHuadai/ThinkSound)

[![Demo][link-demo]](https://huggingface.co/spaces/FunAudioLLM/ThinkSound)


</details>
<!-- /MODEL:thinksound.md -->
<!-- MODEL:mmaudio.md -->
<details id="mmaudio">
<summary>MMAudio</summary>

### MMAudio

**Description:** Multimodal joint training framework for high-quality synchronized audio generation from video and/or text inputs. State-of-the-art open source model for generating sounds for videos, images, and text prompts.

**Release Date:** December 2024 (CVPR 2025)

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Text** | ✅ |
| **Video** | ✅ |
| **Image** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Synchronized-Audio** | yes |
| **Multimodal-Joint-Training** | yes |

**Links:**
[![GitHub][link-github]](https://github.com/hkchengrex/MMAudio)

[![HuggingFace][link-huggingface]](https://huggingface.co/hkchengrex/MMAudio)

[![Demo][link-demo]](https://huggingface.co/spaces/hkchengrex/MMAudio)

[![arXiv][link-arxiv]](https://arxiv.org/abs/2412.15322)


</details>
<!-- /MODEL:mmaudio.md -->

---

## Audio Restoration & Enhancement

### Audio Restoration & Enhancement Quick Comparison

| Model | Type | Bandwidth Extension | Inpainting | License |
| :--- | :---: | :---: | :---: | :--- |
| [RE-USE](#re-use) | Universal Speech Enhancement | ✅ | ❌ | ![NVIDIA NC][license-nvidia-noncommercial] |
| [NovaSR](#novasr) | Audio Super-Resolution | ✅ | ❌ | ![Apache 2.0][license-apache-2.0] |
| [PASE](#pase) | Speech Enhancement | ❌ | ❌ | ![Apache 2.0][license-apache-2.0] |
| [DTT-BSR](#dtt-bsr) | Music Source Restoration | ❌ | ❌ | ![MIT][license-mit] |
| [NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)](#nvidia-a2sb) | High-Resolution Audio Restoration | ✅ | ✅ | ![NVIDIA NC][license-nvidia-noncommercial] |
| [AudioSR](#audiosr) | Audio Super-Resolution | ✅ | ❌ | ![Apache 2.0][license-apache-2.0] |

<!-- MODEL:re-use.md -->
<details id="re-use">
<summary>RE-USE</summary>

### RE-USE

**Description:** RE-USE (RE-…), NVIDIA's multilingual universal speech enhancement model, targets distortion–perception trade-off by training a single model that balances listening quality against fidelity to the underlying linguistic / speaker / emotional content. Designed to restore diverse degraded speech while leaving everything else (content, identity, prosody, accent, paralinguistic attributes) intact.

**Release Date:** March 17, 2026

| Feature | Value |
|---------|-------|
| **Type** | Universal Speech Enhancement |
| **Bandwidth Extension** | ✅ |
| **Inpainting** | ❌ |
| **Sample Rate** | 8 / 16 / 22.05 / 24 / 32 / 44.1 / 48 kHz (multi-rate input) |
| **Architecture** | Mamba-SSM backbone |
| **Degradation Coverage** | additive noise, reverberation, clipping, bandwidth limit, codec artifacts, packet loss, low-quality mics |
| **Language Agnostic** | yes |
| **License** | ![NVIDIA NC][license-nvidia-noncommercial] |

**Features:** A **single Mamba-SSM model** that handles seven different input sample rates (no resampling pre-step), covers a broad degradation menu in one checkpoint, stays language-agnostic without per-language training, and explicitly balances distortion reduction against fidelity to the input speech — addressing the universal-SE trade-off that earlier single-purpose enhancers couldn't.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/nvidia/RE-USE)

[![Demo][link-demo]](https://huggingface.co/spaces/nvidia/RE-USE)

[![Paper][link-paper]](https://arxiv.org/abs/2603.02641)


</details>
<!-- /MODEL:re-use.md -->
<!-- MODEL:novasr.md -->
<details id="novasr">
<summary>NovaSR</summary>

### NovaSR

**Description:** NovaSR is a tiny audio upsampler (~52 kB parameter count) that bandwidth-extends 16 kHz input up to 48 kHz. Public card on `YatharthS/NovaSR` advertises realtime factors around 3500× on A100, making it a candidate for real-time on-device super-resolution where model size dominates latency. Inference path is small enough to fit in CPU memory; the use case is speech-bandwidth extension without GPU.

**Release Date:** January 6, 2026

| Feature | Value |
|---------|-------|
| **Type** | Audio Super-Resolution (16 kHz → 48 kHz) |
| **Bandwidth Extension** | ✅ |
| **Inpainting** | ❌ |
| **Channels** | mono |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Parameters** | 52 kB |
| **Streamable** | yes (low VRAM / runs without GPU) |
| **Realtime Factor** | ~3500× (A100) |

**Features:** A 52 kB-parameter Upsampler that hits ~3500× realtime on GPU and runs on CPU — pushing bandwidth extension below the size / latency envelope where a typical neural upsampler is unacceptable (real-time on-device speech enhancement).

**Links:**
[![GitHub][link-github]](https://github.com/ysharma3501/NovaSR)

[![HuggingFace][link-huggingface]](https://huggingface.co/YatharthS/NovaSR)


</details>
<!-- /MODEL:novasr.md -->
<!-- MODEL:pase.md -->
<details id="pase">
<summary>PASE</summary>

### PASE

**Description:** PASE (Phonologically Anchored Speech Enhancer) is a generative speech-enhancement model from Cisco Collaboration AI that removes noise and reverberation while preserving linguistic content and speaker identity. It uses two fine-tuned WavLM-derived components:

**Release Date:** November 8, 2025

| Feature | Value |
|---------|-------|
| **Type** | Speech Enhancement |
| **Bandwidth Extension** | ❌ |
| **Inpainting** | ❌ |
| **Sample Rate** | 16 kHz mono |
| **Architecture** | Denoising WavLM (DRD from WavLM-Large) + Dual-Stream Vocoder (phonetic + acoustic) |
| **Finetuned From** | WavLM-Large |
| **Training Data** | DN5/DNS5 challenge clean + noise, LibriTTS, VCTK, OpenSLR26+28 RIRs |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Features:** Anchors enhancement to phonology instead of spectrum: by reconstructing from a **phonetic** stream and a separate **acoustic** stream (per DeWavLM's two representations), PASE keeps the words intact even when the spectrum is severely degraded — substantially lowering hallucinations while still regaining perceptual quality.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/Xiaobin-Rong/pase)

[![GitHub][link-github]](https://github.com/cisco-open/pase)

[![Demo][link-demo]](https://xiaobin-rong.github.io/pase_demo/)

[![Paper][link-paper]](https://arxiv.org/abs/2511.13300)


</details>
<!-- /MODEL:pase.md -->
<!-- MODEL:dtt-bsr.md -->
<details id="dtt-bsr">
<summary>DTT-BSR</summary>

### DTT-BSR

**Description:** DTT-BSR (DTTNet with **B**and**S**equence and **R**oPE) is a music-source-restoration challenge submission from team AC/DC (Wuhan University) to ICASSP 2026. It is built inside the official MSR-Kit GAN framework, where the baseline generator is replaced by a DTTNet-style time-frequency U-Net and augmented at the bottleneck with:

**Release Date:** October 16, 2025

| Feature | Value |
|---------|-------|
| **Type** | Music Source Restoration |
| **Bandwidth Extension** | ❌ |
| **Inpainting** | ❌ |
| **Architecture** | DTTNet TFC-TDF U-Net (complex STFT) + Improved Dual-Path BandSplitRNN block + RoPE-Transformer |
| **Input** | complex STFT (real + imag channels; n_fft=2048, hop=512) |
| **Discriminator** | Multi-Frequency Discriminator (baseline) |
| **Framework** | MSR-Kit GAN (reconstruction + adversarial + feature-matching losses) |
| **License** | ![MIT][license-mit] |

**Features:** Treats music-source restoration as a **complex-STFT time-frequency U-Net enhancement at the bottleneck**: keep the strong DTTNet dual-path TFC-TDF structure for local spectral patterns, then layer in BandSplitRNN-style sub-band recurrence + RoPE self-attention so the generator can model long-range, cross-band harmonic structure that ordinary GAN baselines miss — critical for restoring non-vocal stems cleanly.

**Links:**
[![GitHub][link-github]](https://github.com/OrigamiShido/DTT-BSR)


</details>
<!-- /MODEL:dtt-bsr.md -->
<!-- MODEL:nvidia-a2sb.md -->
<details id="nvidia-a2sb">
<summary>NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)</summary>

### NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)

**Description:** A2SB is NVIDIA's audio-to-audio Schrödinger Bridge diffusion model for high-resolution (44.1 kHz) music restoration. It is the first long-audio restoration model that can restore hour-long inputs without boundary artifacts, and it's end-to-end — predicting waveform outputs directly without a separate vocoder. A single trained checkpoint handles both bandwidth extension (predicting high-frequency components) and inpainting (re-generating missing segments), training on permissively-licensed subsets of FMA, Medley-Solos-DB, MUSAN, Musical Instrument, MusicNet, Slakh, FreeSound, FSD50K, GTZAN, and NSynth.

**Release Date:** August 1, 2025

| Feature | Value |
|---------|-------|
| **Type** | High-Resolution Audio Restoration |
| **Bandwidth Extension** | ✅ |
| **Inpainting** | ✅ |
| **License** | ![NVIDIA NC][license-nvidia-noncommercial] |
| **Channels** | stereo |
| **Sample Rate** | 44.1 kHz |
| **Architecture** | End-to-end vocoder-free diffusion Schrödinger Bridge (factorized audio representation) |
| **Long Audio** | yes (hour-scale restoration, no boundary artifacts) |
| **Multi Task** | yes (single model, joint bandwidth-extension + inpainting) |
| **Training Data** | FMA, Medley-Solos-DB, MUSAN, Musical Instrument, MusicNet, Slakh, FreeSound, FSD50K, GTZAN, NSynth (permissive subsets) |

**Features:** A diffusion Schrödinger Bridge formulation that is **end-to-end vocoder-free**: instead of generating a mel / MFCC / latent and then re-synthesising, the model predicts the waveform directly, which is what lets it stay boundary-free over hour-long inputs. The same checkpoint carries both bandwidth extension and inpainting — two distinct restoration tasks trained jointly on permissive-licensed music data and rolled out under NVIDIA NC.

**Links:**
[![GitHub][link-github]](https://github.com/NVIDIA/diffusion-audio-restoration)

[![HuggingFace][link-huggingface]](https://huggingface.co/nvidia/audio_to_audio_schrodinger_bridge)

[![Demo][link-demo]](https://research.nvidia.com/labs/adlr/A2SB/)

[![Paper][link-paper]](https://arxiv.org/abs/2501.11311)


</details>
<!-- /MODEL:nvidia-a2sb.md -->
<!-- MODEL:audiosr.md -->
<details id="audiosr">
<summary>AudioSR</summary>

### AudioSR

**Description:** AudioSR is a versatile audio super-resolution model from Haoheliu Liu and collaborators, published alongside the arXiv paper `2309.07314`. It is a latent-diffusion model that takes arbitrary low-resolution input audio and reconstructs a 48 kHz waveform — bandwidth extension in one model. Designed to be input-rate-agnostic (8 kHz, 16 kHz, 24 kHz, 32 kHz, 44.1 kHz, 48 kHz), produces a single fixed 48 kHz output regardless of input rate, and supports both mono and stereo material. The HF model id `haoheliu/audiosr_basic` ships the Apache-2.0-licensed basic checkpoint the README links out to; the underlying implementation lives in the GitHub repo `haoheliu/versatile_audio_super_resolution`.

**Release Date:** September 6, 2023

| Feature | Value |
|---------|-------|
| **Type** | Audio Super-Resolution (any → 48 kHz) |
| **Bandwidth Extension** | ✅ |
| **Inpainting** | ❌ |
| **Channels** | mono, stereo |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Vram** | 6 GB minimum |
| **Long Audio** | yes |
| **Architecture** | latent diffusion (audio LDM) |

**Features:** Versatile bandwidth extension over a wide range of input rates (8–48 kHz) under one fixed 48 kHz output, with monaural-only and stereo-only inference paths working through the same latent-diffusion pipeline — letting a single light checkpoint cover multiple BWE tasks instead of separate per-rate models.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/haoheliu/audiosr_basic)

[![GitHub][link-github]](https://github.com/haoheliu/versatile_audio_super_resolution)

[![Paper][link-paper]](https://arxiv.org/abs/2309.07314)


</details>
<!-- /MODEL:audiosr.md -->

---

## Speech Recognition (ASR)

### ASR Quick Comparison

| Model | Languages | Streaming | License |
| :--- | :--- | :---: | :--- |
| [Mega-ASR](#mega-asr) | English, Chinese | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Cohere Transcribe](#cohere-transcribe) | 14 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [VibeVoice-ASR](#vibevoice-asr) | 50+ | ✅ | ![MIT][license-mit] |
| [SYMPHONY-ASR](#symphony-asr) | English, Korean | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Fun-ASR](#fun-asr) | 31 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [SYMPHONY](#symphony) | English, Korean | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Moonshine](#moonshine) | English | ❌ | ![MIT][license-mit] |
| [SenseVoice](#sensevoice) | Multilingual | ✅ | ![Unknown][license-unknown] |
| [FunASR](#funasr) | 50+ | ✅ | ![MIT][license-mit] |

<!-- MODEL:mega-asr.md -->
<details id="mega-asr">
<summary>Mega-ASR</summary>

### Mega-ASR

**Description:** Mega-ASR is a robust ASR foundation model trained to withstand the full spectrum of real-world acoustic degradation: 7 atomic acoustic conditions (reverberation, echo, additive noise, far-field, frequency dropout, bandwidth limitation, clipping distortion) and 54 compound environmental scenarios built on top. The inference stack combines Qwen3-ASR-1.7B as backbone, Mega-ASR adaptation weights, and an audio-quality router that picks per-utterance between the robust Mega-ASR path and the base path to preserve clean-speech quality. Robustness is trained via A2S-SFT plus DG-WGPO reinforcement learning, with reported gains up to ~30 % over leading open- and closed-source SOTA models on adversarial acoustic samples.

**Release Date:** May 19, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 1.7B (Qwen3-ASR backbone) + Mega-ASR adapter + audio-quality router |
| **Languages** | English, Chinese |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Architecture** | Qwen3-ASR-1.7B base + adaptation weights + audio-quality router |
| **Training Data** | ~2.4M samples (Voices-in-the-Wild-2M) |
| **Robustness Atoms** | 7 (reverb, echo, additive noise, far-field, freq dropout, bandwidth limit, clipping) |
| **Robustness Compound Scenarios** | 54 |
| **Training** | A2S-SFT + DG-WGPO RL |
| **Base Model** | Qwen/Qwen3-ASR-1.7B |

**Features:** The first foundation ASR explicitly trained to handle **full-scenario in-the-wild** acoustic conditions (7 atomic effects, 54 compound scenarios, 2.4 M samples), combined with a routed inference path that switches between a robust Mega-ASR adapter and the base Qwen3-ASR backbone via an audio-quality classifier — delivering up to ~30 % WER gains over SOTA while staying fully open under Apache-2.0.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/zhifeixie/Mega-ASR)

[![GitHub][link-github]](https://github.com/xzf-thu/Mega-ASR)

[![Website][link-website]](https://xzf-thu.github.io/Mega-ASR/)

[![Paper][link-paper]](https://arxiv.org/abs/2605.19833)

[![Demo][link-demo]](https://huggingface.co/spaces/zhifeixie/Mega-ASR)


</details>
<!-- /MODEL:mega-asr.md -->
<!-- MODEL:cohere-transcribe.md -->
<details id="cohere-transcribe">
<summary>Cohere Transcribe</summary>

### Cohere Transcribe

**Description:** Open-source automatic speech recognition (ASR) model developed by Cohere. A 2 billion parameter dedicated audio-in, text-out model that ranks #1 on the English ASR leaderboard.

**Release Date:** March 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2B |
| **Architecture** | Conformer-based encoder-decoder |
| **Asr** | ✅ |
| **Languages** | 14 (En, Fr, De, It, Es, Pt, Gr, Nl, Pl, Zh, Jp, Ko, Vi, Ar) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Rtfx** | Up to 3x faster than comparable models |

**Features:** - Long-form transcription with automatic chunking (>35 seconds)
- Optional punctuation control
- Batched inference support
- vLLM integration for production serving
- Apple Silicon support via mlx-audio
- WebGPU browser deployment via transformers.js

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/CohereLabs/cohere-transcribe-03-2026)

[![Demo][link-demo]](https://huggingface.co/spaces/CohereLabs/cohere-transcribe-03-2026)

[![Blog][link-blog]](https://cohere.com/blog/transcribe)


</details>
<!-- /MODEL:cohere-transcribe.md -->
<!-- MODEL:vibevoice-asr.md -->
<details id="vibevoice-asr">
<summary>VibeVoice-ASR</summary>

### VibeVoice-ASR

**Description:** Microsoft's unified speech-to-text model for 60-minute long-form audio processing with speaker diarization and timestamping.

**Release Date:** January 21, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Asr** | ✅ |
| **Languages** | 50+ |
| **Streaming** | ✅ |
| **License** | ![MIT][license-mit] |

**Links:**
[![GitHub][link-github]](https://github.com/microsoft/VibeVoice)

[![HuggingFace][link-huggingface]](https://huggingface.co/microsoft/VibeVoice-ASR)


</details>
<!-- /MODEL:vibevoice-asr.md -->
<!-- MODEL:symphony-asr.md -->
<details id="symphony-asr">
<summary>SYMPHONY-ASR</summary>

### SYMPHONY-ASR

**Description:** SYMPHONY-ASR is Okestro AI Lab's ASR-specialized speech-recognition model built from the earlier SYMPHONY base. It is an LLM-ASR design using **Qwen3-4B** as the language head, an HFQ-Former audio frontend (hierarchically compressing high-frame-rate audio features), and an audio-text-to-text interface that supports both Korean and English in a single model. The architecture is deliberately ASR-specialized rather than multi-task, allowing it to land anywhere the standard long-form benchmarks (AMI, Earnings-22, GigaSpeech, LibriSpeech clean & other, VoxPopuli, TedLium-3, SPGI Speech) are tracked, with public WER numbers reported on the model card.

**Release Date:** January 12, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 4B (Qwen3-4B backbone) |
| **Languages** | English, Korean |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Architecture** | HFQ-Former audio encoder + Qwen3-4B LLM adapter + ASR head |
| **Base Model** | Qwen/Qwen3-4B |
| **Pipeline Tag** | audio-text-to-text |
| **Wer Benchmarks** | AMI 9.56, Earnings-22 9.45, GigaSpeech 9.96, LS-clean 1.91, LS-other 4.43, VoxPopuli-en 6.30, TedLium-3 3.39, SPGI 2.29 |

**Features:** An ASR-specialized cut of LLM-ASR (Qwen3-4B backbone + HFQ-Former + Adapter) that explicitly trades generalist audio-text flexibility for tighter ASR performance: pinned public WER scores across the canonical long-form English benchmarks plus Korean support in the same model.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/okestro-ai-lab/SYMPHONY-ASR)

[![GitHub][link-github]]((not stated on this card))

[![Predecessor][link-predecessor]](https://huggingface.co/okestro-ai-lab/SYMPHONY)


</details>
<!-- /MODEL:symphony-asr.md -->
<!-- MODEL:fun-asr.md -->
<details id="fun-asr">
<summary>Fun-ASR</summary>

### Fun-ASR

**Description:** Fun-ASR (Fun-ASR-Nano-2512) is an end-to-end speech recognition large model from Tongyi Lab / FunAudioLLM, trained on tens of millions of hours of real speech data. The Nano variant covers 31 languages including Chinese with multiple dialects (Wu, Cantonese, Min, Hakka, Gan, Xiang, Jin) and 26 regional accents plus English/Japanese, with optional lyric / rap recognition. vLLM-based batch inference is 3-5× faster than baseline, and a llama.cpp / GGUF runtime brings the model to CPU/edge with built-in VAD.

**Release Date:** December 15, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 800M |
| **Languages** | 31 |
| **Streaming** | ✅ |
| **Vad** | ✅ |
| **Punctuation** | ✅ |
| **Diarization** | ✅ |
| **Timestamps** | yes |
| **Hotwords** | yes |
| **Quant** | GGUF (~484MB q-form) |
| **License** | ![Apache 2.0][license-apache-2.0] |

**Features:** Far-field, high-noise end-to-end ASR (conference rooms, in-vehicle, industrial) without the "hallucination" generation and language confusion common to Whisper-class models, plus a vLLM WebSocket streaming SDK that delivers sub-second transcription at scale and a llama.cpp / GGUF edge runtime.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/FunAudioLLM/Fun-ASR-Nano-2512)

[![GitHub][link-github]](https://github.com/FunAudioLLM/Fun-ASR)


</details>
<!-- /MODEL:fun-asr.md -->
<!-- MODEL:symphony.md -->
<details id="symphony">
<summary>SYMPHONY</summary>

### SYMPHONY

**Description:** SYMPHONY is the earlier LLM-ASR design from Okestro AI Lab that pre-dates the ASR-specialized SYMPHONY-ASR. It uses the same Qwen3-4B backbone, an HFQ-Former audio frontend, and an audio-text-to-text interface for Korean + English. The model card self-identifies SYMPHONY-ASR as the `new_version`, and the SYMPHONY card itself is now minimal (auto-generated stub after the successor was published). Public WER numbers on the older release are slightly behind SYMPHONY-ASR — e.g. LibriSpeech-clean 2.26 vs 1.91, TedLium-3 3.97 vs 3.39.

**Release Date:** October 27, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 4B (Qwen3-4B backbone) |
| **Languages** | English, Korean |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Architecture** | HFQ-Former audio encoder + Qwen3-4B LLM adapter |
| **Base Model** | Qwen/Qwen3-4B |
| **Pipeline Tag** | audio-text-to-text |
| **Status** | superseded by SYMPHONY-ASR (Jan 12, 2026) |

**Features:** An earlier general-purpose LLM-ASR recipe (Qwen3-4B + HFQ-Former + Adapter) on the Korean + English bilingual target — preserved here as the version-history parent of the ASR-specialized SYMPHONY-ASR successor.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/okestro-ai-lab/SYMPHONY)

[![Successor][link-successor]](https://huggingface.co/okestro-ai-lab/SYMPHONY-ASR)


</details>
<!-- /MODEL:symphony.md -->
<!-- MODEL:moonshine.md -->
<details id="moonshine">
<summary>Moonshine</summary>

### Moonshine

**Description:** Moonshine is a tiny automatic-speech-recognition family from Useful Sensors, designed for real-time speech transcription on severely memory- and compute-constrained hardware. The release ships two checkpoints (tiny 27M, base 61M), both English-only ASR trained on 200,000 hours of audio + transcript pairs collected from the internet and open HuggingFace datasets. It is the smallest practical Wh-class model family for edge / microcontroller-class deployment among those with public benchmarks against standard ASR datasets.

**Release Date:** September 26, 2024

| Feature | Value |
|---------|-------|
| **Parameters** | 27M (tiny), 61M (base) |
| **Asr** | ✅ |
| **Languages** | English |
| **Streaming** | ✅ |
| **License** | ![MIT][license-mit] |
| **Architecture** | sequence-to-sequence ASR |
| **Training Data** | 200,000 hours (internet + open HF datasets) |
| **Target Hardware** | low-cost / edge / MCU-class |
| **Variants English Only** | yes |

**Features:** A purpose-built tiny ASR (27M–61M parameters) ranging far below the smallest Whisper-class models while remaining competitive on standard ASR datasets — built specifically so a microcontroller / low-cost hardware developer can run real-time English transcription with usable accuracy, rather than shipping a quantized-down Whisper clone.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/UsefulSensors/moonshine)

[![GitHub][link-github]](https://github.com/usefulsensors/moonshine)

[![Blog][link-blog]](https://petewarden.com/2024/10/21/introducing-moonshine-the-new-state-of-the-art-for-speech-to-text/)

[![Paper][link-paper]](https://arxiv.org/abs/2410.15608)


</details>
<!-- /MODEL:moonshine.md -->
<!-- MODEL:sensevoice.md -->
<details id="sensevoice">
<summary>SenseVoice</summary>

### SenseVoice

**Description:** SenseVoice is a speech foundation model that combines automatic speech recognition (ASR), spoken-language identification (LID), speech-emotion recognition (SER), and audio-event detection (AED) in a single non-autoregressive architecture. The Small variant processes 10 s of audio in roughly 70 ms, runs CPU/edge via a llama.cpp-compatible GGUF runtime, and is trained on over 400 k hours of data spanning 50+ languages.

**Release Date:** July 3, 2024

| Feature | Value |
|---------|-------|
| **Parameters** | ~230M (SenseVoice-Small) |
| **Languages** | 50+ (multilingual) |
| **Streaming** | ✅ |
| **Vad** | ✅ |
| **Punctuation** | ✅ |
| **Diarization** | ✅ |
| **Timestamps** | yes |
| **Emotion Recognition** | yes |
| **Audio Event Detection** | yes |
| **License** | ![Unknown][license-unknown] |

**Features:** A non-autoregressive end-to-end architecture that runs at 15× the speed of Whisper-Large while bundling ASR + LID + SER + AED in one model, plus a GGUF/llama.cpp path that brings the whole pipeline to CPU/edge devices without Python at runtime.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/FunAudioLLM/SenseVoiceSmall)

[![GitHub][link-github]](https://github.com/FunAudioLLM/SenseVoice)


</details>
<!-- /MODEL:sensevoice.md -->
<!-- MODEL:funasr.md -->
<details id="funasr">
<summary>FunASR</summary>

### FunASR

**Description:** Industrial-grade end-to-end speech recognition toolkit with SOTA pretrained models, supporting ASR, VAD, punctuation, language modeling, speaker verification, speaker diarization, and multi-talker ASR across 50+ languages. Architectures are updated frequently and the project tracks upstream ModelScope releases.

**Release Date:** Ongoing (First: 2023)

| Feature | Value |
|---------|-------|
| **Parameters** | ~220M (Paraformer-large) |
| **Asr** | ✅ |
| **Languages** | 50+ |
| **Vad** | ✅ |
| **Punctuation** | ✅ |
| **Diarization** | ✅ |
| **Timestamps** | yes |
| **Emotion** | yes |
| **Streaming** | ✅ |
| **License** | ![MIT][license-mit] |

**Links:**
[![GitHub][link-github]](https://github.com/modelscope/FunASR)

[![Website][link-website]](https://www.funasr.com)


</details>
<!-- /MODEL:funasr.md -->

---

## Audio Codecs & Tokenizers

Audio autoencoders, codecs, and latent-space tokenizers that compress waveforms into compact continuous or discrete tokens — the substrate for downstream TTS, music, and a2a generators.

### Audio Codecs & Tokenizers Quick Comparison

| Model | Type | Sample Rate | Latent Dim | Modalities | License |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [KVAE-Audio](#kvae-audio) | Audio VAE | 48 kHz | 64 | Speech, Music, Sound | ![MIT][license-mit] |

<!-- MODEL:kvae-audio.md -->
<details id="kvae-audio">
<summary>KVAE-Audio</summary>

### KVAE-Audio

**Description:** KVAE-Audio is a continuous, full-band (48 kHz) audio autoencoder by Kandinsky Lab / SberBank. It compresses raw waveforms into compact continuous latents (64-dim) and reconstructs them with high fidelity across speech, music, and general sound. The model is intended both for reconstruction and as a latent space for downstream generative models — internal ablations show that swapping the autoencoder under a fixed generator (same DiT, same data, same steps) consistently improves generative quality.

**Release Date:** June 29, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 166.9M |
| **Sample Rate** | 48 kHz full-band |
| **Latent Dim** | 64 |
| **Modalities** | speech, music, sound |
| **Reconstruction Quality** | beats MMAudio/DACVAE/SAME-L on AudioCaps FAD |
| **Architecture** | VAE (continuous latents) |
| **Related Papers** | 2412.15322, 2410.13720, 2605.18613 |
| **License** | ![MIT][license-mit] |

**Features:** Full-band 48 kHz continuous audio VAE with a comparatively tiny 64-dimensional latent space, designed as a drop-in replacement for prior codec/VAEs for *generative* pipelines — internal benchmarks show lower FAD on AudioCaps and Song Describer than MMAudio, DACVAE (MovieGen), and SAME-L under a fixed generator.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/kandinskylab/KVAE-Audio)

[![GitHub][link-github]](https://github.com/kandinskylab/kvae-audio)

[![Website][link-website]](https://kandinskylab.ai/)


</details>
<!-- /MODEL:kvae-audio.md -->

---

## Audio Transcription Models

Multi-stance audio annotators — specialized models that transcribe not just speech but also musical audio (lyrics, song structure). Often used to label training data for downstream speech or music generation.

### Audio Transcription Models Quick Comparison

| Model | Use Case | Input | Languages | Base Model | License |
| :--- | :--- | :--- | :--- | :--- | :--- |
| [ACE-Step Transcriber](#acestep-transcriber) | Music data labeling | Audio | 50+ | Qwen2.5 Omni 7B | ![MIT][license-mit] |

<!-- MODEL:acestep-transcriber.md -->
<details id="acestep-transcriber">
<summary>ACE-Step Transcriber</summary>

### ACE-Step Transcriber

**Description:** ACE-Step Transcriber is the **annotation model** that ACE-Step used to label its v1.5 music-generation training data. It is a multilingual audio annotation model built on **Qwen2.5 Omni 7B** that transcribes both **speech** and **singing voice** with high accuracy, then automatically identifies song structural elements (verse, chorus, bridge, intro, outro, pre/post-chorus, instrumental interludes). Output is structured: `# Languages` + `# Lyrics` blocks with `[Section Tag - Optional Instrument]` markers.

**Release Date:** January 23, 2026

| Feature | Value |
|---------|-------|
| **Asr** | ✅ |
| **Languages** | 50+ |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |
| **Architecture** | Qwen2.5 Omni 7B base, multi-modal audio-text-to-text |
| **Pipeline Tag** | audio-text-to-text |
| **Target Output** | structured `# Languages` + `# Lyrics` with `[Section Tag]` markers (verse, chorus, bridge, intro, outro, pre-chorus, post-chorus, intro/outro, guiter interlude, instrumental, spoken) |
| **Training Role** | annotation / labeling model for ACE-Step v1.5 music data |
| **Modalities** | speech + singing voice + musical structure |
| **Datasets** | multilingual (50+), music + speech corpora |

**Features:** A *specialized audio annotator* that bridges speech recognition and music-structure understanding: it labels both what is being said and how the song is organized (verse/chorus/bridge and instrumental boundaries) in one pass — built specifically to label the training corpus of the ACE-Step v1.5 music model, but usable as a stand-alone multilingual lyrics / audio-structure transcriber.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/ACE-Step/acestep-transcriber)

[![Paper][link-paper]](https://arxiv.org/abs/2602.00744)


</details>
<!-- /MODEL:acestep-transcriber.md -->

---

## Additional Resources

Community-maintained leaderboards for tracking and comparing speech models across providers and benchmarks.

### Text-to-Speech

- [Artificial Analysis — Text-to-Speech Leaderboard](https://artificialanalysis.ai/text-to-speech/leaderboard) — Elo-based speech arena ranking TTS models on each provider's native voices, with API pricing and arena voice counts.

### Speech-to-Text (ASR)

- [🤗 Open ASR Leaderboard](https://huggingface.co/spaces/hf-audio/open_asr_leaderboard) — Hugging Face community benchmark ranking open and proprietary ASR models by average WER and RTFx across English and multilingual datasets.
- [Artificial Analysis — Speech-to-Text (Streaming) Leaderboard](https://artificialanalysis.ai/speech-to-text/streaming) — Compares streaming STT models and providers on the AA-WER Streaming index, latency, and pricing.
- [FFASR Leaderboard (Treble Technologies)](https://huggingface.co/spaces/treble-technologies/ffasr) — Far-field ASR multi-condition benchmark reporting WER and RTFx across noisy, reverberant, and SNR-stratified scenarios (measured & simulated RIRs).

---

## Contributing

This list is continuously evolving. If you have any models to add or updates to suggest, please feel free to contribute! See [CONTRIBUTING.md](./CONTRIBUTING.md) for the template-driven workflow.

---

*Last Updated: July 2026*

<!-- MARKDOWN LINKS & IMAGES -->
[license-mit]: https://img.shields.io/badge/MIT-green?style=flat-square&logo=openldap "MIT"
[license-research-only]: https://img.shields.io/badge/Research_Only-orange?style=flat-square "Research Only"
[license-apache-2.0]: https://img.shields.io/badge/Apache_2.0-green?style=flat-square&logo=apache "Apache 2.0"
[license-unknown]: https://img.shields.io/badge/Unknown-lightgrey?style=flat-square "Unknown"
[license-cc-by-nc-4.0]: https://img.shields.io/badge/CC_BY--NC_4.0-orange?style=flat-square&logo=creativecommons "CC BY-NC 4.0"
[license-openrail-m]: https://img.shields.io/badge/OpenRAIL--M-blueviolet?style=flat-square "OpenRAIL-M"
[license-lfm]: https://img.shields.io/badge/LFM-blue?style=flat-square "LFM"
[license-nvidia-noncommercial]: https://img.shields.io/badge/NVIDIA_NC-yellow?style=flat-square&logo=nvidia "NVIDIA NC"

[link-blog]: https://img.shields.io/badge/Blog-post-blue?style=flat-square "Blog post"
[link-demo]: https://img.shields.io/badge/Demo-live-blue?style=flat-square "Demo live"
[link-github]: https://img.shields.io/badge/GitHub-code-black?style=flat-square&logo=github "GitHub code"
[link-huggingface]: https://img.shields.io/badge/HuggingFace-models-yellow?style=flat-square&logo=huggingface "HuggingFace models"
[link-paper]: https://img.shields.io/badge/Paper-paper-red?style=flat-square "Paper paper"
[link-website]: https://img.shields.io/badge/Website-site-blue?style=flat-square "Website site"
[link-arxiv]: https://img.shields.io/badge/arXiv-paper-red?style=flat-square "arXiv paper"
