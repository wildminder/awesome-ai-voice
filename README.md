# Awesome TTS & Voice Generation Models

A curated list of open-source Text-to-Speech (TTS), voice cloning, and music generation models. Models are sorted by release date (newest first).

---

## Table of Contents

- [Text-to-Speech (TTS) Models](#text-to-speech-tts-models)
- [Music Generation Models](#music-generation-models)
- [Anything to Audio](#anything-to-audio)
- [Audio Restoration & Enhancement](#audio-restoration--enhancement)
- [Speech Recognition (ASR)](#speech-recognition-asr)
- [Additional Resources](#additional-resources)

---

## Text-to-Speech (TTS) Models

### TTS Quick Comparison

| Model | Voice Cloning | ASR | Languages | Streaming | License |
| :--- | :---: | :---: | :--- | :---: | :--- |
| [Fish Audio S2 Pro](#fish-audio-s2-pro) | ✅ | ❌ | 80+ | ✅ | Research License |
| [KittenTTS](#kittenTTS) | ✅ | ❌ | En+ | ✅ | Apache-2.0 |
| [MOSS-TTS](#moss-tts) | ✅ | ❌ | 20 | ✅ | Apache-2.0 |
| [SoulX-Singer](#soulx-singer) | ✅ (Singing) | ❌ | Zh/En/Canto | ✅ | Apache-2.0 |
| [SoproTTS](#soprotts) | ✅ | ❌ | En | ✅ | Apache-2.0 |
| [NeuTTS](#neutts) | ✅ | ❌ | En/Es/De/Fr | ✅ | Apache-2.0 |
| [Qwen3-TTS](#qwen3-tts) | ✅ | ❌ | 10 | ✅ | Apache-2.0 |
| [GLM-TTS](#glm-tts) | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [VibeVoice-Realtime](#vibevoice-realtime) | ✅ | ❌ | Multi | ✅ | MIT |
| [Fun-CosyVoice 3.0](#fun-cosyvoice-30) | ✅ | ❌ | 9 + 18 dialects | ✅ | Apache-2.0 |
| [MioTTS-2.6B](#miotts-26b) | ✅ | ❌ | En/Jp | ✅ | LFM |
| [Supertonic 2](#supertonic-2) | ❌ | ❌ | 5 | ✅ | OpenRAIL-M |
| [KugelAudio](#kugelaudio) | ✅ | ❌ | 23 EU | ✅ | MIT |
| [Kokoro-82M](#kokoro-82m) | ✅ | ❌ | 8 (54 voices) | ✅ | Apache-2.0 |
| [KokoClone](#kokoclone) | ✅ | ❌ | 7 | ✅ | Apache-2.0 |
| [IndexTTS2](#indextts2) | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [Maya1](#maya1) | ✅ | ❌ | En | ✅ | Apache-2.0 |
| [LFM2-Audio-1.5B](#lfm2-audio-15b) | ✅ | ✅ | En | ✅ | LFM |
| [Step-Audio-EditX](#step-audio-editx) | ✅ | ❌ | Zh/En/Jp/Ko | ✅ | Apache-2.0 |
| [FireRedTTS2](#fireredtts2) | ✅ | ❌ | 7 langs | ✅ | Apache-2.0 |
| [VoxCPM](#voxcpm) | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [LuxTTS](#luxtts) | ✅ | ❌ | - | ✅ | Apache-2.0 |
| [MegaTTS3](#megatts3) | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [Spark-TTS](#spark-tts) | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |
| [Fish Speech](#fish-speech) | ✅ | ❌ | 8 langs | ✅ | Apache-2.0 |
| [Step-Audio](#step-audio) | ✅ | ✅ | Zh/En/Jp | ✅ | Apache-2.0 |
| [SoulX-Podcast](#soulx-podcast) | ✅ | ❌ | Zh/En/Canto | ✅ | Apache-2.0 |
| [Chatterbox](#chatterbox) | ✅ | ❌ | 23+ | ✅ | MIT |
| [Orpheus-TTS](#orpheus-tts) | ✅ | ❌ | Multi | ✅ | Apache-2.0 |
| [Dia](#dia) | ✅ | ❌ | En | ✅ | Apache-2.0 |
| [VieNeu-TTS](#vieneu-tts) | ✅ | ❌ | Vi | ✅ | Apache-2.0 |
| [MiMo-Audio](#mimo-audio) | ✅ | ✅ | Multi | ✅ | Apache-2.0 |
| [Kimi-Audio](#kimi-audio) | ✅ | ✅ | Multi | ✅ | MIT/Apache-2.0 |
| [ZipVoice](#zipvoice) | ✅ | ❌ | Zh/En | ✅ | Apache-2.0 |

<details id="fish-audio-s2-pro">
<summary>Fish Audio S2 Pro</summary>

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

</details>

<details id="kittenTTS">
<summary>KittenTTS</summary>

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

</details>

<details id="moss-tts">
<summary>MOSS-TTS</summary>

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

</details>

<details id="soulx-singer">
<summary>SoulX-Singer</summary>

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

</details>

<details id="soprotts">
<summary>SoproTTS</summary>

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

</details>

<details id="neutts">
<summary>NeuTTS</summary>

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

</details>

<details id="qwen3-tts">
<summary>Qwen3-TTS</summary>

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

</details>

<details id="glm-tts">
<summary>GLM-TTS</summary>

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

</details>

<details id="vibevoice-realtime">
<summary>VibeVoice-Realtime</summary>

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

</details>

<details id="fun-cosyvoice-30">
<summary>Fun-CosyVoice 3.0</summary>

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

</details>

<details id="miotts-26b">
<summary>MioTTS-2.6B</summary>

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

</details>

<details id="supertonic-2">
<summary>Supertonic 2</summary>

### Supertonic 2

**Description:** Lightning-fast, on-device text-to-speech system designed for extreme performance with minimal computational overhead. Powered by ONNX Runtime, it runs entirely on-device—no cloud, no API calls, no privacy concerns. Outperforms ElevenLabs Flash v2.5 by up to 42× in speed benchmarks.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 66M |
| **Zero-shot Voice Cloning** | ❌ |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | English, Korean, Spanish, Portuguese, French |
| **Streaming** | ✅ |
| **RTF** | 0.001-0.015 (up to 167× realtime) |
| **On-Device** | ✅ (ONNX Runtime) |
| **License** | OpenRAIL-M |

**Performance Comparison:**

| System | Speed (chars/sec) | RTF |
|--------|-------------------|-----|
| Supertonic 2 (RTX 4090) | 12,164 | 0.001 |
| Supertonic 2 (M4 Pro CPU) | 1,263 | 0.012 |
| ElevenLabs Flash v2.5 | 287 | 0.5 |
| Kokoro (Open-source) | 117 | 1.3 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-supertone-inc/supertonic-black?logo=github&style=flat)](https://github.com/supertone-inc/supertonic)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Supertone/supertonic--2-yellow?logo=huggingface&style=flat)](https://huggingface.co/Supertone/supertonic-2)
[![Demo](https://img.shields.io/badge/Demo-HF%20Spaces-blue&style=flat)](https://huggingface.co/spaces/Supertone/supertonic-2)

</details>

<details id="kugelaudio">
<summary>KugelAudio</summary>

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

</details>

<details id="kokoro-82m">
<summary>Kokoro-82M</summary>

### Kokoro-82M

**Description:** Kokoro is an open-weight Text-to-Speech model with 82 million parameters. Despite its lightweight architecture, it delivers comparable quality to larger models while being significantly faster and more cost-efficient. With Apache-licensed weights, Kokoro can be deployed anywhere from production environments to personal projects.

**Release Date:** January 27, 2025 (v1.0)

| Feature | Value |
|---------|-------|
| **Parameters** | 82M |
| **Architecture** | StyleTTS 2, ISTFTNet |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ (via misaki G2P) |
| **Emotion Control** | ✅ (voice styles) |
| **Languages** | 8 (54 voices) |
| **Streaming** | ✅ (generator pattern) |
| **Cost** | <$0.06 per hour of audio |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-hexgrad/kokoro-black?logo=github&style=flat)](https://github.com/hexgrad/kokoro)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-hexgrad/Kokoro--82M-yellow?logo=huggingface&style=flat)](https://huggingface.co/hexgrad/Kokoro-82M)
[![Demo](https://img.shields.io/badge/Demo-HF%20Spaces-blue&style=flat)](https://hf.co/spaces/hexgrad/Kokoro-TTS)

</details>

<details id="kokoclone">
<summary>KokoClone</summary>

### KokoClone

**Description:** KokoClone is a fast, real-time compatible multilingual voice cloning system built on top of Kokoro-ONNX. It enables users to type text in multiple languages, provide a short 3-10 second reference audio clip, and instantly generate speech in that same voice.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 82M (Base: Kokoro-ONNX) |
| **Zero-shot Voice Cloning** | ✅ (3-10s reference) |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ✅ |
| **Languages** | 7 (En, Hi, Fr, Ja, Zh, It, Pt, Es) |
| **Streaming** | ✅ (CPU real-time) |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-Ashish--Patnaik/kokoclone-black?logo=github&style=flat)](https://github.com/Ashish-Patnaik/kokoclone)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-PatnaikAshish/kokoclone-yellow?logo=huggingface&style=flat)](https://huggingface.co/PatnaikAshish/kokoclone)
[![Demo](https://img.shields.io/badge/Demo-HF%20Spaces-blue&style=flat)](https://huggingface.co/spaces/PatnaikAshish/kokoclone)

</details>

<details id="indextts2">
<summary>IndexTTS2</summary>

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

</details>

<details id="maya1">
<summary>Maya1</summary>

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

</details>

<details id="lfm2-audio-15b">
<summary>LFM2-Audio-1.5B</summary>

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

</details>

<details id="step-audio-editx">
<summary>Step-Audio-EditX</summary>

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

</details>

<details id="fireredtts2">
<summary>FireRedTTS2</summary>

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

</details>

<details id="voxcpm">
<summary>VoxCPM</summary>

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

</details>

<details id="luxtts">
<summary>LuxTTS</summary>

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

</details>

<details id="megatts3">
<summary>MegaTTS3</summary>

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

</details>

<details id="spark-tts">
<summary>Spark-TTS</summary>

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

</details>

<details id="fish-speech">
<summary>Fish Speech</summary>

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

</details>

<details id="step-audio">
<summary>Step-Audio</summary>

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

</details>

<details id="audio-flamingo-3">
<summary>Audio Flamingo 3 (AF3)</summary>

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

</details>

<details id="soulx-podcast">
<summary>SoulX-Podcast</summary>

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

</details>

<details id="chatterbox">
<summary>Chatterbox</summary>

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

</details>

<details id="orpheus-tts">
<summary>Orpheus-TTS</summary>

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

</details>

<details id="dia">
<summary>Dia</summary>

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

</details>

<details id="vieneu-tts">
<summary>VieNeu-TTS</summary>

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

</details>

<details id="mimo-audio">
<summary>MiMo-Audio</summary>

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

</details>

<details id="kimi-audio">
<summary>Kimi-Audio</summary>

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

</details>

<details id="zipvoice">
<summary>ZipVoice</summary>

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

</details>

---

## Music Generation Models

### Music Quick Comparison

| Model | Music Gen | Languages | Streaming | License |
| :--- | :---: | :--- | :---: | :--- |
| [ACE-Step 1.5](#ace-step-15) | ✅ | 50+ | ✅ | MIT |
| [LeVo 2](#levo-2) | ✅ | Zh/En | ❌ | Apache-2.0 |
| [Foundation-1](#foundation-1) | ✅ (Samples) | - | ❌ | Stability AI |
| [Music Flamingo](#music-flamingo) | ❌ | - | - | Apache-2.0 |
| [Magenta Realtime](#magenta-realtime) | ✅ | - | ✅ | Apache-2.0/CC-BY-4.0 |
| [Uni-MoE (Audio)](#uni-moe-audio) | ✅ | - | ✅ | Apache-2.0 |

<details id="ace-step-15">
<summary>ACE-Step 1.5</summary>

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

</details>

<details id="levo-2">
<summary>LeVo 2</summary>

### LeVo 2 (SongGeneration 2)

**Description:** Open-source foundation model for commercial-grade music generation by Tencent AI Lab. It outperforms open-source baselines and rivals commercial systems in Overall Quality, Melody, Arrangement, Sound Quality, and Structure.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Architecture** | Hybrid LLM-Diffusion |
| **Music Generation** | ✅ |
| **Lyrics Support** | ✅ (Chinese, English) |
| **Multilingual** | ✅ (Zh, En) |
| **Text/Audio Prompts** | ✅ |
| **VRAM** | 12GB-22GB |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-tencent--ailab/songgeneration-black?logo=github&style=flat)](https://github.com/tencent-ailab/songgeneration)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-tencent/SongGeneration-yellow?logo=huggingface&style=flat)](https://huggingface.co/tencent/SongGeneration)
[![Demo](https://img.shields.io/badge/Demo-HF%20Spaces-blue&style=flat)](https://huggingface.co/spaces/tencent/SongGeneration)

</details>

<details id="foundation-1">
<summary>Foundation-1</summary>

### Foundation-1

**Description:** Structured text-to-sample generation model for music production workflows. Generates tempo-synced, key-aware, bar-aware sample generation with support for instrument identity, timbre control, and FX processing.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Type** | Text-to-Sample (Music) |
| **Base Model** | stabilityai/stable-audio-open-1.0 |
| **Instrument Control** | ✅ |
| **Timbre Descriptors** | ✅ (Warm, Bright, etc.) |
| **FX Tags** | ✅ (Reverb, Delay, etc.) |
| **Musical Notation** | ✅ (Chord, Melody, Arp) |
| **VRAM** | ~8GB |
| **License** | Stability AI Community License |

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-RoyalCities/Foundation--1-yellow?logo=huggingface&style=flat)](https://huggingface.co/RoyalCities/Foundation-1)

</details>

<details id="music-flamingo">
<summary>Music Flamingo</summary>

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

</details>

<details id="magenta-realtime">
<summary>Magenta Realtime</summary>

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

</details>

<details id="soulx-singer-music">
<summary>SoulX-Singer</summary>

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

</details>

<details id="uni-moe-audio">
<summary>Uni-MoE (Audio)</summary>

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

</details>

---
| [voicetoinstrument.com](https://voicetoinstrument.com) | ✅ (Tracks) | Multi | ❌ | Proprietary |

## Anything to Audio

Models that can generate audio from multiple input modalities (video, text, image, audio). These are unified frameworks for multimodal audio synthesis.

### Anything to Audio Quick Comparison

| Model | Text | Video | Image | Audio | License |
| :--- | :---: | :---: | :---: | :---: | :--- |
| [PrismAudio](#prismaudio) | ❌ | ✅ | ❌ | ❌ | Apache-2.0 |
| [ThinkSound](#thinksound) | ✅ | ✅ | ❌ | ✅ | Apache-2.0 |
| [HunyuanVideo-Foley](#hunyuanvideo-foley) | ✅ | ✅ | ❌ | ❌ | Research Only |
| [MMAudio](#mmaudio) | ✅ | ✅ | ✅ | ❌ | Apache-2.0 |
| [AudioX](#audiox) | ✅ | ✅ | ✅ | ✅ | Apache-2.0 |
| [Uni-MoE (Audio)](#uni-moe-audio-any2audio) | ✅ | ✅ | ❌ | ✅ | Apache-2.0 |

<details id="audiox">
<summary>AudioX</summary>

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

</details>

<details id="mmaudio">
<summary>MMAudio</summary>

### MMAudio

**Description:** Multimodal joint training framework for high-quality synchronized audio generation from video and/or text inputs. State-of-the-art open source model for generating sounds for videos, images, and text prompts.

**Release Date:** December 2024 (CVPR 2025)

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Video-to-Audio** | ✅ |
| **Text-to-Audio** | ✅ |
| **Image-to-Audio** | ✅ |
| **Synchronized Audio** | ✅ |
| **Multimodal Joint Training** | ✅ |
| **License** | Apache-2.0 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-hkchengrex/MMAudio-black?logo=github&style=flat)](https://github.com/hkchengrex/MMAudio)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-hkchengrex/MMAudio-yellow?logo=huggingface&style=flat)](https://huggingface.co/hkchengrex/MMAudio)
[![Demo](https://img.shields.io/badge/Demo-HF%20Spaces-blue&style=flat)](https://huggingface.co/spaces/hkchengrex/MMAudio)
[![arXiv](https://img.shields.io/badge/arXiv-2412.15322-red&style=flat)](https://arxiv.org/abs/2412.15322)

</details>

<details id="hunyuanvideo-foley">
<summary>HunyuanVideo-Foley</summary>

### HunyuanVideo-Foley

**Description:** Tencent's end-to-end video sound effect generation model for professional-grade AI Foley sound generation. Analyzes footage and creates immersive audio that matches the visual content perfectly.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Video-to-Audio (Foley)** | ✅ |
| **Text-to-Audio** | ✅ |
| **High-Quality Foley** | ✅ |
| **Context-Aware** | ✅ |
| **Output Quality** | 48 kHz |
| **License** | Research & Non-commercial only |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-Tencent--Hunyuan/HunyuanVideo--Foley-black?logo=github&style=flat)](https://github.com/Tencent-Hunyuan/HunyuanVideo-Foley)
[![Demo](https://img.shields.io/badge/Demo-HF%20Spaces-blue&style=flat)](https://huggingface.co/spaces/tencent/HunyuanVideo-Foley)
[![Website](https://img.shields.io/badge/Website-hunyuanvideofoley.org-blue&style=flat)](https://www.hunyuanvideofoley.org/)
[![arXiv](https://img.shields.io/badge/arXiv-2508.16930-red&style=flat)](https://arxiv.org/abs/2508.16930)

</details>

<details id="thinksound">
<summary>ThinkSound</summary>

### ThinkSound

**Description:** Unified Any2Audio generation framework with flow matching guided by Chain-of-Thought (CoT) reasoning. Supports generating or editing audio from video, text, audio, or their combinations. Accepted to NeurIPS 2025.

**Release Date:** 2025

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Video-to-Audio** | ✅ (SOTA) |
| **Text-to-Audio** | ✅ |
| **Audio-to-Audio** | ✅ |
| **Audio Editing** | ✅ |
| **CoT-Driven Reasoning** | ✅ |
| **Interactive Object-centric Editing** | ✅ |
| **License** | Apache-2.0 (Research only) |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-FunAudioLLM/ThinkSound-black?logo=github&style=flat)](https://github.com/FunAudioLLM/ThinkSound)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-liuHuadai/ThinkSound-yellow?logo=huggingface&style=flat)](https://huggingface.co/liuHuadai/ThinkSound)
[![Demo](https://img.shields.io/badge/Demo-HF%20Spaces-blue&style=flat)](https://huggingface.co/spaces/FunAudioLLM/ThinkSound)

</details>

<details id="prismaudio">
<summary>PrismAudio</summary>

### PrismAudio

**Description:** Video-to-Audio generation framework with Reinforcement Learning and specialized Chain-of-Thought (CoT) planning. Decomposes reasoning into four specialized modules (Semantic, Temporal, Aesthetic, Spatial CoT) for comprehensive video understanding. Built upon ThinkSound.

**Release Date:** 2025 (ICLR 2026)

| Feature | Value |
|---------|-------|
| **Parameters** | 518M |
| **Video-to-Audio** | ✅ |
| **CoT Planning** | ✅ (4 modules) |
| **Multi-Dimensional RL** | ✅ |
| **Fast-GRPO** | ✅ (Hybrid ODE-SDE) |
| **Inference Time** | 0.63 seconds |
| **License** | Apache-2.0 |

**Performance Benchmarks:**

| Metric | VGGSound | AudioCanvas |
|--------|----------|-------------|
| Semantic (CLAP) | 0.47 | 0.52 |
| Temporal (DeSync↓) | 0.41 | 0.36 |
| Aesthetic (MOS-Q) | 4.21±0.35 | 4.12±0.28 |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-FunAudioLLM/ThinkSound-black?logo=github&style=flat)](https://github.com/FunAudioLLM/ThinkSound/tree/prismaudio)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FunAudioLLM/PrismAudio-yellow?logo=huggingface&style=flat)](https://huggingface.co/FunAudioLLM/PrismAudio)
[![Demo](https://img.shields.io/badge/Demo-HF%20Spaces-blue&style=flat)](https://huggingface.co/spaces/FunAudioLLM/PrismAudio)
[![arXiv](https://img.shields.io/badge/arXiv-2511.18833-red&style=flat)](https://arxiv.org/abs/2511.18833)

</details>

<details id="uni-moe-audio-any2audio">
<summary>Uni-MoE (Audio)</summary>

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

</details>

---

## Audio Restoration & Enhancement

### Audio Restoration & Enhancement Quick Comparison

| Model | Type | Bandwidth Extension | Inpainting | License |
| :--- | :---: | :---: | :---: | :--- |
| [NVIDIA A2SB](#nvidia-a2sb) | Restoration | ✅ | ✅ | NVIDIA Non-Commercial |
| [NovaSR](#novasr) | Enhancement | ✅ | ❌ | Apache-2.0 |
| [AudioSR](#audiosr) | Enhancement | ✅ | ❌ | MIT |

<details id="nvidia-a2sb">
<summary>NVIDIA A2SB</summary>

### NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)

**Description:** Diffusion-based audio restoration model tailored for high-resolution music at 44.1kHz. An end-to-end, vocoder-free, multi-task model capable of both bandwidth extension (predicting high-frequency components) and inpainting (re-generating missing segments). Can restore hour-long audio inputs without boundary artifacts.

**Release Date:** January 2025

| Feature | Value |
|---------|-------|
| **Architecture** | End-to-end vocoder-free |
| **Bandwidth Extension** | ✅ |
| **Audio Inpainting** | ✅ |
| **High-Resolution** | ✅ (44.1kHz) |
| **Long Audio** | ✅ (hour-long) |
| **Streaming** | ❌ |
| **License** | NVIDIA OneWay NonCommercial License |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-NVIDIA/diffusion--audio--restoration-black?logo=github&style=flat)](https://github.com/NVIDIA/diffusion-audio-restoration)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-nvidia/audio__to__audio__schrodinger__bridge-yellow?logo=huggingface&style=flat)](https://huggingface.co/nvidia/audio_to_audio_schrodinger_bridge)
[![arXiv](https://img.shields.io/badge/arXiv-2501.11311-red&style=flat)](https://arxiv.org/abs/2501.11311)

</details>

<details id="novasr">
<summary>NovaSR</summary>

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

</details>

<details id="audiosr">
<summary>AudioSR</summary>

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

</details>

---

## Speech Recognition (ASR)

### ASR Quick Comparison

| Model | Languages | Streaming | License |
| :--- | :--- | :---: | :--- |
| [VibeVoice-ASR](#vibevoice-asr) | 50+ | ✅ | MIT |
| [FunASR](#funasr) | 50+ | ✅ | MIT |

<details id="vibevoice-asr">
<summary>VibeVoice-ASR</summary>

### VibeVoice-ASR

**Description:** Microsoft's unified speech-to-text model for 60-minute long-form audio processing with speaker diarization and timestamping.

**Release Date:** January 21, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **ASR** | ✅ |
| **Languages** | 50+ |
| **Streaming** | ✅ |
| **License** | MIT |

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-microsoft/VibeVoice-black?logo=github&style=flat)](https://github.com/microsoft/VibeVoice)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-microsoft/VibeVoice--ASR-yellow?logo=huggingface&style=flat)](https://huggingface.co/microsoft/VibeVoice-ASR)

</details>

<details id="funasr">
<summary>FunASR</summary>

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

</details>

---

## Additional Resources

### ComfyUI Integrations

### ASR Leaderboard

| Resource | Description |
|---------|-------------|
| **Open ASR Leaderboard** | Hugging Face leaderboard for comparing ASR model performance across languages and metrics. |

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Open%20ASR%20Leaderboard-yellow?logo=huggingface&style=flat)](https://huggingface.co/spaces/hf-audio/open_asr_leaderboard)

---

## Legend

**Symbols:** ✅ = Supported | ❌ = Not Supported | - = N/A

**Languages:** En = English | Zh = Chinese | Jp = Japanese | Ko = Korean | Vi = Vietnamese | EU = European | Canto = Cantonese

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
