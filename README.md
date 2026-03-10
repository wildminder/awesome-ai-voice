# Awesome TTS & Voice Generation Models

A curated list of open-source Text-to-Speech (TTS), voice cloning, and music generation models. Models are sorted by release date (newest first).

---

## Quick Comparison

| Model | Type | Voice Cloning | ASR | Languages | Streaming | License |
| :--- | :---: | :---: | :---: | :--- | :---: | :--- |
| [Fish Audio S2 Pro](#fish-audio-s2-pro) | TTS | ✅ | ❌ | 80+ | ✅ | Research License |
| [KittenTTS](#kittenTTS) | TTS | ✅ | ❌ | En+ | ✅ | Apache-2.0 |
| [MOSS-TTS](#moss-tts) | TTS | ✅ | ❌ | 20 | ✅ | Apache-2.0 |
| [SoulX-Singer](#soulx-singer) | TTS | ✅ (Singing) | ❌ | Zh/En/Canto | ✅ | Apache-2.0 |
| [SoproTTS](#soproTTS) | TTS | ✅ | ❌ | En | ✅ | Apache-2.0 |
| [NeuTTS](#neutts) | TTS | ✅ | ❌ | En/Es/De/Fr | ✅ | Apache-2.0 |
| [Qwen3-TTS](#qwen3-tts) | TTS | ✅ | ❌ | 10 | ✅ | Apache-2.0 |
| [VibeVoice-ASR](#vibevoice-asr) | ASR | ❌ | ✅ | 50+ | ✅ | MIT |
| [GLM-TTS](#glm-tts) | TTS | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [VibeVoice-Realtime](#vibevoice-realtime) | TTS | ✅ | ❌ | Multi | ✅ | MIT |
| [Fun-CosyVoice 3.0](#fun-cosyvoice-30) | TTS | ✅ | ❌ | 9 + 18 dialects | ✅ | Apache-2.0 |
| [MioTTS-2.6B](#miotts-26b) | TTS | ✅ | ❌ | En/Jp | ✅ | LFM |
| [KugelAudio](#kugelaudio) | TTS | ✅ | ❌ | 23 EU | ✅ | MIT |
| [IndexTTS2](#indextts2) | TTS | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [Maya1](#maya1) | TTS | ✅ | ❌ | En | ✅ | Apache-2.0 |
| [LFM2-Audio-1.5B](#lfm2-audio-15b) | TTS | ✅ | ✅ | En | ✅ | LFM |
| [Step-Audio-EditX](#step-audio-editx) | TTS | ✅ | ❌ | Zh/En/Jp/Ko | ✅ | Apache-2.0 |
| [FireRedTTS2](#fireredtts2) | TTS | ✅ | ❌ | 7 langs | ✅ | Apache-2.0 |
| [VoxCPM](#voxcpm) | TTS | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [LuxTTS](#luxtts) | TTS | ✅ | ❌ | - | ✅ | Apache-2.0 |
| [MegaTTS3](#megatts3) | TTS | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [Spark-TTS](#spark-tts) | TTS | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [Fish Speech](#fish-speech) | TTS | ✅ | ❌ | 8 langs | ✅ | Apache-2.0 |
| [Step-Audio](#step-audio) | TTS | ✅ | ✅ | Zh/En/Jp | ✅ | Apache-2.0 |
| [Audio Flamingo 3](#audio-flamingo-3-af3) | Audio LLM | ❌ | ✅ | Multi | ✅ | Apache-2.0 |
| [SoulX-Podcast](#soulx-podcast) | TTS | ✅ | ❌ | Zh/En/Canto | ✅ | Apache-2.0 |
| [Chatterbox](#chatterbox) | TTS | ✅ | ❌ | 23+ | ✅ | MIT |
| [Orpheus-TTS](#orpheus-tts) | TTS | ✅ | ❌ | Multi | ✅ | Apache-2.0 |
| [Dia](#dia) | TTS | ✅ | ❌ | En | ✅ | Apache-2.0 |
| [VieNeu-TTS](#vieneu-tts) | TTS | ✅ | ❌ | Vi | ✅ | Apache-2.0 |
| [MiMo-Audio](#mimo-audio) | Audio LLM | ✅ | ✅ | Multi | ✅ | Apache-2.0 |
| [Kimi-Audio](#kimi-audio) | Audio LLM | ✅ | ✅ | Multi | ✅ | MIT/Apache-2.0 |
| [ACE-Step 1.5](#ace-step-15) | Music | - | - | 50+ | ✅ | MIT |
| [Music Flamingo](#music-flamingo) | Music | - | - | - | - | Apache-2.0 |
| [Magenta Realtime](#magenta-realtime) | Music | - | - | - | ✅ | Apache-2.0/CC-BY-4.0 |
| [AudioX](#audiox) | Audio | - | - | - | ✅ | Apache-2.0 |
| [Uni-MoE (Audio)](#uni-moE-audio) | Audio | ✅ | - | - | ✅ | Apache-2.0 |
| [NovaSR](#novasr) | Enhancement | - | - | - | ✅ | Apache-2.0 |
| [AudioSR](#audiosr) | Enhancement | - | - | - | - | MIT |
| [ZipVoice](#zipvoice) | TTS | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [FunASR](#funasr) | ASR | - | ✅ | 50+ | ✅ | MIT |

**Legend:** ✅ = Supported | ❌ = Not Supported | - = N/A | En = English | Zh = Chinese | Jp = Japanese | Ko = Korean | Vi = Vietnamese | EU = European | Canto = Cantonese

---

## Table of Contents

- [Text-to-Speech (TTS) Models](#text-to-speech-tts-models)
- [Music Generation Models](#music-generation-models)
- [Audio Enhancement \& Processing](#audio-enhancement--processing)
- [Speech Recognition (ASR)](#speech-recognition-asr)
- [Multimodal \& Unified Models](#multimodal--unified-models)
- [Additional Resources](#additional-resources)

---

## Text-to-Speech (TTS) Models

### Fish Audio S2 Pro

**Description:** Fish Audio S2 Pro is a leading text-to-speech model with fine-grained inline control of prosody and emotion. It combines reinforcement learning alignment with a dual-autoregressive architecture for high-quality speech synthesis.

**Release Date:** March 10, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 5B (4B Slow AR + 400M Fast AR) |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ (15,000+ tags) |
| **Emotion Control** | ✅ (fine-grained inline control) |
| **Languages** | 80+ (Tier 1: En, Zh, Jp) |
| **Streaming** | ✅ (RTF 0.195, 100ms TTFA) |
| **Model Size** | ~10 GB (BF16) |
| **License** | Fish Audio Research License |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-fishaudio/fish--speech-black?logo=github&style=flat)](https://github.com/fishaudio/fish-speech)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-fishaudio/s2--pro-yellow?logo=huggingface&style=flat)](https://huggingface.co/fishaudio/s2-pro)

---

### KittenTTS

**Description:** KittenTTS is an open-source realistic text-to-speech model designed for lightweight deployment. It is a state-of-the-art TTS model under 25MB with just 15 million parameters, running without GPU on any device.

**Release Date:** February 24, 2026 (v0.8.1)

| Feature | Value |
|---------|-------|
| **Parameters** | 15M-80M |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | English, Multiple |
| **Streaming** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-KittenML/KittenTTS-black?logo=github&style=flat)](https://github.com/KittenML/KittenTTS)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Demo-yellow?logo=huggingface&style=flat)](https://huggingface.co/spaces/KittenML/KittenTTS-Demo)

---

### MOSS-TTS

**Description:** MOSS-TTS is a production-grade Text-to-Speech foundation model developed by OpenMOSS Team and MOSI.AI. Features state-of-the-art evaluation performance on Seed-TTS-eval benchmark with zero-shot voice cloning.

**Release Date:** February 10, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 8B (Delay), 1.7B (Local) |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ (Pinyin/Phoneme-level) |
| **Emotion Control** | ✅ |
| **Languages** | 20 languages |
| **Streaming** | ✅ |
| **Max Duration** | 1 hour |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-OpenMOSS/MOSS--TTS-black?logo=github&style=flat)](https://github.com/OpenMOSS/MOSS-TTS)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-OpenMOSS--Team/MOSS--TTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/OpenMOSS-Team/MOSS-TTS)
[![Project Page](https://img.shields.io/badge/Project-mosi.cn-blue&style=flat)](https://mosi.cn/models/moss-tts)

---

### SoulX-Singer

**Description:** SoulX-Singer is a high-fidelity, zero-shot singing voice synthesis model for generating realistic singing voices for unseen singers without fine-tuning.

**Release Date:** February 6, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Zero-shot Voice Cloning** | ✅ (Singing) |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ (MIDI/F0) |
| **Emotion Control** | ✅ |
| **Languages** | Mandarin, English, Cantonese |
| **Streaming** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-Soul--AILab/SoulX--Singer-black?logo=github&style=flat)](https://github.com/Soul-AILab/SoulX-Singer)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Soul--AILab/SoulX--Singer-yellow?logo=huggingface&style=flat)](https://huggingface.co/spaces/Soul-AILab/SoulX-Singer)
[![arXiv](https://img.shields.io/badge/arXiv-2602.07803-red&style=flat)](https://arxiv.org/abs/2602.07803)

---

### SoproTTS

**Description:** SoproTTS is a lightweight English text-to-speech model with zero-shot voice cloning. It uses dilated convolutions (WaveNet-style) and lightweight cross-attention layers instead of the common Transformer architecture.

**Release Date:** February 4, 2026 (v1.5)

| Feature | Value |
|---------|-------|
| **Parameters** | 135M |
| **Zero-shot Voice Cloning** | ✅ (3-12s) |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ✅ (style_strength) |
| **Languages** | English |
| **Streaming** | ✅ (250ms TTFA) |
| **RTF** | 0.05 (CPU M3) |
| **Training Cost** | ~$100 |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-samuel-vitorino/sopro-black?logo=github&style=flat)](https://github.com/samuel-vitorino/sopro)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-samuel--vitorino/sopro-yellow?logo=huggingface&style=flat)](https://huggingface.co/samuel-vitorino/sopro)

---

### NeuTTS

**Description:** NeuTTS is a collection of open-source on-device TTS models with instant voice cloning. Built off LLM backbones with GGUF format quantizations for efficient on-device deployment.

**Release Date:** Early 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 360M (Air), 120M (Nano) |
| **Zero-shot Voice Cloning** | ✅ (3-second) |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | English, Spanish, German, French |
| **Streaming** | ✅ |
| **On-Device** | ✅ (GGUF quantizations) |
| **License** | Apache-2.0 (Air), NeuTTS Open License 1.0 (Nano) |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-neuphonic/neutts-black?logo=github&style=flat)](https://github.com/neuphonic/neutts)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-neuphonic/neutts--air-yellow?logo=huggingface&style=flat)](https://huggingface.co/neuphonic/neutts-air)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-neuphonic/neutts--nano-yellow?logo=huggingface&style=flat)](https://huggingface.co/neuphonic/neutts-nano)

---

### Qwen3-TTS

**Description:** Qwen3-TTS is an open-source series of Text-to-Speech models developed by Alibaba Cloud. Supports stable, expressive, and streaming speech generation with free-form voice design.

**Release Date:** January 22, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 0.6B-1.7B |
| **Zero-shot Voice Cloning** | ✅ (3-second) |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 10 (Chinese, English, Japanese, Korean, German, French, Russian, Portuguese, Spanish, Italian) |
| **Streaming** | ✅ (97ms latency) |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-QwenLM/Qwen3--TTS-black?logo=github&style=flat)](https://github.com/QwenLM/Qwen3-TTS)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Qwen/Qwen3--TTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/collections/Qwen/qwen3-tts)
[![arXiv](https://img.shields.io/badge/arXiv-2601.15621-red&style=flat)](https://arxiv.org/abs/2601.15621)

---

### VibeVoice-ASR

**Description:** Microsoft's unified speech-to-text model for 60-minute long-form audio processing with speaker diarization and timestamping.

**Release Date:** January 21, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Zero-shot Voice Cloning** | ❌ |
| **ASR** | ✅ |
| **Pronunciation Control** | N/A |
| **Emotion Control** | ❌ |
| **Languages** | 50+ |
| **Streaming** | ✅ |
| **License** | MIT |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-microsoft/VibeVoice-black?logo=github&style=flat)](https://github.com/microsoft/VibeVoice)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-microsoft/VibeVoice--ASR-yellow?logo=huggingface&style=flat)](https://huggingface.co/microsoft/VibeVoice-ASR)

---

### GLM-TTS

**Description:** High-quality TTS synthesis system based on LLMs from ZhipuAI, supporting zero-shot voice cloning with Multi-Reward Reinforcement Learning.

**Release Date:** December 11, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Zero-shot Voice Cloning** | ✅ (3-10s) |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ (Phoneme-level) |
| **Emotion Control** | ✅ (RL-enhanced) |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-zai--org/GLM--TTS-black?logo=github&style=flat)](https://github.com/zai-org/GLM-TTS)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-zai--org/GLM--TTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/zai-org/GLM-TTS)
[![arXiv](https://img.shields.io/badge/arXiv-2512.14291-red&style=flat)](https://arxiv.org/abs/2512.14291)

---

### VibeVoice-Realtime

**Description:** Real-time TTS model from Microsoft with streaming text input and ultra-low latency (~300ms).

**Release Date:** December 3, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.5B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Multilingual |
| **Streaming** | ✅ (300ms) |
| **Max Duration** | ~10 minutes |
| **License** | MIT |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-microsoft/VibeVoice-black?logo=github&style=flat)](https://github.com/microsoft/VibeVoice)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-microsoft/VibeVoice--Realtime--0.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/microsoft/VibeVoice-Realtime-0.5B)

---

### Fun-CosyVoice 3.0

**Description:** Advanced TTS system based on LLMs for zero-shot multilingual speech synthesis from FunAudioLLM.

**Release Date:** December 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.5B |
| **Zero-shot Voice Cloning** | ✅ (Multi-lingual/Cross-lingual) |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ (Pinyin/CMU) |
| **Emotion Control** | ✅ |
| **Languages** | 9 + 18+ Chinese dialects |
| **Streaming** | ✅ (150ms) |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-FunAudioLLM/CosyVoice-black?logo=github&style=flat)](https://github.com/FunAudioLLM/CosyVoice)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FunAudioLLM/Fun--CosyVoice3--0.5B--2512-yellow?logo=huggingface&style=flat)](https://huggingface.co/FunAudioLLM/Fun-CosyVoice3-0.5B-2512)
[![arXiv](https://img.shields.io/badge/arXiv-2505.17589-red&style=flat)](https://arxiv.org/abs/2505.17589)

---

### MioTTS-2.6B

**Description:** Lightweight, high-speed LLM-based TTS model for English and Japanese with minimal resource usage.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2.6B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | English, Japanese |
| **Streaming** | ✅ |
| **RTF** | 0.135-0.145 |
| **License** | LFM Open License |

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Aratako/MioTTS--2.6B-yellow?logo=huggingface&style=flat)](https://huggingface.co/Aratako/MioTTS-2.6B)
[![GitHub](https://img.shields.io/badge/GitHub-Aratako/MioTTS--Inference-black?logo=github&style=flat)](https://github.com/Aratako/MioTTS-Inference)

---

### KugelAudio

**Description:** Open-source TTS for European languages with 7B parameters. Outperformed ElevenLabs in human preference testing.

**Release Date:** Early 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ (Speaking styles) |
| **Languages** | 23 European languages |
| **Streaming** | ✅ |
| **License** | MIT |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-Kugelaudio/kugelaudio--open-black?logo=github&style=flat)](https://github.com/Kugelaudio/kugelaudio-open)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-kugelaudio/kugelaudio--0--open-yellow?logo=huggingface&style=flat)](https://huggingface.co/kugelaudio/kugelaudio-0-open)
[![Website](https://img.shields.io/badge/Website-kugelaudio.com-blue&style=flat)](https://kugelaudio.com)

---

### IndexTTS2

**Description:** AI-Enhanced Text-to-Speech System with Intelligent Optimization and self-learning capabilities.

**Release Date:** November 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ (5 emotions) |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **Multi-speaker** | ✅ (1-4 speakers) |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-xuchenxu168/Comfyui--Index--TTS2-black?logo=github&style=flat)](https://github.com/xuchenxu168/Comfyui-Index-TTS2)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-IndexTeam/IndexTTS--2-yellow?logo=huggingface&style=flat)](https://huggingface.co/IndexTeam/IndexTTS-2)

---

### Maya1

**Description:** State-of-the-art speech model for expressive voice generation with natural language voice control.

**Release Date:** November 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 3B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ (Tags) |
| **Languages** | English (Multi-accent) |
| **Streaming** | ✅ (<100ms) |
| **License** | Apache-2.0 |

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-maya--research/maya1-yellow?logo=huggingface&style=flat)](https://huggingface.co/maya-research/maya1)
[![Website](https://img.shields.io/badge/Website-mayaresearch.ai-blue&style=flat)](https://mayaresearch.ai)

---

### LFM2-Audio-1.5B

**Description:** Liquid AI's first end-to-end audio foundation model with low latency and real-time conversation.

**Release Date:** November 28, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 1.5B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ✅ (Integrated) |
| **Pronunciation Control** | N/A |
| **Emotion Control** | ✅ |
| **Languages** | English |
| **Streaming** | ✅ |
| **License** | LFM Open License |

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-LiquidAI/LFM2--Audio--1.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/LiquidAI/LFM2-Audio-1.5B)
[![Website](https://img.shields.io/badge/Website-docs.liquid.ai-blue&style=flat)](https://docs.liquid.ai/lfm)

---

### Step-Audio-EditX

**Description:** 3B-parameter LLM-based RL audio model specialized in expressive and iterative audio editing.

**Release Date:** November 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 3B (4B BF16) |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ (Polyphone) |
| **Emotion Control** | ✅ (14 emotions) |
| **Languages** | Mandarin, English, Sichuanese, Cantonese, Japanese, Korean |
| **Streaming** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-stepfun--ai/Step--Audio--EditX-yellow?logo=huggingface&style=flat)](https://huggingface.co/stepfun-ai/Step-Audio-EditX)
[![arXiv](https://img.shields.io/badge/arXiv-2511.03601-red&style=flat)](https://arxiv.org/abs/2511.03601)

---

### FireRedTTS2

**Description:** Long-form streaming TTS system for multi-speaker dialogue generation with stable, natural speech.

**Release Date:** September 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | EN, ZH, JP, KO, FR, DE, RU |
| **Streaming** | ✅ (140ms) |
| **Multi-speaker** | ✅ (4 speakers) |
| **Max Duration** | 3 minutes |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-FireRedTeam/FireRedTTS2-black?logo=github&style=flat)](https://github.com/FireRedTeam/FireRedTTS2)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FireRedTeam/FireRedTTS2-yellow?logo=huggingface&style=flat)](https://huggingface.co/FireRedTeam/FireRedTTS2)
[![arXiv](https://img.shields.io/badge/arXiv-2509.02020-red&style=flat)](https://arxiv.org/abs/2509.02020)

---

### VoxCPM

**Description:** Tokenizer-free TTS system for context-aware speech generation and true-to-life voice cloning.

**Release Date:** September 16, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 640M-800M |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ (RTF 0.17) |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-OpenBMB/VoxCPM-black?logo=github&style=flat)](https://github.com/OpenBMB/VoxCPM)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-openbmb/VoxCPM--0.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/openbmb/VoxCPM-0.5B)
[![arXiv](https://img.shields.io/badge/arXiv-2509.24650-red&style=flat)](https://arxiv.org/abs/2509.24650)

---

### LuxTTS

**Description:** Lightweight ZipVoice-based TTS model for high quality voice cloning at speeds exceeding 150x realtime.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | - |
| **Streaming** | ✅ |
| **RTF** | 150x |
| **VRAM** | 1GB |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-ysharma3501/LuxTTS-black?logo=github&style=flat)](https://github.com/ysharma3501/LuxTTS)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-YatharthS/LuxTTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/YatharthS/LuxTTS)

---

### MegaTTS3

**Description:** Advanced zero-shot speech synthesis with Sparse Alignment Enhanced Latent Diffusion Transformer.

**Release Date:** March 22, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.45B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-bytedance/MegaTTS3-black?logo=github&style=flat)](https://github.com/bytedance/MegaTTS3)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-ByteDance/MegaTTS3-yellow?logo=huggingface&style=flat)](https://huggingface.co/spaces/ByteDance/MegaTTS3)
[![arXiv](https://img.shields.io/badge/arXiv-2502.18924-red&style=flat)](https://arxiv.org/abs/2502.18924)

---

### Spark-TTS

**Description:** Efficient LLM-Based TTS Model with Single-Stream Decoupled Speech Tokens, built on Qwen2.5.

**Release Date:** March 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.5B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-SparkAudio/Spark--TTS-black?logo=github&style=flat)](https://github.com/SparkAudio/Spark-TTS)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-SparkAudio/Spark--TTS--0.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/SparkAudio/Spark-TTS-0.5B)
[![arXiv](https://img.shields.io/badge/arXiv-2503.01710-red&style=flat)](https://arxiv.org/abs/2503.01710)

---

### Fish Speech

**Description:** State-of-the-art open source TTS and voice cloning model that generates natural, realistic, and emotionally rich speech.

**Release Date:** May 31, 2025 (v1.5.1)

| Feature | Value |
|---------|-------|
| **Parameters** | 4B (S1), 0.5B (S1-mini) |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 8 (EN, JP, KO, ZH, FR, DE, AR, ES) |
| **Streaming** | ✅ |
| **RTF** | ~1:7 |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-fishaudio/fish--speech-black?logo=github&style=flat)](https://github.com/fishaudio/fish-speech)
[![Website](https://img.shields.io/badge/Website-fish.audio-blue&style=flat)](https://fish.audio/)

---

### Step-Audio

**Description:** Production-ready open-source framework for intelligent speech interaction with unified speech comprehension and generation.

**Release Date:** February 17, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 130B (Chat), 3B (TTS) |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ✅ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English, Japanese |
| **Streaming** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-stepfun--ai/Step--Audio-black?logo=github&style=flat)](https://github.com/stepfun-ai/Step-Audio)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-stepfun--ai-yellow?logo=huggingface&style=flat)](https://huggingface.co/stepfun-ai)
[![arXiv](https://img.shields.io/badge/arXiv-2502.11946-red&style=flat)](https://arxiv.org/abs/2502.11946)

---

### Audio Flamingo 3 (AF3)

**Description:** Fully open-source Large Audio Language Model from NVIDIA ADLR with state-of-the-art audio understanding.

**Release Date:** July 9, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Zero-shot Voice Cloning** | ❌ |
| **ASR** | ✅ |
| **Pronunciation Control** | N/A |
| **Emotion Control** | ✅ |
| **Languages** | Multi-lingual |
| **Streaming** | ✅ |
| **Context** | 10 minutes |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-NVIDIA/audio--flamingo-black?logo=github&style=flat)](https://github.com/NVIDIA/audio-flamingo)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-nvidia/audio--flamingo--3-yellow?logo=huggingface&style=flat)](https://huggingface.co/nvidia/audio-flamingo-3)

---

### SoulX-Podcast

**Description:** SOTA Multi-Speaker TTS model for generating realistic long-form podcasts with dialectal diversity.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Mandarin, English, Cantonese, Sichuanese, Henanese |
| **Streaming** | ✅ |
| **Max Duration** | 90+ minutes |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-Soul--AILab/SoulX--Podcast-black?logo=github&style=flat)](https://github.com/Soul-AILab/SoulX-Podcast)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Soul--AILab/soulx--podcast-yellow?logo=huggingface&style=flat)](https://huggingface.co/collections/Soul-AILab/soulx-podcast)
[![arXiv](https://img.shields.io/badge/arXiv-2510.23541-red&style=flat)](https://arxiv.org/abs/2510.23541)

---

### Chatterbox

**Description:** Family of SOTA open-source TTS models by Resemble AI with zero-shot voice cloning and multilingual synthesis.

**Release Date:** June 13, 2025 (v0.1.2)

| Feature | Value |
|---------|-------|
| **Parameters** | 350M-500M |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ (Tags) |
| **Languages** | 23+ |
| **Streaming** | ✅ |
| **License** | MIT |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-resemble--ai/chatterbox-black?logo=github&style=flat)](https://github.com/resemble-ai/chatterbox)
[![Website](https://img.shields.io/badge/Website-resemble.ai-blue&style=flat)](https://resemble.ai/)

---

### Orpheus-TTS

**Description:** SOTA open-source TTS built on Llama-3b backbone demonstrating emergent capabilities of LLMs for speech synthesis.

**Release Date:** April 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 3B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Multilingual |
| **Streaming** | ✅ (200ms) |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-canopyai/Orpheus--TTS-black?logo=github&style=flat)](https://github.com/canopyai/Orpheus-TTS)
[![Website](https://img.shields.io/badge/Website-canopylabs.ai-blue&style=flat)](https://canopylabs.ai/model-releases)

---

### Dia

**Description:** 1.6B parameter TTS model by Nari Labs for generating ultra-realistic dialogue in one pass.

**Release Date:** June 27, 2024

| Feature | Value |
|---------|-------|
| **Parameters** | 1.6B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | English |
| **Streaming** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-nari--labs/dia-black?logo=github&style=flat)](https://github.com/nari-labs/dia)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-nari--labs/Dia--1.6B--0626-yellow?logo=huggingface&style=flat)](https://huggingface.co/nari-labs/Dia-1.6B-0626)

---

### VieNeu-TTS

**Description:** Advanced on-device Vietnamese TTS model with instant voice cloning from 3-5 seconds of reference audio.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 0.3B-0.6B |
| **Zero-shot Voice Cloning** | ✅ (3-5s) |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ❌ |
| **Languages** | Vietnamese |
| **Streaming** | ✅ (On-device) |
| **License** | Apache-2.0 |

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-pnnbao--ump/VieNeu--TTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/pnnbao-ump/VieNeu-TTS)
[![GitHub](https://img.shields.io/badge/GitHub-pnnbao97/VieNeu--TTS-black?logo=github&style=flat)](https://github.com/pnnbao97/VieNeu-TTS)

---

### MiMo-Audio

**Description:** Audio Language Model by Xiaomi functioning as a Few-Shot Learner with SOTA audio understanding.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ✅ |
| **Pronunciation Control** | N/A |
| **Emotion Control** | ✅ |
| **Languages** | Multi-lingual |
| **Streaming** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-XiaomiMiMo/MiMo--Audio-black?logo=github&style=flat)](https://github.com/XiaomiMiMo/MiMo-Audio)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-XiaomiMiMo/mimo--audio-yellow?logo=huggingface&style=flat)](https://huggingface.co/collections/XiaomiMiMo/mimo-audio-68cc7202692c27dae881cce0)

---

### Kimi-Audio

**Description:** Open-source audio foundation model by Moonshot AI for audio understanding, generation, and conversation.

**Release Date:** 2024

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ✅ |
| **Pronunciation Control** | N/A |
| **Emotion Control** | ✅ |
| **Languages** | Multi-lingual |
| **Streaming** | ✅ |
| **License** | MIT/Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-MoonshotAI/Kimi--Audio-black?logo=github&style=flat)](https://github.com/MoonshotAI/Kimi-Audio)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-moonshotai/Kimi--Audio--7B-yellow?logo=huggingface&style=flat)](https://huggingface.co/moonshotai/Kimi-Audio-7B)

---

## Music Generation Models

### ACE-Step 1.5

**Description:** The most powerful local music generation model outperforming most commercial alternatives. Supports Mac, AMD, Intel, and CUDA devices.

**Release Date:** February 20, 2026 (v0.1.2)

| Feature | Value |
|---------|-------|
| **Parameters** | 0.6B-4B (LM), DiT variants |
| **Music Generation** | ✅ |
| **Lyrics Support** | ✅ (50+ languages) |
| **Voice2BGM** | ✅ |
| **Reference Audio** | ✅ |
| **Track Separation** | ✅ |
| **Duration** | 10s - 10min |
| **VRAM** | <4GB |
| **Platforms** | CUDA, MPS, ROCm, XPU, CPU |
| **License** | MIT |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-ace--step/ACE--Step--1.5-black?logo=github&style=flat)](https://github.com/ace-step/ACE-Step-1.5)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-ACE--Step/Ace--Step1.5-yellow?logo=huggingface&style=flat)](https://huggingface.co/ACE-Step/Ace-Step1.5)
[![Website](https://img.shields.io/badge/Website-ace--step.github.io-blue&style=flat)](https://ace-step.github.io/ace-step-v1.5.github.io/)
[![arXiv](https://img.shields.io/badge/arXiv-2602.00744-red&style=flat)](https://arxiv.org/abs/2602.00744)

---

### Music Flamingo

**Description:** Large audio-language model designed to advance music (including song) understanding. Achieves SOTA on 10+ music benchmarks.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Music Understanding** | ✅ |
| **Music Generation** | ❌ |
| **Rich Captions** | ✅ |
| **Music QA** | ✅ |
| **Reasoning** | ✅ (Chain-of-thought) |
| **Long-form** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![Website](https://img.shields.io/badge/Website-musicflamingo.github.io-blue&style=flat)](https://musicflamingo.github.io/)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-google/music--flamingo-yellow?logo=huggingface&style=flat)](https://huggingface.co/google/music-flamingo)

---

### Magenta Realtime

**Description:** Open music generation model from Google DeepMind enabling continuous generation of musical audio steered by text prompts or audio examples.

**Release Date:** August 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Music Generation** | ✅ (Real-time) |
| **Text-to-Music** | ✅ |
| **Audio-to-Music** | ✅ |
| **Reference Audio** | ✅ |
| **Continuous Generation** | ✅ |
| **Latency** | Style prompt 2s+ |
| **Context** | 10 seconds |
| **Training Data** | ~190k hours |
| **License** | Apache-2.0 (code), CC-BY-4.0 (model) |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-magenta/magenta--realtime-black?logo=github&style=flat)](https://github.com/magenta/magenta-realtime)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-google/magenta--realtime-yellow?logo=huggingface&style=flat)](https://huggingface.co/google/magenta-realtime)
[![arXiv](https://img.shields.io/badge/arXiv-2508.04651-red&style=flat)](https://arxiv.org/abs/2508.04651)

---

### AudioX

**Description:** Unified framework for anything-to-audio generation integrating text, video, image, and audio conditions. Accepted to ICLR 2026.

**Release Date:** March 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Text-to-Audio** | ✅ |
| **Text-to-Music** | ✅ |
| **Video-to-Audio** | ✅ |
| **Audio Inpainting** | ✅ |
| **Music Completion** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-ZeyueT/AudioX-black?logo=github&style=flat)](https://github.com/ZeyueT/AudioX)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-HKUSTAudio/audiox-yellow?logo=huggingface&style=flat)](https://huggingface.co/collections/HKUSTAudio/audiox)
[![arXiv](https://img.shields.io/badge/arXiv-2503.10522-red&style=flat)](https://arxiv.org/abs/2503.10522)

---

### SoulX-Singer

*(Already listed in TTS - singing voice synthesis)*

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Singing Generation** | ✅ |
| **Zero-shot** | ✅ |
| **Melody Control** | ✅ (F0/MIDI) |
| **Languages** | Mandarin, English, Cantonese |
| **License** | Apache-2.0 |

---

### Uni-MoE (Audio)

**Description:** MoE-based omnimodal model with voice cloning, TTS, T2M (text-to-music), and V2M (video-to-music).

**Release Date:** October 16, 2025 (Uni-MoE-Audio)

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Voice Cloning** | ✅ |
| **TTS** | ✅ |
| **Text-to-Music** | ✅ |
| **Video-to-Music** | ✅ |
| **Dynamic Routing** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-HITsz--TMG/Uni--MoE-black?logo=github&style=flat)](https://github.com/HITsz-TMG/Uni-MoE)
[![arXiv](https://img.shields.io/badge/arXiv-2510.13344-red&style=flat)](https://arxiv.org/abs/2510.13344)

---

## Audio Enhancement & Processing

### NovaSR

**Description:** Lightning fast audio upsampler - 50kB model that upscales 16kHz audio to 48kHz at 3500x realtime.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Size** | 52kB |
| **Speed** | 3600x realtime (A100) |
| **Input** | 16kHz |
| **Output** | 48kHz |
| **VRAM** | Minimal |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-ysharma3501/NovaSR-black?logo=github&style=flat)](https://github.com/ysharma3501/NovaSR)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-YatharthS/NovaSR-yellow?logo=huggingface&style=flat)](https://huggingface.co/YatharthS/NovaSR)

---

### AudioSR

**Description:** Audio super resolution model using latent diffusion to upscale low-quality audio to 48kHz.

**Release Date:** February 12, 2026 (v1.1.1)

| Feature | Value |
|---------|-------|
| **Input** | 8kHz-48kHz |
| **Output** | 48kHz |
| **VRAM** | 6GB min |
| **Stereo** | ✅ |
| **Long Audio** | ✅ |
| **License** | MIT |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-Saganaki22/ComfyUI--AudioSR-black?logo=github&style=flat)](https://github.com/Saganaki22/ComfyUI-AudioSR)
[![arXiv](https://img.shields.io/badge/arXiv-2309.07314-red&style=flat)](https://arxiv.org/abs/2309.07314)

---

### ZipVoice

**Description:** Fast and high-quality zero-shot TTS models based on flow matching.

**Release Date:** June 16, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 123M |
| **Zero-shot Cloning** | ✅ |
| **Languages** | Chinese, English |
| **Dialogue** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-k2--fsa/ZipVoice-black?logo=github&style=flat)](https://github.com/k2-fsa/ZipVoice)
[![Website](https://img.shields.io/badge/Website-zipvoice.github.io-blue&style=flat)](https://zipvoice.github.io/)
[![arXiv](https://img.shields.io/badge/arXiv-2506.13053-red&style=flat)](https://arxiv.org/abs/2506.13053)

---

## Speech Recognition (ASR)

### FunASR

**Description:** Fundamental end-to-end speech recognition toolkit with SOTA pretrained models.

**Release Date:** Ongoing (First: 2023)

| Feature | Value |
|---------|-------|
| **ASR** | ✅ |
| **VAD** | ✅ |
| **Punctuation** | ✅ |
| **Speaker Diarization** | ✅ |
| **Multi-talker ASR** | ✅ |
| **Timestamp** | ✅ |
| **Emotion Recognition** | ✅ |
| **Languages** | 50+ |
| **License** | MIT/Model License |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-modelscope/FunASR-black?logo=github&style=flat)](https://github.com/modelscope/FunASR)
[![Website](https://img.shields.io/badge/Website-funasr.com-blue&style=flat)](https://www.funasr.com)

---

## Additional Resources

### ComfyUI Integrations

---

## License Notes

Different models have different licenses:
- **Apache-2.0:** Most common open-source license
- **MIT:** KugelAudio, Chatterbox, Kimi-Audio
- **CC-BY-NC-SA-4.0:** Echo-TTS (research and non-commercial)
- **LFM Open License:** MioTTS, LFM2-Audio
- **Model-specific:** Some models have additional restrictions

*Please check each model's license before commercial use.*

---

## Contributing

This list is continuously evolving. If you have any models to add or updates to suggest, please feel free to contribute!

---

*Last Updated: March 2026*
