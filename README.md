# Awesome TTS & Voice Generation Models

A curated list of open-source Text-to-Speech (TTS), voice cloning, and music generation models. Models are sorted by release date (newest first).

![logo-tts2](https://github.com/user-attachments/assets/132b105b-b894-4150-bace-e84ef70ed2be)

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
| [LongCat-AudioDiT](#longcat-audiodit) | ✅ | ❌ | Zh/En | ❌ | MIT |
| [VoxCPM2](#voxcpm2) | ✅ | ❌ | 30 | ✅ | Apache-2.0 |
| [MOSS-TTS-Nano](#moss-tts-nano) | ✅ | ❌ | 20 | ✅ | Apache-2.0 |
| [T5Gemma-TTS](#t5gemma-tts) | ✅ | ❌ | En/Zh/Jp | ❌ | MIT |
| [TinyTTS](#tinytts) | ❌ | ❌ | En | ✅ | Apache-2.0 |
| [LEMAS-TTS](#lemas-tts) | ✅ | ❌ | 10 | ❌ | Apache-2.0 |
| [OmniVoice](#omnivoice) | ✅ | ❌ | 600+ | ❌ | Apache-2.0 |
| [LongCat-Next](#longcat-next) | ✅ | ✅ | Zh/En | ✅ | MIT |
| [Voxtral-4B-TTS](#voxtral-4b-tts) | ✅ | ❌ | 9 | ✅ | CC BY-NC 4.0 |
| [Irodori-TTS-500M-v2](#irodori-tts-500m-v2) | ✅ | ❌ | Jp | ❌ | MIT |
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

<details id="longcat-audiodit">
<summary>LongCat-AudioDiT</summary>

### LongCat-AudioDiT

**Description:** State-of-the-art diffusion-based TTS model operating directly in waveform latent space. Developed by Meituan's LongCat team, it requires only a Waveform VAE and Diffusion backbone, effectively mitigating compounding errors.

**Release Date:** March 30, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 1B / 3.5B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | Chinese, English |
| **Streaming** | ❌ |
| **Sample Rate** | 24000 Hz |
| **License** | MIT |

**Key Innovation:** Adaptive Projection Guidance (APG) replaces traditional classifier-free guidance for elevated generation quality. Outperforms Seed-TTS on zero-shot voice cloning benchmarks.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-meituan--longcat/LongCat--AudioDiT-black?logo=github&style=flat)](https://github.com/meituan-longcat/LongCat-AudioDiT)
[![Hugging Face 1B](https://img.shields.io/badge/Hugging%20Face-1B-yellow?logo=huggingface&style=flat)](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-1B)
[![Hugging Face 3.5B](https://img.shields.io/badge/Hugging%20Face-3.5B-yellow?logo=huggingface&style=flat)](https://huggingface.co/meituan-longcat/LongCat-AudioDiT-3.5B)

</details>

<details id="voxcpm2">
<summary>VoxCPM2</summary>

### VoxCPM2

**Description:** OpenBMB's next-generation tokenizer-free diffusion autoregressive TTS model with 2 billion parameters. Supports 30 languages with automatic detection, voice design from text descriptions, and high-fidelity voice cloning.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ (Voice Design) |
| **Languages** | 30 (+ 9 Chinese dialects) |
| **Streaming** | ✅ (RTF ~0.3) |
| **Audio Output** | 48 kHz |
| **License** | Apache-2.0 |

**Key Innovation:** Tokenizer-free design with LocEnc → TSLM → RALM → LocDiT pipeline. Built-in super-resolution via AudioVAE V2 for 48kHz output.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-OpenBMB/VoxCPM-black?logo=github&style=flat)](https://github.com/OpenBMB/VoxCPM)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-openbmb/VoxCPM2-yellow?logo=huggingface&style=flat)](https://huggingface.co/openbmb/VoxCPM2)
[![Demo](https://img.shields.io/badge/Demo-Space-blue?logo=open&style=flat)](https://huggingface.co/spaces/OpenBMB/VoxCPM-Demo)

</details>

<details id="moss-tts-nano">
<summary>MOSS-TTS-Nano</summary>

### MOSS-TTS-Nano

**Description:** Ultra-lightweight open-source multilingual speech generation model with only 0.1B parameters. Designed for realtime speech generation that runs directly on CPU without GPU.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 0.1B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ❌ |
| **Languages** | 20 |
| **Streaming** | ✅ (CPU-friendly) |
| **Audio Output** | 48 kHz Stereo |
| **License** | Apache-2.0 |

**Key Innovation:** Pure autoregressive architecture with MOSS-Audio-Tokenizer-Nano. Compresses audio to 12.5 Hz token stream using RVQ with 16 codebooks. Runs on 4-core CPU.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-OpenMOSS/MOSS--TTS--Nano-black?logo=github&style=flat)](https://github.com/OpenMOSS/MOSS-TTS-Nano)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-OpenMOSS--Team/MOSS--TTS--Nano--100M-yellow?logo=huggingface&style=flat)](https://huggingface.co/OpenMOSS-Team/MOSS-TTS-Nano-100M)
[![Demo](https://img.shields.io/badge/Demo-Space-blue?logo=open&style=flat)](https://huggingface.co/spaces/OpenMOSS-Team/MOSS-TTS-Nano)

</details>

<details id="t5gemma-tts">
<summary>T5Gemma-TTS</summary>

### T5Gemma-TTS

**Description:** Multilingual TTS model with voice cloning and duration control, built on the T5Gemma encoder-decoder LLM architecture. Supports batch generation for multiple audio variations.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2B-2B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ❌ |
| **Languages** | English, Chinese, Japanese |
| **Streaming** | ❌ |
| **VRAM** | 7.6-10.6 GB |
| **License** | MIT |

**Key Innovation:** PM-RoPE positional encoding with XCodec2 audio codec. Low-VRAM options with CPU offloading. Batch inference efficiency with single encoder pass.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-Aratako/T5Gemma--TTS-black?logo=github&style=flat)](https://github.com/Aratako/T5Gemma-TTS)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Aratako/T5Gemma--TTS--2b--2b-yellow?logo=huggingface&style=flat)](https://huggingface.co/Aratako/T5Gemma-TTS-2b-2b)
[![Demo](https://img.shields.io/badge/Demo-Space-blue?logo=open&style=flat)](https://huggingface.co/spaces/Aratako/T5Gemma-TTS-Demo)

</details>

<details id="tinytts">
<summary>TinyTTS</summary>

### TinyTTS

**Description:** The smallest English TTS model with only 1.6 million parameters. End-to-end neural network achieving ~53x real-time synthesis speed on CPU via ONNX optimization.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 1.6M |
| **Zero-shot Voice Cloning** | ❌ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ❌ |
| **Languages** | English |
| **Streaming** | ✅ (~53x RTF) |
| **Model Size** | ~3.4 MB (ONNX FP16) |
| **License** | Apache-2.0 |

**Key Innovation:** Ultra-compact architecture optimized for CPU-only deployment. Multi-platform support via Python and Node.js APIs. Works on laptops, edge devices, and embedded systems.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-tronghieuit/tiny--tts-black?logo=github&style=flat)](https://github.com/tronghieuit/tiny-tts)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-backtracking/tiny--tts-yellow?logo=huggingface&style=flat)](https://huggingface.co/backtracking/tiny-tts)
[![Demo](https://img.shields.io/badge/Demo-Space-blue?logo=open&style=flat)](https://huggingface.co/spaces/backtracking/tiny-tts-demo)

</details>

<details id="lemas-tts">
<summary>LEMAS-TTS</summary>

### LEMAS-TTS

**Description:** Part of the LEMAS (Large-scale Extensible Multilingual Audio Suite) project. Zero-shot multilingual TTS with 0.3B parameters supporting 10 languages with word-level precise editing capabilities.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 0.3B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | 10 (zh/en/de/fr/es/pt/it/ru/id/vi) |
| **Streaming** | ❌ |
| **Special Feature** | Word-level editing (LEMAS-Edit) |
| **License** | Apache-2.0 |

**Key Innovation:** Built on 150,000+ hours of multilingual speech data with word-level timestamps. Includes LEMAS-Edit for precise word-level speech editing via masked token infilling.

**Links:**
[![Website](https://img.shields.io/badge/Website-LEMAS%20Project-blue&style=flat)](https://lemas-project.github.io/LEMAS-Project/)
[![Hugging Face TTS](https://img.shields.io/badge/Hugging%20Face-LEMAS--Project/LEMAS--TTS-yellow?logo=huggingface&style=flat)](https://huggingface.co/LEMAS-Project/LEMAS-TTS)
[![Hugging Face Edit](https://img.shields.io/badge/Hugging%20Face-LEMAS--Project/LEMAS--Edit-yellow?logo=huggingface&style=flat)](https://huggingface.co/LEMAS-Project/LEMAS-Edit)

</details>

<details id="omnivoice">
<summary>OmniVoice</summary>

### OmniVoice

**Description:** Massive multilingual zero-shot TTS model scaling to 600+ languages. Uses diffusion language model-style discrete non-autoregressive architecture with single-stage text-to-acoustic mapping.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ✅ (Pinyin/CMU) |
| **Emotion Control** | ✅ (Voice Design) |
| **Languages** | 600+ |
| **Streaming** | ❌ |
| **Training Data** | 581k hours |
| **License** | Apache-2.0 |

**Key Innovation:** Simplified single-stage architecture vs conventional two-stage pipelines. Full-codebook random masking strategy with LLM initialization for superior intelligibility. Noise-robust prompt processing.

**Links:**
[![Website](https://img.shields.io/badge/Website-OmniVoice-blue&style=flat)](https://zhu-han.github.io/omnivoice/)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-k2--fsa/OmniVoice-yellow?logo=huggingface&style=flat)](https://huggingface.co/k2-fsa/OmniVoice)

</details>

<details id="longcat-next">
<summary>LongCat-Next</summary>

### LongCat-Next

**Description:** Native multimodal foundation model by Meituan LongCat Team processing text, vision, and audio under a single autoregressive objective. Industrial-strength model with strong speech synthesis and voice cloning.

**Release Date:** March 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 3B (MoE A3B) |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ✅ |
| **Pronunciation Control** | ✅ |
| **Emotion Control** | ✅ |
| **Languages** | Chinese, English |
| **Streaming** | ✅ (Low latency) |
| **Audio Output** | 24 kHz |
| **License** | MIT |

**Key Innovation:** Discrete Native Autoregression Paradigm (DiNA) unifying modalities in shared discrete token space. Combines visual understanding, generation, and audio processing in single model.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-meituan-longcat/LongCat--Next-black?logo=github&style=flat)](https://github.com/meituan-longcat/LongCat-Next)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-meituan-longcat/LongCat--Next-yellow?logo=huggingface&style=flat)](https://huggingface.co/meituan-longcat/LongCat-Next)

</details>

<details id="voxtral-4b-tts">
<summary>Voxtral-4B-TTS</summary>

### Voxtral-4B-TTS

**Description:** Frontier, open-weights text-to-speech model developed by Mistral AI. Designed to be fast, instantly adaptable, and produces lifelike speech with natural prosody and emotional range.

**Release Date:** March 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 4B |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ✅ (expressive speech) |
| **Languages** | 9 (En, Fr, Es, De, It, Pt, Nl, Ar, Hi) |
| **Streaming** | ✅ (RTF 0.103 at concurrency 1) |
| **Audio Output** | 24 kHz |
| **License** | CC BY-NC 4.0 |

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Voxtral--4B--TTS--2603-yellow?logo=huggingface&style=flat)](https://huggingface.co/mistralai/Voxtral-4B-TTS-2603)
[![Demo](https://img.shields.io/badge/Demo-Mistral%20AI%20Studio-blue?logo=steam&style=flat&cc=wildminder)](https://console.mistral.ai/build/audio/text-to-speech)
[![Blog](https://img.shields.io/badge/Blog-Mistral%20AI-red?logo=blogger&style=flat)](https://mistral.ai/news/voxtral-tts)

</details>

<details id="irodori-tts-500m-v2">
<summary>Irodori-TTS-500M-v2</summary>

### Irodori-TTS-500M-v2

**Description:** Japanese Text-to-Speech model based on Rectified Flow Diffusion Transformer. Features emoji-based style and sound effect control by embedding emojis in input text for expressive speech generation.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 500M |
| **Zero-shot Voice Cloning** | ✅ |
| **ASR** | ❌ |
| **Pronunciation Control** | ❌ |
| **Emotion Control** | ✅ (emoji-based) |
| **Languages** | Japanese |
| **Streaming** | ❌ |
| **Output Quality** | 48kHz waveform |
| **License** | MIT |

**Key Feature:** Emoji annotation control - insert specific emojis into text to control speaking styles, emotions, and sound effects.

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Irodori--TTS--500M--v2-yellow?logo=huggingface&style=flat&cc=wildminder)](https://huggingface.co/Aratako/Irodori-TTS-500M-v2)
[![GitHub](https://img.shields.io/badge/GitHub-Aratako/Irodori--TTS-black?logo=github&style=flat)](https://github.com/Aratako/Irodori-TTS)
[![Demo](https://img.shields.io/badge/Demo-Space-blue?logo=open&style=flat)](https://huggingface.co/spaces/Aratako/Irodori-TTS-500M-v2-Demo)

</details>

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
<summary>Audio Flamingo 3 (AF3) / Audio Flamingo Next</summary>

### Audio Flamingo 3 (AF3) / Audio Flamingo Next

**Description:** NVIDIA ADLR's fully open-source Large Audio Language Model with state-of-the-art audio understanding. Audio Flamingo Next (AF-Next) is the latest generation featuring stronger general audio understanding, longer context support, and timestamp-grounded reasoning.

**Release Date:** July 2025 (AF3), 2026 (AF-Next)

| Feature | Value |
|---------|-------|
| **Parameters** | 7B |
| **Zero-shot Voice Cloning** | ❌ |
| **ASR** | ✅ |
| **Pronunciation Control** | N/A |
| **Emotion Control** | ✅ |
| **Languages** | Multi-lingual |
| **Streaming** | ✅ |
| **Context** | Up to 30 minutes |
| **License** | Apache-2.0 |

**Key Innovation (AF-Next):** Staged curriculum training with GRPO-based RL post-training. Three specialized checkpoints: Instruct, Think (reasoning), and Captioner. Temporal Audio Chain-of-Thought grounding intermediate reasoning to timestamps.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-NVIDIA/audio--flamingo-black?logo=github&style=flat)](https://github.com/NVIDIA/audio-flamingo)
[![Hugging Face AF3](https://img.shields.io/badge/Hugging%20Face-nvidia/audio--flamingo--3-yellow?logo=huggingface&style=flat)](https://huggingface.co/nvidia/audio-flamingo-3)
[![Website AF-Next](https://img.shields.io/badge/Website-AF--Next-blue&style=flat)](https://afnext-umd-nvidia.github.io/)

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

## Anything to Audio

Models that can generate audio from multiple input modalities (video, text, image, audio). These are unified frameworks for multimodal audio synthesis.

### Anything to Audio Quick Comparison

| Model | Text | Video | Image | Audio | License |
| :--- | :---: | :---: | :---: | :---: | :--- |
| [Woosh](#woosh) | ✅ | ✅ | ❌ | ✅ | Apache-2.0 |
| [PrismAudio](#prismaudio) | ❌ | ✅ | ❌ | ❌ | Apache-2.0 |
| [ThinkSound](#thinksound) | ✅ | ✅ | ❌ | ✅ | Apache-2.0 |
| [HunyuanVideo-Foley](#hunyuanvideo-foley) | ✅ | ✅ | ❌ | ❌ | Research Only |
| [MMAudio](#mmaudio) | ✅ | ✅ | ✅ | ❌ | Apache-2.0 |
| [AudioX](#audiox) | ✅ | ✅ | ✅ | ✅ | Apache-2.0 |
| [Uni-MoE (Audio)](#uni-moe-audio-any2audio) | ✅ | ✅ | ❌ | ✅ | Apache-2.0 |

<details id="audiox">
<summary>AudioX / Audio-Omni</summary>

### AudioX / Audio-Omni

**Description:** Audio-Omni is the first end-to-end framework unifying understanding, generation, and editing across general sound, music, and speech domains. Presented at SIGGRAPH 2026. AudioX is a unified framework integrating text, video, image, and audio conditions.

**Release Date:** March 2025 (AudioX), 2026 (Audio-Omni)

| Feature | Value |
|---------|-------|
| **Parameters** | - |
| **Text-to-Audio** | ✅ |
| **Text-to-Music** | ✅ |
| **Text-to-Speech** | ✅ |
| **Video-to-Audio/Music** | ✅ |
| **Audio Editing** | ✅ (Add/Remove/Extract/Style) |
| **Voice Conversion** | ✅ |
| **License** | Apache-2.0 / CC-BY-NC-4.0 |

**Key Innovation:** First unified framework covering all three audio domains. Combines frozen multimodal LLM (Qwen2.5-Omni) with trainable Diffusion Transformer for high-fidelity synthesis. Any-to-any audio processing.

**Links:**
[![GitHub AudioX](https://img.shields.io/badge/GitHub-ZeyueT/AudioX-black?logo=github&style=flat)](https://github.com/ZeyueT/AudioX)
[![GitHub Audio-Omni](https://img.shields.io/badge/GitHub-Audio--Omni-black?logo=github&style=flat)](https://github.com/ZeyueT/Audio-Omni)
[![Hugging Face AudioX](https://img.shields.io/badge/Hugging%20Face-HKUSTAudio/audiox-yellow?logo=huggingface&style=flat)](https://huggingface.co/collections/HKUSTAudio/audiox)
[![Hugging Face Audio-Omni](https://img.shields.io/badge/Hugging%20Face-HKUSTAudio/Audio--Omni-yellow?logo=huggingface&style=flat)](https://huggingface.co/HKUSTAudio/Audio-Omni)
[![arXiv AudioX](https://img.shields.io/badge/arXiv-2503.10522-red&style=flat)](https://arxiv.org/abs/2503.10522)

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

<details id="woosh">
<summary>Woosh</summary>

### Woosh

**Description:** Sony AI's sound effect foundation model for text-to-audio and video-to-audio generation. Includes Woosh-AE (audio encoder/decoder), Woosh-Flow/DFlow (T2A), and Woosh-VFlow/DVFlow (V2A) with distilled fast inference variants.

**Release Date:** 2026

| Feature | Value |
|---------|-------|
| **Text-to-Audio** | ✅ |
| **Video-to-Audio** | ✅ |
| **Audio Encoding** | ✅ |
| **Fast Inference** | ✅ (Distilled models) |
| **Architecture** | Flow-based generative models |
| **License** | Apache-2.0 |

**Key Innovation:** Optimized for sound effects (not general audio) with both public and private model versions. Video-conditioned generation without requiring captions. Competitive with Stable Audio Open and TangoFlux.

**Links:**
[![GitHub](https://img.shields.io/badge/GitHub-SonyResearch/Woosh--SFX-black?logo=github&style=flat)](https://github.com/SonyResearch/Woosh-SFX)
[![arXiv](https://img.shields.io/badge/arXiv-2604.01929-red&style=flat)](https://arxiv.org/abs/2604.01929)

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
| [Cohere Transcribe](#cohere-transcribe) | 14 | ✅ | Apache-2.0 |
| [VibeVoice-ASR](#vibevoice-asr) | 50+ | ✅ | MIT |
| [FunASR](#funasr) | 50+ | ✅ | MIT |

<details id="cohere-transcribe">
<summary>Cohere Transcribe</summary>

### Cohere Transcribe

**Description:** Open-source automatic speech recognition (ASR) model developed by Cohere. A 2 billion parameter dedicated audio-in, text-out model that ranks #1 on the English ASR leaderboard.

**Release Date:** March 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2B |
| **Architecture** | Conformer-based encoder-decoder |
| **ASR** | ✅ |
| **Languages** | 14 (En, Fr, De, It, Es, Pt, Gr, Nl, Pl, Zh, Jp, Ko, Vi, Ar) |
| **Streaming** | ✅ |
| **RTFx** | Up to 3x faster than comparable models |
| **License** | Apache-2.0 |

**Key Features:**
- Long-form transcription with automatic chunking (>35 seconds)
- Optional punctuation control
- Batched inference support
- vLLM integration for production serving
- Apple Silicon support via mlx-audio
- WebGPU browser deployment via transformers.js

**Links:**
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Cohere--Transcribe-yellow?logo=huggingface&cc=wildminder&style=flat)](https://huggingface.co/CohereLabs/cohere-transcribe-03-2026)
[![Demo](https://img.shields.io/badge/Demo-Space-blue?logo=open&style=flat)](https://huggingface.co/spaces/CohereLabs/cohere-transcribe-03-2026)
[![Blog](https://img.shields.io/badge/Blog-Cohere-blue?logo=blogger&style=flat)](https://cohere.com/blog/transcribe)

</details>

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
## Agent Identity & Trust

- [TWZRD Agent Intel](https://intel.twzrd.xyz) - Trust scoring MCP for AI agents on Solana. Verify agent wallet identity and autonomy score before authorizing x402 micropayments in voice AI pipelines. Free MCP: `{"mcpServers":{"twzrd-agent-intel":{"url":"https://intel.twzrd.xyz/mcp"}}}`


### ComfyUI Integrations

### Leaderboard

| Resource | Description | Link |
|---------|-------------| :--: |
| **Open ASR Leaderboard** | Hugging Face leaderboard for comparing ASR model performance across languages and metrics. | [![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Open%20ASR%20Leaderboard-yellow?logo=huggingface&style=flat)](https://huggingface.co/spaces/hf-audio/open_asr_leaderboard) |

---

## Contributing

This list is continuously evolving. If you have any models to add or updates to suggest, please feel free to contribute!

---

*Last Updated: March 2026*
