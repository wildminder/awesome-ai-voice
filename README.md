# Awesome TTS & Voice Generation Models

A curated list of open-source Text-to-Speech (TTS) and voice cloning models. Models are sorted by release date (newest first).

![logo-tts2](https://github.com/user-attachments/assets/132b105b-b894-4150-bace-e84ef70ed2be)

---

## Table of Contents

- [Text-to-Speech (TTS) Models](#text-to-speech-tts-models)
- [Anything to Audio](#anything-to-audio)
- [Audio Restoration & Enhancement](#audio-restoration--enhancement)
- [Speech Recognition (ASR)](#speech-recognition-asr)
- [Additional Resources](#additional-resources)

---

## Text-to-Speech (TTS) Models

### TTS Quick Comparison

| Model | Voice Cloning | ASR | Languages | Streaming | License |
| :--- | :---: | :---: | :--- | :---: | :--- |
| [Higgs Audio v3 TTS](#higgs-audio-v3-tts) | ✅ | ❌ | 102 | ✅ | ![Research Only][license-research-only] |
| [LongCat-AudioDiT](#longcat-audiodit) | ✅ | ❌ | Chinese, English | ❌ | ![MIT][license-mit] |
| [Fish Audio S2 Pro](#fish-audio-s2-pro) | ✅ | ❌ | 80+ | ✅ | ![Research Only][license-research-only] |
| [LongCat-Next](#longcat-next) | ✅ | ✅ | Chinese, English | ✅ | ![MIT][license-mit] |
| [Voxtral-4B-TTS](#voxtral-4b-tts) | ✅ | ❌ | 9 | ✅ | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [KittenTTS](#kittenTTS) | ✅ | ❌ | English, Multiple | ✅ | ![Apache 2.0][license-apache-2.0] |
| [MOSS-TTS](#moss-tts) | ✅ | ❌ | 20 languages | ✅ | ![Apache 2.0][license-apache-2.0] |
| [SoulX-Singer](#soulx-singer) | ✅ | ❌ | Mandarin, English, Cantonese | ✅ | ![Apache 2.0][license-apache-2.0] |
| [SoproTTS](#soprotts) | ✅ | ❌ | English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Qwen3-TTS](#qwen3-tts) | ✅ | ❌ | 10 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Irodori-TTS-500M-v2](#irodori-tts-500m-v2) | ✅ | ❌ | Japanese | ❌ | ![MIT][license-mit] |
| [KugelAudio](#kugelaudio) | ✅ | ❌ | 23 European languages | ✅ | ![MIT][license-mit] |
| [LEMAS-TTS](#lemas-tts) | ✅ | ❌ | 10 | ❌ | ![Apache 2.0][license-apache-2.0] |
| [MioTTS-2.6B](#miotts-26b) | ✅ | ❌ | English, Japanese | ✅ | ![LFM][license-lfm] |
| [MOSS-TTS-Nano](#moss-tts-nano) | ✅ | ❌ | 20 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [NeuTTS](#neutts) | ✅ | ❌ | English, Spanish, German, French | ✅ | ![Apache 2.0][license-apache-2.0] |
| [OmniVoice](#omnivoice) | ✅ | ❌ | 600+ | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Supertonic 2](#supertonic-2) | ❌ | ❌ | English, Korean, Spanish, Portuguese, French | ✅ | ![OpenRAIL-M][license-openrail-m] |
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
| [Chatterbox](#chatterbox) | ✅ | ❌ | 23+ | ✅ | ![MIT][license-mit] |
| [Fish Speech](#fish-speech) | ✅ | ❌ | 8 | ✅ | ![Apache 2.0][license-apache-2.0] |
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

**Innovation:** Interleaved text/audio token modelling with a delay-pattern multi-codebook embedding/head: a single autoregressive stack emits both modalities and supports inline `<|category:value|>` control tags (emotion/style/sfx/prosody) inserted at any point in the target text.

**Links:**
[![HuggingFace](https://img.shields.io/badge/HuggingFace-higgs--audio--v3--tts--4b-yellow?logo=huggingface&style=flat)](https://huggingface.co/bosonai/higgs-audio-v3-tts-4b)
[![GitHub](https://img.shields.io/badge/GitHub-sglang--omni-black?logo=github&style=flat)](https://github.com/sgl-project/sglang-omni)
[![Blog](https://img.shields.io/badge/Blog-higgs--audio--v3--tts-blue&style=flat)](https://www.boson.ai/blog/higgs-audio-v3-tts)
[![Demo](https://img.shields.io/badge/Demo-higgs--audio--v3--tts-blue&style=flat)](https://huggingface.co/spaces/multimodalart/higgs-audio-v3-tts)

</details>
<!-- /MODEL:higgs-audio-v3-tts.md -->
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

**Innovation:** Adaptive Projection Guidance (APG) replaces traditional classifier-free guidance for elevated generation quality. Outperforms Seed-TTS on zero-shot voice cloning benchmarks.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-LongCat--AudioDiT-black?logo=github&style=flat)](https://github.com/meituan-longcat/LongCat-AudioDiT)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-LongCat--AudioDiT--1B-yellow?logo=huggingface&style=flat)](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-1B)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-LongCat--AudioDiT--3.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-3.5B)

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
[![GitHub](https://img.shields.io/badge/GitHub-fish--speech-black?logo=github&style=flat)](https://github.com/fishaudio/fish-speech)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-s2--pro-yellow?logo=huggingface&style=flat)](https://huggingface.co/fishaudio/s2-pro)

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

**Innovation:** Discrete Native Autoregression Paradigm (DiNA) unifying modalities in shared discrete token space. Combines visual understanding, generation, and audio processing in single model.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-LongCat--Next-black?logo=github&style=flat)](https://github.com/meituan-longcat/LongCat-Next)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-LongCat--Next-yellow?logo=huggingface&style=flat)](https://huggingface.co/meituan-longcat/LongCat-Next)

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
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Voxtral--4B--TTS--2603-yellow?logo=huggingface&style=flat)](https://huggingface.co/mistralai/Voxtral-4B-TTS-2603)
[![Demo](https://img.shields.io/badge/Demo-text--to--speech-blue&style=flat)](https://console.mistral.ai/build/audio/text-to-speech)
[![Blog](https://img.shields.io/badge/Blog-voxtral--tts-blue&style=flat)](https://mistral.ai/news/voxtral-tts)

</details>
<!-- /MODEL:voxtral-4b-tts.md -->
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
[![GitHub](https://img.shields.io/badge/GitHub-KittenTTS-black?logo=github&style=flat)](https://github.com/KittenML/KittenTTS)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-KittenTTS--Demo-yellow?logo=huggingface&style=flat)](https://huggingface.co/spaces/KittenML/KittenTTS-Demo)

</details>
<!-- /MODEL:kittenTTS.md -->
<!-- MODEL:moss-tts.md -->
<details id="moss-tts">
<summary>MOSS-TTS</summary>

### MOSS-TTS

**Description:** MOSS-TTS is a production-grade Text-to-Speech foundation model developed by OpenMOSS Team and MOSI.AI. Features state-of-the-art evaluation performance on Seed-TTS-eval benchmark with zero-shot voice cloning.

**Release Date:** February 10, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 8B (Delay), 1.7B (Local) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 20 languages |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Max-Duration** | 1 hour |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-MOSS--TTS-black?logo=github&style=flat)](https://github.com/OpenMOSS/MOSS-TTS)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-MOSS--TTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/OpenMOSS-Team/MOSS-TTS)
[![Website](https://img.shields.io/badge/Website-moss--tts-blue&style=flat)](https://mosi.cn/models/moss-tts)

</details>
<!-- /MODEL:moss-tts.md -->
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
[![GitHub](https://img.shields.io/badge/GitHub-SoulX--Singer-black?logo=github&style=flat)](https://github.com/Soul-AILab/SoulX-Singer)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-SoulX--Singer-yellow?logo=huggingface&style=flat)](https://huggingface.co/spaces/Soul-AILab/SoulX-Singer)
[![arXiv](https://img.shields.io/badge/arXiv-2602.07803-red&style=flat)](https://arxiv.org/abs/2602.07803)

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
[![GitHub](https://img.shields.io/badge/GitHub-sopro-black?logo=github&style=flat)](https://github.com/samuel-vitorino/sopro)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-sopro-yellow?logo=huggingface&style=flat)](https://huggingface.co/samuel-vitorino/sopro)

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
[![GitHub](https://img.shields.io/badge/GitHub-Qwen3--TTS-black?logo=github&style=flat)](https://github.com/QwenLM/Qwen3-TTS)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-qwen3--tts-yellow?logo=huggingface&style=flat)](https://huggingface.co/collections/Qwen/qwen3-tts)
[![arXiv](https://img.shields.io/badge/arXiv-2601.15621-red&style=flat)](https://arxiv.org/abs/2601.15621)

</details>
<!-- /MODEL:qwen3-tts.md -->
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

**Innovation:** **Key Feature:** Emoji annotation control - insert specific emojis into text to control speaking styles, emotions, and sound effects.

**Links:**
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Irodori--TTS--500M--v2-yellow?logo=huggingface&style=flat)](https://huggingface.co/Aratako/Irodori-TTS-500M-v2)
[![GitHub](https://img.shields.io/badge/GitHub-Irodori--TTS-black?logo=github&style=flat)](https://github.com/Aratako/Irodori-TTS)
[![Demo](https://img.shields.io/badge/Demo-Irodori--TTS--500M--v2--Demo-blue&style=flat)](https://huggingface.co/spaces/Aratako/Irodori-TTS-500M-v2-Demo)

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
[![GitHub](https://img.shields.io/badge/GitHub-kugelaudio--open-black?logo=github&style=flat)](https://github.com/Kugelaudio/kugelaudio-open)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-kugelaudio--0--open-yellow?logo=huggingface&style=flat)](https://huggingface.co/kugelaudio/kugelaudio-0-open)
[![Website](https://img.shields.io/badge/Website-kugelaudio.com-blue&style=flat)](https://kugelaudio.com)

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

**Innovation:** Built on 150,000+ hours of multilingual speech data with word-level timestamps. Includes LEMAS-Edit for precise word-level speech editing via masked token infilling.

**Links:**
[![Website](https://img.shields.io/badge/Website-LEMAS--Project-blue&style=flat)](https://lemas-project.github.io/LEMAS-Project/)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-LEMAS--TTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/LEMAS-Project/LEMAS-TTS)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-LEMAS--Edit-yellow?logo=huggingface&style=flat)](https://huggingface.co/LEMAS-Project/LEMAS-Edit)

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
[![HuggingFace](https://img.shields.io/badge/HuggingFace-MioTTS--2.6B-yellow?logo=huggingface&style=flat)](https://huggingface.co/Aratako/MioTTS-2.6B)
[![GitHub](https://img.shields.io/badge/GitHub-MioTTS--Inference-black?logo=github&style=flat)](https://github.com/Aratako/MioTTS-Inference)

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

**Innovation:** Pure autoregressive architecture with MOSS-Audio-Tokenizer-Nano. Compresses audio to 12.5 Hz token stream using RVQ with 16 codebooks. Runs on 4-core CPU.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-MOSS--TTS--Nano-black?logo=github&style=flat)](https://github.com/OpenMOSS/MOSS-TTS-Nano)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-MOSS--TTS--Nano--100M-yellow?logo=huggingface&style=flat)](https://huggingface.co/OpenMOSS-Team/MOSS-TTS-Nano-100M)
[![Demo](https://img.shields.io/badge/Demo-MOSS--TTS--Nano-blue&style=flat)](https://huggingface.co/spaces/OpenMOSS-Team/MOSS-TTS-Nano)

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
[![GitHub](https://img.shields.io/badge/GitHub-neutts-black?logo=github&style=flat)](https://github.com/neuphonic/neutts)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-neutts--air-yellow?logo=huggingface&style=flat)](https://huggingface.co/neuphonic/neutts-air)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-neutts--nano-yellow?logo=huggingface&style=flat)](https://huggingface.co/neuphonic/neutts-nano)

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

**Innovation:** Simplified single-stage architecture vs conventional two-stage pipelines. Full-codebook random masking strategy with LLM initialization for superior intelligibility. Noise-robust prompt processing.

**Links:**
[![Website](https://img.shields.io/badge/Website-omnivoice-blue&style=flat)](https://zhu-han.github.io/omnivoice/)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-OmniVoice-yellow?logo=huggingface&style=flat)](https://huggingface.co/k2-fsa/OmniVoice)

</details>
<!-- /MODEL:omnivoice.md -->
<!-- MODEL:supertonic-2.md -->
<details id="supertonic-2">
<summary>Supertonic 2</summary>

### Supertonic 2

**Description:** Lightning-fast, on-device text-to-speech system designed for extreme performance with minimal computational overhead. Powered by ONNX Runtime, it runs entirely on-device—no cloud, no API calls, no privacy concerns. Outperforms ElevenLabs Flash v2.5 by up to 42× in speed benchmarks.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 66M |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Pronunciation** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | English, Korean, Spanish, Portuguese, French |
| **Streaming** | ✅ |
| **License** | ![OpenRAIL-M][license-openrail-m] |
| **Rtf** | 0.001-0.015 (up to 167× realtime) |
| **On-Device** | yes (ONNX Runtime) |

**Innovation:** **Performance Comparison:**

| System | Speed (chars/sec) | RTF |
|--------|-------------------|-----|
| Supertonic 2 (RTX 4090) | 12,164 | 0.001 |
| Supertonic 2 (M4 Pro CPU) | 1,263 | 0.012 |
| ElevenLabs Flash v2.5 | 287 | 0.5 |
| Kokoro (Open-source) | 117 | 1.3 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-supertonic-black?logo=github&style=flat)](https://github.com/supertone-inc/supertonic)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-supertonic--2-yellow?logo=huggingface&style=flat)](https://huggingface.co/Supertone/supertonic-2)
[![Demo](https://img.shields.io/badge/Demo-supertonic--2-blue&style=flat)](https://huggingface.co/spaces/Supertone/supertonic-2)

</details>
<!-- /MODEL:supertonic-2.md -->
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

**Innovation:** PM-RoPE positional encoding with XCodec2 audio codec. Low-VRAM options with CPU offloading. Batch inference efficiency with single encoder pass.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-T5Gemma--TTS-black?logo=github&style=flat)](https://github.com/Aratako/T5Gemma-TTS)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-T5Gemma--TTS--2b--2b-yellow?logo=huggingface&style=flat)](https://huggingface.co/Aratako/T5Gemma-TTS-2b-2b)
[![Demo](https://img.shields.io/badge/Demo-T5Gemma--TTS--Demo-blue&style=flat)](https://huggingface.co/spaces/Aratako/T5Gemma-TTS-Demo)

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

**Innovation:** Ultra-compact architecture optimized for CPU-only deployment. Multi-platform support via Python and Node.js APIs. Works on laptops, edge devices, and embedded systems.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-tiny--tts-black?logo=github&style=flat)](https://github.com/tronghieuit/tiny-tts)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-tiny--tts-yellow?logo=huggingface&style=flat)](https://huggingface.co/backtracking/tiny-tts)
[![Demo](https://img.shields.io/badge/Demo-tiny--tts--demo-blue&style=flat)](https://huggingface.co/spaces/backtracking/tiny-tts-demo)

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

**Innovation:** Tokenizer-free design with LocEnc → TSLM → RALM → LocDiT pipeline. Built-in super-resolution via AudioVAE V2 for 48kHz output.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-VoxCPM-black?logo=github&style=flat)](https://github.com/OpenBMB/VoxCPM)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-VoxCPM2-yellow?logo=huggingface&style=flat)](https://huggingface.co/openbmb/VoxCPM2)
[![Demo](https://img.shields.io/badge/Demo-VoxCPM--Demo-blue&style=flat)](https://huggingface.co/spaces/OpenBMB/VoxCPM-Demo)

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
[![GitHub](https://img.shields.io/badge/GitHub-GLM--TTS-black?logo=github&style=flat)](https://github.com/zai-org/GLM-TTS)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-GLM--TTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/zai-org/GLM-TTS)
[![arXiv](https://img.shields.io/badge/arXiv-2512.14291-red&style=flat)](https://arxiv.org/abs/2512.14291)

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
| **Max-Duration** | ~10 minutes |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-VibeVoice-black?logo=github&style=flat)](https://github.com/microsoft/VibeVoice)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-VibeVoice--Realtime--0.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/microsoft/VibeVoice-Realtime-0.5B)

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
[![GitHub](https://img.shields.io/badge/GitHub-CosyVoice-black?logo=github&style=flat)](https://github.com/FunAudioLLM/CosyVoice)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Fun--CosyVoice3--0.5B--2512-yellow?logo=huggingface&style=flat)](https://huggingface.co/FunAudioLLM/Fun-CosyVoice3-0.5B-2512)
[![arXiv](https://img.shields.io/badge/arXiv-2505.17589-red&style=flat)](https://arxiv.org/abs/2505.17589)

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
[![HuggingFace](https://img.shields.io/badge/HuggingFace-LFM2--Audio--1.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/LiquidAI/LFM2-Audio-1.5B)
[![Website](https://img.shields.io/badge/Website-lfm-blue&style=flat)](https://docs.liquid.ai/lfm)

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
[![GitHub](https://img.shields.io/badge/GitHub-Comfyui--Index--TTS2-black?logo=github&style=flat)](https://github.com/xuchenxu168/Comfyui-Index-TTS2)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-IndexTTS--2-yellow?logo=huggingface&style=flat)](https://huggingface.co/IndexTeam/IndexTTS-2)

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
[![HuggingFace](https://img.shields.io/badge/HuggingFace-maya1-yellow?logo=huggingface&style=flat)](https://huggingface.co/maya-research/maya1)
[![Website](https://img.shields.io/badge/Website-mayaresearch.ai-blue&style=flat)](https://mayaresearch.ai)

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
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Step--Audio--EditX-yellow?logo=huggingface&style=flat)](https://huggingface.co/stepfun-ai/Step-Audio-EditX)
[![arXiv](https://img.shields.io/badge/arXiv-2511.03601-red&style=flat)](https://arxiv.org/abs/2511.03601)

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
[![GitHub](https://img.shields.io/badge/GitHub-VoxCPM-black?logo=github&style=flat)](https://github.com/OpenBMB/VoxCPM)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-VoxCPM--0.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/openbmb/VoxCPM-0.5B)
[![arXiv](https://img.shields.io/badge/arXiv-2509.24650-red&style=flat)](https://arxiv.org/abs/2509.24650)

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
| **Max-Duration** | 3 minutes |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-FireRedTTS2-black?logo=github&style=flat)](https://github.com/FireRedTeam/FireRedTTS2)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-FireRedTTS2-yellow?logo=huggingface&style=flat)](https://huggingface.co/FireRedTeam/FireRedTTS2)
[![arXiv](https://img.shields.io/badge/arXiv-2509.02020-red&style=flat)](https://arxiv.org/abs/2509.02020)

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

**Innovation:** **Key Innovation (AF-Next):** Staged curriculum training with GRPO-based RL post-training. Three specialized checkpoints: Instruct, Think (reasoning), and Captioner. Temporal Audio Chain-of-Thought grounding intermediate reasoning to timestamps.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-audio--flamingo-black?logo=github&style=flat)](https://github.com/NVIDIA/audio-flamingo)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-audio--flamingo--3-yellow?logo=huggingface&style=flat)](https://huggingface.co/nvidia/audio-flamingo-3)
[![Website](https://img.shields.io/badge/Website-afnext--umd--nvidia.github.io-blue&style=flat)](https://afnext-umd-nvidia.github.io/)

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
[![GitHub](https://img.shields.io/badge/GitHub-ZipVoice-black?logo=github&style=flat)](https://github.com/k2-fsa/ZipVoice)
[![Website](https://img.shields.io/badge/Website-zipvoice.github.io-blue&style=flat)](https://zipvoice.github.io/)
[![arXiv](https://img.shields.io/badge/arXiv-2506.13053-red&style=flat)](https://arxiv.org/abs/2506.13053)

</details>
<!-- /MODEL:zipvoice.md -->
<!-- MODEL:chatterbox.md -->
<details id="chatterbox">
<summary>Chatterbox</summary>

### Chatterbox

**Description:** Family of SOTA open-source TTS models by Resemble AI with zero-shot voice cloning and multilingual synthesis.

**Release Date:** June 13, 2025 (v0.1.2)

| Feature | Value |
|---------|-------|
| **Parameters** | 350M-500M |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 23+ |
| **Streaming** | ✅ |
| **License** | ![MIT][license-mit] |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-chatterbox-black?logo=github&style=flat)](https://github.com/resemble-ai/chatterbox)
[![Website](https://img.shields.io/badge/Website-resemble.ai-blue&style=flat)](https://resemble.ai/)

</details>
<!-- /MODEL:chatterbox.md -->
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
[![GitHub](https://img.shields.io/badge/GitHub-fish--speech-black?logo=github&style=flat)](https://github.com/fishaudio/fish-speech)
[![Website](https://img.shields.io/badge/Website-fish.audio-blue&style=flat)](https://fish.audio/)

</details>
<!-- /MODEL:fish-speech.md -->
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
[![GitHub](https://img.shields.io/badge/GitHub-Orpheus--TTS-black?logo=github&style=flat)](https://github.com/canopyai/Orpheus-TTS)
[![Website](https://img.shields.io/badge/Website-model--releases-blue&style=flat)](https://canopylabs.ai/model-releases)

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
[![GitHub](https://img.shields.io/badge/GitHub-MegaTTS3-black?logo=github&style=flat)](https://github.com/bytedance/MegaTTS3)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-MegaTTS3-yellow?logo=huggingface&style=flat)](https://huggingface.co/spaces/ByteDance/MegaTTS3)
[![arXiv](https://img.shields.io/badge/arXiv-2502.18924-red&style=flat)](https://arxiv.org/abs/2502.18924)

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
[![GitHub](https://img.shields.io/badge/GitHub-Spark--TTS-black?logo=github&style=flat)](https://github.com/SparkAudio/Spark-TTS)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Spark--TTS--0.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/SparkAudio/Spark-TTS-0.5B)
[![arXiv](https://img.shields.io/badge/arXiv-2503.01710-red&style=flat)](https://arxiv.org/abs/2503.01710)

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
[![GitHub](https://img.shields.io/badge/GitHub-Step--Audio-black?logo=github&style=flat)](https://github.com/stepfun-ai/Step-Audio)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-stepfun--ai-yellow?logo=huggingface&style=flat)](https://huggingface.co/stepfun-ai)
[![arXiv](https://img.shields.io/badge/arXiv-2502.11946-red&style=flat)](https://arxiv.org/abs/2502.11946)

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
[![GitHub](https://img.shields.io/badge/GitHub-kokoro-black?logo=github&style=flat)](https://github.com/hexgrad/kokoro)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Kokoro--82M-yellow?logo=huggingface&style=flat)](https://huggingface.co/hexgrad/Kokoro-82M)
[![Demo](https://img.shields.io/badge/Demo-Kokoro--TTS-blue&style=flat)](https://hf.co/spaces/hexgrad/Kokoro-TTS)

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
[![GitHub](https://img.shields.io/badge/GitHub-kokoclone-black?logo=github&style=flat)](https://github.com/Ashish-Patnaik/kokoclone)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-kokoclone-yellow?logo=huggingface&style=flat)](https://huggingface.co/PatnaikAshish/kokoclone)
[![Demo](https://img.shields.io/badge/Demo-kokoclone-blue&style=flat)](https://huggingface.co/spaces/PatnaikAshish/kokoclone)

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
[![GitHub](https://img.shields.io/badge/GitHub-LuxTTS-black?logo=github&style=flat)](https://github.com/ysharma3501/LuxTTS)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-LuxTTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/YatharthS/LuxTTS)

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
[![GitHub](https://img.shields.io/badge/GitHub-MiMo--Audio-black?logo=github&style=flat)](https://github.com/XiaomiMiMo/MiMo-Audio)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-mimo--audio--68cc7202692c27dae881cce0-yellow?logo=huggingface&style=flat)](https://huggingface.co/collections/XiaomiMiMo/mimo-audio-68cc7202692c27dae881cce0)

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
| **Max-Duration** | 90+ minutes |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-SoulX--Podcast-black?logo=github&style=flat)](https://github.com/Soul-AILab/SoulX-Podcast)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-soulx--podcast-yellow?logo=huggingface&style=flat)](https://huggingface.co/collections/Soul-AILab/soulx-podcast)
[![arXiv](https://img.shields.io/badge/arXiv-2510.23541-red&style=flat)](https://arxiv.org/abs/2510.23541)

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
[![HuggingFace](https://img.shields.io/badge/HuggingFace-VieNeu--TTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/pnnbao-ump/VieNeu-TTS)
[![GitHub](https://img.shields.io/badge/GitHub-VieNeu--TTS-black?logo=github&style=flat)](https://github.com/pnnbao97/VieNeu-TTS)

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
[![GitHub](https://img.shields.io/badge/GitHub-dia-black?logo=github&style=flat)](https://github.com/nari-labs/dia)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Dia--1.6B--0626-yellow?logo=huggingface&style=flat)](https://huggingface.co/nari-labs/Dia-1.6B-0626)

</details>
<!-- /MODEL:dia.md -->
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
[![GitHub](https://img.shields.io/badge/GitHub-Kimi--Audio-black?logo=github&style=flat)](https://github.com/MoonshotAI/Kimi-Audio)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Kimi--Audio--7B-yellow?logo=huggingface&style=flat)](https://huggingface.co/moonshotai/Kimi-Audio-7B)

</details>
<!-- /MODEL:kimi-audio.md -->

---

## Anything to Audio

Models that can generate audio from multiple input modalities (video, text, image, audio). These are unified frameworks for multimodal audio synthesis.

### Anything to Audio Quick Comparison

| Model | Text | Video | Image | Audio | License |
| :--- | :---: | :---: | :---: | :---: | :--- |
| [Woosh](#woosh) | ✅ | ✅ | — | — | ![Apache 2.0][license-apache-2.0] |
| [Uni-MoE (Audio)](#uni-moe-audio-any2audio) | ✅ | ✅ | — | — | ![Apache 2.0][license-apache-2.0] |
| [AudioX / Audio-Omni](#audiox) | ✅ | ✅ | — | ✅ | ![Apache 2.0][license-apache-2.0]<br>![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [HunyuanVideo-Foley](#hunyuanvideo-foley) | ✅ | ✅ | — | — | ![Unknown][license-unknown] |
| [PrismAudio](#prismaudio) | — | ✅ | — | — | ![Apache 2.0][license-apache-2.0] |
| [ThinkSound](#thinksound) | ✅ | — | — | ✅ | ![Apache 2.0][license-apache-2.0] |
| [MMAudio](#mmaudio) | ✅ | ✅ | ✅ | — | ![Apache 2.0][license-apache-2.0] |

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

**Innovation:** Optimized for sound effects (not general audio) with both public and private model versions. Video-conditioned generation without requiring captions. Competitive with Stable Audio Open and TangoFlux.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-Woosh--SFX-black?logo=github&style=flat)](https://github.com/SonyResearch/Woosh-SFX)
[![arXiv](https://img.shields.io/badge/arXiv-2604.01929-red&style=flat)](https://arxiv.org/abs/2604.01929)

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
[![GitHub](https://img.shields.io/badge/GitHub-Uni--MoE-black?logo=github&style=flat)](https://github.com/HITsz-TMG/Uni-MoE)
[![arXiv](https://img.shields.io/badge/arXiv-2510.13344-red&style=flat)](https://arxiv.org/abs/2510.13344)

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

**Innovation:** First unified framework covering all three audio domains. Combines frozen multimodal LLM (Qwen2.5-Omni) with trainable Diffusion Transformer for high-fidelity synthesis. Any-to-any audio processing.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-AudioX-black?logo=github&style=flat)](https://github.com/ZeyueT/AudioX)
[![GitHub](https://img.shields.io/badge/GitHub-Audio--Omni-black?logo=github&style=flat)](https://github.com/ZeyueT/Audio-Omni)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-audiox-yellow?logo=huggingface&style=flat)](https://huggingface.co/collections/HKUSTAudio/audiox)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-Audio--Omni-yellow?logo=huggingface&style=flat)](https://huggingface.co/HKUSTAudio/Audio-Omni)
[![arXiv](https://img.shields.io/badge/arXiv-2503.10522-red&style=flat)](https://arxiv.org/abs/2503.10522)

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
| **Audio Output** | 48 kHz |
| **Text** | ✅ |
| **Video** | ✅ |
| **License** | ![Unknown][license-unknown] |
| **High-Quality-Foley** | yes |
| **Context-Aware** | yes |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-HunyuanVideo--Foley-black?logo=github&style=flat)](https://github.com/Tencent-Hunyuan/HunyuanVideo-Foley)
[![Demo](https://img.shields.io/badge/Demo-HunyuanVideo--Foley-blue&style=flat)](https://huggingface.co/spaces/tencent/HunyuanVideo-Foley)
[![Website](https://img.shields.io/badge/Website-www.hunyuanvideofoley.org-blue&style=flat)](https://www.hunyuanvideofoley.org/)
[![arXiv](https://img.shields.io/badge/arXiv-2508.16930-red&style=flat)](https://arxiv.org/abs/2508.16930)

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

**Innovation:** **Performance Benchmarks:**

| Metric | VGGSound | AudioCanvas |
|--------|----------|-------------|
| Semantic (CLAP) | 0.47 | 0.52 |
| Temporal (DeSync↓) | 0.41 | 0.36 |
| Aesthetic (MOS-Q) | 4.21±0.35 | 4.12±0.28 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-prismaudio-black?logo=github&style=flat)](https://github.com/FunAudioLLM/ThinkSound/tree/prismaudio)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-PrismAudio-yellow?logo=huggingface&style=flat)](https://huggingface.co/FunAudioLLM/PrismAudio)
[![Demo](https://img.shields.io/badge/Demo-PrismAudio-blue&style=flat)](https://huggingface.co/spaces/FunAudioLLM/PrismAudio)
[![arXiv](https://img.shields.io/badge/arXiv-2511.18833-red&style=flat)](https://arxiv.org/abs/2511.18833)

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
[![GitHub](https://img.shields.io/badge/GitHub-ThinkSound-black?logo=github&style=flat)](https://github.com/FunAudioLLM/ThinkSound)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-ThinkSound-yellow?logo=huggingface&style=flat)](https://huggingface.co/liuHuadai/ThinkSound)
[![Demo](https://img.shields.io/badge/Demo-ThinkSound-blue&style=flat)](https://huggingface.co/spaces/FunAudioLLM/ThinkSound)

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
[![GitHub](https://img.shields.io/badge/GitHub-MMAudio-black?logo=github&style=flat)](https://github.com/hkchengrex/MMAudio)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-MMAudio-yellow?logo=huggingface&style=flat)](https://huggingface.co/hkchengrex/MMAudio)
[![Demo](https://img.shields.io/badge/Demo-MMAudio-blue&style=flat)](https://huggingface.co/spaces/hkchengrex/MMAudio)
[![arXiv](https://img.shields.io/badge/arXiv-2412.15322-red&style=flat)](https://arxiv.org/abs/2412.15322)

</details>
<!-- /MODEL:mmaudio.md -->

---

## Audio Restoration & Enhancement

### Audio Restoration & Enhancement Quick Comparison

| Model | Type | Bandwidth Extension | Inpainting | License |
| :--- | :---: | :---: | :---: | :--- |
| [AudioSR](#audiosr) | — | — | — | ![MIT][license-mit] |
| [NovaSR](#novasr) | — | — | — | ![Apache 2.0][license-apache-2.0] |
| [NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)](#nvidia-a2sb) | — | ✅ | ✅ | ![NVIDIA NC][license-nvidia-noncommercial] |

<!-- MODEL:audiosr.md -->
<details id="audiosr">
<summary>AudioSR</summary>

### AudioSR

**Description:** Audio super resolution model using latent diffusion to upscale low-quality audio to 48kHz.

**Release Date:** February 12, 2026 (v1.1.1)

| Feature | Value |
|---------|-------|
| **Audio Input** | 8kHz-48kHz |
| **Audio Output** | 48kHz |
| **License** | ![MIT][license-mit] |
| **Vram** | 6GB min |
| **Stereo** | yes |
| **Long-Audio** | yes |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-ComfyUI--AudioSR-black?logo=github&style=flat)](https://github.com/Saganaki22/ComfyUI-AudioSR)
[![arXiv](https://img.shields.io/badge/arXiv-2309.07314-red&style=flat)](https://arxiv.org/abs/2309.07314)

</details>
<!-- /MODEL:audiosr.md -->
<!-- MODEL:novasr.md -->
<details id="novasr">
<summary>NovaSR</summary>

### NovaSR

**Description:** Lightning fast audio upsampler - 50kB model that upscales 16kHz audio to 48kHz at 3500x realtime.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 52kB |
| **Audio Input** | 16kHz |
| **Audio Output** | 48kHz |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Speed** | 3600x realtime (A100) |
| **Vram** | Minimal |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-NovaSR-black?logo=github&style=flat)](https://github.com/ysharma3501/NovaSR)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-NovaSR-yellow?logo=huggingface&style=flat)](https://huggingface.co/YatharthS/NovaSR)

</details>
<!-- /MODEL:novasr.md -->
<!-- MODEL:nvidia-a2sb.md -->
<details id="nvidia-a2sb">
<summary>NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)</summary>

### NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)

**Description:** Diffusion-based audio restoration model tailored for high-resolution music at 44.1kHz. An end-to-end, vocoder-free, multi-task model capable of both bandwidth extension (predicting high-frequency components) and inpainting (re-generating missing segments). Can restore hour-long audio inputs without boundary artifacts.

**Release Date:** January 2025

| Feature | Value |
|---------|-------|
| **Architecture** | End-to-end vocoder-free |
| **Streaming** | ❌ |
| **Inpainting** | ✅ |
| **Bandwidth Extension** | ✅ |
| **License** | ![NVIDIA NC][license-nvidia-noncommercial] |
| **High-Resolution** | yes (44.1kHz) |
| **Long-Audio** | yes (hour-long) |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-diffusion--audio--restoration-black?logo=github&style=flat)](https://github.com/NVIDIA/diffusion-audio-restoration)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-audio_to_audio_schrodinger_bridge-yellow?logo=huggingface&style=flat)](https://huggingface.co/nvidia/audio_to_audio_schrodinger_bridge)
[![arXiv](https://img.shields.io/badge/arXiv-2501.11311-red&style=flat)](https://arxiv.org/abs/2501.11311)

</details>
<!-- /MODEL:nvidia-a2sb.md -->

---

## Speech Recognition (ASR)

### ASR Quick Comparison

| Model | Languages | Streaming | License |
| :--- | :--- | :---: | :--- |
| [Cohere Transcribe](#cohere-transcribe) | 14 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [VibeVoice-ASR](#vibevoice-asr) | 50+ | ✅ | ![MIT][license-mit] |
| [FunASR](#funasr) | 50+ | — | ![MIT][license-mit] |

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

**Innovation:** - Long-form transcription with automatic chunking (>35 seconds)
- Optional punctuation control
- Batched inference support
- vLLM integration for production serving
- Apple Silicon support via mlx-audio
- WebGPU browser deployment via transformers.js

**Links:**
[![HuggingFace](https://img.shields.io/badge/HuggingFace-cohere--transcribe--03--2026-yellow?logo=huggingface&style=flat)](https://huggingface.co/CohereLabs/cohere-transcribe-03-2026)
[![Demo](https://img.shields.io/badge/Demo-cohere--transcribe--03--2026-blue&style=flat)](https://huggingface.co/spaces/CohereLabs/cohere-transcribe-03-2026)
[![Blog](https://img.shields.io/badge/Blog-transcribe-blue&style=flat)](https://cohere.com/blog/transcribe)

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
[![GitHub](https://img.shields.io/badge/GitHub-VibeVoice-black?logo=github&style=flat)](https://github.com/microsoft/VibeVoice)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-VibeVoice--ASR-yellow?logo=huggingface&style=flat)](https://huggingface.co/microsoft/VibeVoice-ASR)

</details>
<!-- /MODEL:vibevoice-asr.md -->
<!-- MODEL:funasr.md -->
<details id="funasr">
<summary>FunASR</summary>

### FunASR

**Description:** Fundamental end-to-end speech recognition toolkit with SOTA pretrained models.

**Release Date:** Ongoing (First: 2023)

| Feature | Value |
|---------|-------|
| **Asr** | ✅ |
| **Languages** | 50+ |
| **Vad** | ✅ |
| **Punctuation** | ✅ |
| **Diarization** | ✅ |
| **Timestamps** | yes |
| **Emotion** | yes |
| **License** | ![MIT][license-mit] |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-FunASR-black?logo=github&style=flat)](https://github.com/modelscope/FunASR)
[![Website](https://img.shields.io/badge/Website-www.funasr.com-blue&style=flat)](https://www.funasr.com)

</details>
<!-- /MODEL:funasr.md -->

---

## Contributing

This list is continuously evolving. If you have any models to add or updates to suggest, please feel free to contribute! See [CONTRIBUTING.md](./CONTRIBUTING.md) for the template-driven workflow.

---

*Last Updated: July 2026*

<!-- MARKDOWN LINKS & IMAGES -->
[license-research-only]: https://img.shields.io/badge/Research_Only-orange?style=flat-square "Research Only"
[license-mit]: https://img.shields.io/badge/MIT-green?style=flat-square&logo=openldap "MIT"
[license-cc-by-nc-4.0]: https://img.shields.io/badge/CC_BY--NC_4.0-orange?style=flat-square&logo=creativecommons "CC BY-NC 4.0"
[license-apache-2.0]: https://img.shields.io/badge/Apache_2.0-green?style=flat-square&logo=apache "Apache 2.0"
[license-lfm]: https://img.shields.io/badge/LFM-blue?style=flat-square "LFM"
[license-openrail-m]: https://img.shields.io/badge/OpenRAIL--M-blueviolet?style=flat-square "OpenRAIL-M"
[license-nvidia-noncommercial]: https://img.shields.io/badge/NVIDIA_NC-yellow?style=flat-square&logo=nvidia "NVIDIA NC"
[license-unknown]: https://img.shields.io/badge/Unknown-lightgrey?style=flat-square "Unknown"
