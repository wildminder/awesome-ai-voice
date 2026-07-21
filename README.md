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
| [Scylla's Band](#scyllasband) | ❌ | ❌ | en_us, en_gb, es, it | ✅ | ![Apache 2.0][license-apache-2.0] |
| [sanoTTS](#sanotts) | ❌ | ❌ | English, Nepali, Hindi, Vietnamese, Indonesian, Chinese | ❌ | ![Unknown][license-unknown] |
| [FreyaTTS](#freyatts) | ❌ | ❌ | Turkish | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Gepard](#gepard) | ✅ | ❌ | English, Spanish, Portuguese, Dutch | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Higgs Audio v3 TTS](#higgs-audio-v3-tts) | ✅ | ❌ | 102 | ✅ | ![Research Only][license-research-only] |
| [dots.tts](#dots-tts) | ✅ | ❌ | Multilingual | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Confucius4-TTS](#confucius4-tts) | ✅ | ❌ | 14 | ❌ | ![Apache 2.0][license-apache-2.0] |
| [WavTTS](#wavtts) | ✅ | ❌ | English, Chinese | ❌ | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [MOSS-TTS](#moss-tts) | ✅ | ❌ | 31 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [VoxFlash-TTS](#voxflash-tts) | ✅ | ❌ | Chinese, English | ❌ | ![Apache 2.0][license-apache-2.0] |
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
| [Soprano](#soprano) | ❌ | ❌ | English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [GLM-TTS](#glm-tts) | ✅ | ❌ | Chinese, English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Echo-TTS](#echo-tts) | ✅ | ❌ | English | ❌ | ![MIT][license-mit] |
| [VibeVoice-Realtime](#vibevoice-realtime) | ✅ | ❌ | Multilingual | ✅ | ![MIT][license-mit] |
| [Fun-CosyVoice 3.0](#fun-cosyvoice-30) | ✅ | ❌ | 9 + 18+ Chinese dialects | ✅ | ![Apache 2.0][license-apache-2.0] |
| [LFM2-Audio-1.5B](#lfm2-audio-15b) | ✅ | ✅ | English | ✅ | ![LFM][license-lfm] |
| [Marvis-TTS](#marvis-tts) | ✅ | ❌ | English, French, German | ✅ | ![Apache 2.0][license-apache-2.0] |
| [IndexTTS2](#indextts2) | ✅ | ❌ | Chinese, English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Maya1](#maya1) | ✅ | ❌ | English | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Step-Audio-EditX](#step-audio-editx) | ✅ | ❌ | Mandarin, English, Sichuanese, Cantonese, Japanese, Korean | ✅ | ![Apache 2.0][license-apache-2.0] |
| [KaniTTS](#kani-tts) | ❌ | ❌ | English, German, Chinese, Korean, Arabic, Spanish | ✅ | ![LFM][license-lfm] |
| [VibeVoice-Finetuning](#vibevoice-finetuning) | ❌ | ❌ | — | ❌ | ![MIT][license-mit] |
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
| [eSpeak-NG](#espeak-ng) | ❌ | ❌ | 100+ | ✅ | ![Unknown][license-unknown] |

<!-- MODEL:scyllasband.md -->
<details id="scyllasband">
<summary>Scylla's Band</summary>

### Scylla's Band

**Description:** **Scylla's Band** is a multilingual, multi-voice, **expressive** TTS model from Spybyscript, designed specifically for **local and self-hosted inference** through ONNX Runtime (with an experimental LiteRT backend for explicit native / mobile use). The architecture is a continuous-latent TTS family:

**Release Date:** July 19, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | not stated (architecture: 4-layer duration predictor (192 hidden) + 12-layer rectified-flow acoustic generator (512 hidden, AdaLN, QK norm)) |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Languages** | en_us, en_gb, es, it (4 public text-input languages) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Sample Rate** | 24,000 Hz |
| **Managed Voices** | 10 (ariadne, felix, gwen, ink, max, orpheus, rex, scylla, stone, tuesday) |
| **Voice Default Locale** | en_us for most; ink / orpheus / tuesday default to en_gb |
| **Voice Style Dim** | 128 (style features) + 32 (prosody features) |
| **Affect Axes** | 6 (calm, joy, anger, sadness, sarcasm, questioning — all continuous in `[0, 1]`) |
| **Affect Overlay Axes** | sarcasm, questioning (mixable with any core delivery) |
| **Affect Cfg Scope** | duration + acoustic-flow prediction (preserves voice / reference) |
| **Encoders Default** | ONNX Runtime (Python CLI / Python API / Android sample / `libscyllasband` native) |
| **Encoders Experimental** | LiteRT (experimental / explicit-selection) |
| **Cli Quality Default** | 8-step Heun sampling |
| **Graph Budgets** | 512 G2P text tokens / 512 phone frames / 640 latent frames |
| **Latent Target Buckets** | 256 / 384 / 512 / 640 (smallest-fit selection) |
| **Vocoder** | Scylla's Band acoustic adapter + frozen `charactr/vocos-mel-24khz` |
| **Hop Lengths** | 256 (waveform) / 512 (latent) |
| **Text Frontend** | phrase-level multilingual G2P (74-phone vocabulary) |
| **Span Context** | 3 segments over up to 768 phones with 512-dim context state |
| **Prefix Context** | up to 24 acoustic latent frames from preceding chunk |
| **Long Form Features** | boundary metadata + punctuation pause floors + prefix-latent carryover + span context |
| **Group Speak Input** | `[voice]`, `[voice:language]`, `[voice:language:axis=value,...]` annotations |
| **Bundle Contract** | 1.0.0 / `scyllasband-duration-flow` |
| **Intended Use** | single-voice speech synthesis (10 voices); en/es/it; long-form narration; multi-voice dialogue from tagged text; continuous affect control; ONNX desktop/server; ONNX + LiteRT native/mobile |
| **Not Intended** | arbitrary-speaker cloning / impersonation / fraud / deceptive speech |
| **Distributions** | training data, trainer checkpoints, and export tooling not distributed |
| **Cli Commands** | download, validate-bundle, list-voices, normalize-text, speak, group-speak, stream, plan |
| **Library Name** | onnxruntime (tags include onnx, tflite, litert, duration-flow) |

**Features:** Three design decisions distinguish Scylla's Band in the multilingual
TTS class. First, **decoupling duration and acoustic flow as
separate rectified-flow stages** — duration is a 192-hidden, 4-layer
predictor operating on a 512-phone window, acoustic latents a
512-hidden, 12-layer AdaLN / QK-norm generator at 24-dim. This split
lets affect-CFG act on **both** stages independently while retaining
voice / reference conditioning, supporting the 6-axis continuous
composability. Second, **6 affect axes** (with `sarcasm` and
`questioning` as overlays mixed with any core delivery) instead of
mutually-exclusive discrete emotion classes — `calm=0.5, joy=0.5` is
a valid input, and axes stay in `[0, 1]` so multi-axis states are
expressible without combinatorial blow-up. Third, the **ONNX-first
runtime** design with `libscyllasband` native + an experimental
LiteRT backend sits at a budget most neural TTS systems don't
target — the 8-step Heun default and 512/512/640 fixed graph budget
keep the model usable on CPU and mobile, and the inference-only
release surface (training data + checkpoints not distributed) is the
complement of the latency / mobile inference focus.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/spybyscript/scyllasband)
[![GitHub][link-github]](https://github.com/lowkeytea/scyllasband)
[![Website][link-website]](https://lowkeytea.github.io/scyllasband/)

</details>
<!-- /MODEL:scyllasband.md -->
<!-- MODEL:sanotts.md -->
<details id="sanotts">
<summary>sanoTTS</summary>

### sanoTTS

**Description:** **sanoTTS** is the smallest known neural text-to-speech family. The name *sano* (सानो) is Nepali for **"small"**. Each voice weighs **745k to 1.8M parameters** — smaller than the smallest voice in prior families (TinyTTS at 1.62M; Inflect Nano at 4.63M; Kokoro at 82M) and the family fits in **under 4 MB per voice** with zero runtime dependencies (the espeak-ng phonemizer is bundled). Voices run **real-time on a ~$3 ESP32-S3 microcontroller** (output through a GPIO into an LM386 and a speaker) and **live in the browser via WebAssembly** — no server, no upload, no NPU. The full neural stack is **duration → acoustic → decoder**, quantized to int8, with the espeak-ng phonemizer included. **9 voices** across **6 languages** ship: English (4 voices — including a 745k on-device "robot" voice), Nepali, Hindi, Vietnamese, Indonesian, and Chinese. The project page at [ampixa.github.io/sanoTTS](https://ampixa.github.io/sanoTTS/) hosts a live browser synthesis demo for every voice.

**Release Date:** July 13, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 745k–1.8M per voice (smallest = the 745k on-device "robot" voice) |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Languages** | English, Nepali, Hindi, Vietnamese, Indonesian, Chinese (6 languages, 9 voices) |
| **Streaming** | ❌ |
| **License** | ![Unknown][license-unknown] |
| **Architecture** | full neural stack — duration model → acoustic model → decoder |
| **Quantization** | int8 |
| **Runtime Microcontroller** | ESP32-S3 (real-time, GPIO → LM386 → speaker) |
| **Runtime Browser** | WebAssembly (no server, no upload, no NPU) |
| **Runtime Footprint** | under 4 MB per voice, zero dependencies |
| **Voices** | 9 (English: amy / kristin / hfc / amy-small / robot; one voice each for NE / HI / VI / ID / ZH) |
| **Phonemizer** | espeak-ng (bundled) |
| **Library Name** | sanotts |
| **Training Method** | distillation (per voice) |

**Features:** The hard constraint — be the smallest neural TTS family known,
real-time on a $3 microcontroller — drives the entire stack.
Conventional sub-100M TTS systems are too large for an ESP32's flash
and RAM. sanoTTS keeps the full **duration → acoustic → decoder**
neural pipeline (no espeak-NG-only fallback, no concatenative
hybrid), quantizes everything to int8, and *bundles the phonemizer*
so the whole voice ships in under 4 MB with zero runtime dependencies.
The result is a per-voice footprint 100× smaller than Kokoro and
2× smaller than TinyTTS while still scoring competitively on the
authors' SCOREQ / UTMOS / DNSMOS-SIG no-reference 24-sentence harness
— and the demo synthesizes every voice **live in the browser via
WASM**, so the smallest-known neural TTS is also the only one that
runs unattended on a $3 chip and a $0 web page.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/ampixa/sanoTTS)
[![GitHub][link-github]](https://github.com/Ampixa/sanoTTS)
[![Website][link-website]](https://ampixa.github.io/sanoTTS/)

</details>
<!-- /MODEL:sanotts.md -->
<!-- MODEL:freyatts.md -->
<details id="freyatts">
<summary>FreyaTTS</summary>

### FreyaTTS

**Description:** **FreyaTTS** is a 183M-parameter Turkish text-to-speech model. It is **tokenizer-free at the character level** — 92 symbols in its Turkish vocabulary — so there is no phonemizer or G2P step in either training or inference. Speech is generated with a **non-autoregressive conditional flow-matching DiT** in the frozen [AudioVAE2](https://huggingface.co/openbmb/VoxCPM2) latent space (25 Hz, 64-dim latents, 16 kHz encode / 48 kHz decode). Training runs from scratch on Turkish speech: a pretraining stage followed by SFT stage 1/2 for voice lock and short-utterance coverage. Output is 48 kHz mono. On the project's Freya-TR-Eval benchmark the model reports **WER 8.0% / CER 3.0%**, ranking 3rd of 7 among open sub-1B Turkish TTS systems — a deliberate **single-target-speaker, no-cloning** design choice for a focused foundation release. The evaluation dataset is [freya-tr-eval](https://huggingface.co/datasets/freyavoice/freya-tr-eval).

**Release Date:** July 7, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 183.2M |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Languages** | Turkish (tr) |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Architecture** | conditional flow-matching diffusion transformer (DiT), non-autoregressive, 32-step Euler ODE, no CFG |
| **Tokenizer** | character-level (92 Turkish symbols; no phonemizer, no G2P) |
| **Latent Space** | frozen AudioVAE2 (Apache-2.0, openbmb/VoxCPM2), 64-dim at 25 Hz |
| **Codec Io** | 16 kHz encode / 48 kHz decode |
| **Sample Rate** | 48,000 Hz |
| **Training** | from scratch on Turkish speech; pretraining + SFT stage 1/2 (voice lock + short-utterance coverage) |
| **Evaluation** | Freya-TR-Eval — WER 8.0% / CER 3.0%, 3rd of 7 open sub-1B Turkish TTS |
| **Library Name** | freyatts |

**Features:** Two design choices are worth flagging. First, **tokenizer-free
character-level Turkish**: by training directly on the 92-symbol
Turkish alphabet with no phonemizer or G2P grapheme-to-phoneme step,
the model removes a dependency that is fragile for agglutinative
Turkish morphology and that often degrades quality when ported to
low-resource Turkic relatives. Second, **non-autoregressive
conditional flow-matching in a frozen AudioVAE2 latent space**:
the 25 Hz / 64-dim bottleneck keeps the DiT small (183M) while
inheriting a separately-trained audio codec's representation,
letting a focused single-language-non-multilingual release ship at
a fraction of the parameter budget of multilingual foundation TTS
systems. The deliberate "no cloning, single target speaker" choice
is a scope-lowering move that lets the foundation release put all
its capacity into Turkish speech quality rather than spread it
across zero-shot speaker adaptation.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/freyavoice/Freya-TTS)
[![GitHub][link-github]](https://github.com/freyavoiceai/FreyaTTS)
[![Paper][link-paper]](https://arxiv.org/abs/2607.09530)

</details>
<!-- /MODEL:freyatts.md -->
<!-- MODEL:gepard.md -->
<details id="gepard">
<summary>Gepard</summary>

### Gepard

**Description:** **GE**nerative, **P**rosody-aware, **A**utoregressive text-to-speech model for **R**ealtime **D**ialogue. Gepard is built for low-latency, high-throughput streaming conversation: the model starts speaking the moment text begins arriving, generating audio piece by piece instead of waiting for a full sentence. It is a single decoder-only autoregressive language model built on Qwen3.5 (14 layers, hidden 1024, 8 heads) with ≈556M total parameters (backbone + audio interface + voice-cloning compressor). Audio is produced through NVIDIA NeMo NanoCodec — Finite Scalar Quantization at 22.05 kHz, 21.5 frames/s, 1.89 kbps — with the full 32-channel FSQ frame sampled in one step. Reports ~25× real time on a single RTX 5090 with first-audio-chunk latency around 50 ms; a 96 GB Blackwell card serves up to 256 concurrent conversations. CFG refinement is baked into the weights so quality gain comes at no extra two-pass cost at inference, though the two-pass mode is still selectable as a quality dial.

**Release Date:** June 22, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | ~556M (Qwen3.5-14 backbone + audio interface + voice-cloning compressor) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ❌ |
| **Languages** | English (US/UK), Spanish (es-MX), Portuguese (pt-BR), Dutch (NL) |
| **Streaming** | ✅ |
| **License** | ![Research Only][license-research-only] |
| **Audio Codec** | NVIDIA NeMo NanoCodec (FSQ, 22.05 kHz, 21.5 fps, 1.89 kbps) |
| **Sample Rate** | 22,050 Hz |
| **Backbone** | Qwen3.5 full-attention transformer (14 layers, hidden 1024, 8 heads; ~500M params) |
| **Inference** | vLLM |
| **Throughput** | 256 conversations on one 96 GB Blackwell (RTX Pro 6000) GPU |

**Features:** A prosody-aware autoregressive single-pass frame generator: the whole
32-channel FSQ audio frame is sampled in one step (no depth transformer),
and CFG quality refinement is **baked into the weights** rather than
incurred at inference as a two-pass cost — so the publicly reported TTFA
of ~50 ms and 25× real time on a single RTX 5090 represent the
quality-on path, not a cheap-fast preview. Voice cloning is decoupled
into a separate up-front compressor, which means cloning is "free" at
run-time once the reference clip is encoded — a structural choice that
supports serving hundreds of conversations per GPU.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/nineninesix/gepard-1.0)
[![Demo][link-demo]](https://huggingface.co/spaces/nineninesix/gepard)
[![Paper][link-paper]](https://huggingface.co/nineninesix/gepard-1.0/resolve/main/gepard_techreport.pdf)
[![Website][link-website]](https://www.nineninesix.ai/)

</details>
<!-- /MODEL:gepard.md -->
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
<!-- MODEL:voxflash-tts.md -->
<details id="voxflash-tts">
<summary>VoxFlash-TTS</summary>

### VoxFlash-TTS

**Description:** **VoxFlash-TTS** is a zero-shot voice-cloning text-to-speech engine built around extreme latent compression. The VAE encodes 24 kHz waveforms into a **9 frames/s** latent space — roughly 8× more compressed than EnCodec (75 fps) and 2.4× more than Stable Audio (21.5 fps). Generating 10 s of audio therefore requires the diffusion model to produce just **90 latent vectors** rather than hundreds or thousands of tokens, with downstream quadratic savings in attention cost. A ConvNeXtV2-based phoneme encoder followed by a novel coarse-alignment algorithm (cheaper than cross-attention) maps text into the latent sequence; a modern diffusion head then iteratively refines speech latents that the lightweight VAE decoder renders back to waveforms. The architecture targets low-latency, low-resource deployment — consumer-grade GPUs and edge devices — with Chinese and English zero-shot cloning. The project card lists `inference: false` on HF (no hosted inference endpoint), but the project page at [voxflash.github.io](https://voxflash.github.io/) carries the abstract, demo examples, and ablations.

**Release Date:** May 22, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | not stated (ConvNeXtV2 phoneme encoder + diffusion head + lightweight VAE decoder) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Languages** | Chinese, English |
| **Streaming** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Audio Codec** | VoxFlash VAE (9 Hz / 9 fps latent, 24 kHz input) |
| **Compression Ratio** | ~8× tighter than EnCodec (75 fps), ~2.4× tighter than Stable Audio (21.5 fps) |
| **Phoneme Encoder** | ConvNeXtV2 + coarse-alignment algorithm (no cross-attention) |
| **Diffusion Head** | modern multi-step iterative refinement |
| **Decoder** | lightweight VAE decoder |
| **Sample Rate** | 24,000 Hz |
| **Inference** | local CUDA ≥ 12.3.2; no HF hosted endpoint |
| **Training Dataset** | seed-tts-eval |
| **Metrics** | word_error_rate, speaker_similarity |

**Features:** The central technical move is **compressing the audio latent
space to 9 frames/s instead of the conventional 75 fps (EnCodec)
or 21.5 fps (Stable Audio)**. This is not a quantization tweak —
it is a temporal-decimation architectural choice that shrinks the
sequence length the diffusion model has to traverse, and because
attention cost scales quadratically with sequence length the
end-to-end compute drops by orders of magnitude. Combined with a
**coarse-alignment phoneme-to-latent map that avoids cross-attention
entirely** (using a ConvNeXtV2 phoneme encoder instead), VoxFlash
hits millisecond-level inference latency on consumer-grade and
edge hardware for zero-shot Chinese + English cloning, where
conventional latent-diffusion TTS systems are too slow for real-time
edge deployment.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/VoxFlashTTS/VoxFlashTTS)
[![GitHub][link-github]](https://github.com/VoxFlash/VoxFlashTTS)
[![Website][link-website]](https://voxflash.github.io/)
[![Paper][link-paper]](https://arxiv.org/abs/2406.02430)

</details>
<!-- /MODEL:voxflash-tts.md -->
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
<!-- MODEL:soprano.md -->
<details id="soprano">
<summary>Soprano</summary>

### Soprano

**Description:** **Soprano** is an ultra-lightweight, on-device text-to-speech (TTS) model designed for expressive, high-fidelity speech synthesis at unprecedented speed. The 1.1 release ships an 80M-parameter backbone that achieves up to **20× real-time generation on CPU** and **2000× real-time on GPU**, with **lossless streaming** (<250 ms latency on CPU, <15 ms on GPU), **<1 GB memory usage** at inference, and **infinite generation length** (automatic text splitting). Output sample rate is **32 kHz**, with widespread device support (CUDA / CPU / MPS on Windows, Linux, and Mac). Inference is production-ready through an OpenAI-compatible endpoint, ONNX, WebUI, CLI, and ComfyUI nodes. The base 1.1 model is `ekwek/Soprano-1.1-80M` on HuggingFace; a fine-tuning toolkit (`soprano-factory`) was released January 13 2026 alongside the 1.1 weights — the 1.1 release reports **95% fewer hallucinations** and a **63% preference rate** over 1.0 (Soprano-80M). A live demo runs on `ekwek/Soprano-TTS` HF Space.

**Release Date:** December 22, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 80M (Soprano-1.1-80M) |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Languages** | English (US/UK family voices, per HF Space) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Sample Rate** | 32,000 Hz |
| **Inference Targets** | OpenAI-compatible endpoint, ONNX, WebUI, CLI, ComfyUI |
| **Performance Cpu** | up to 20× real-time |
| **Performance Gpu** | up to 2000× real-time |
| **Memory** | <1 GB at inference |
| **Text Length** | infinite (automatic text splitting) |
| **Devices** | CUDA, CPU, MPS (Windows, Linux, Mac) |
| **Training Toolkit** | soprano-factory (https://github.com/ekwek1/soprano-factory) |
| **History 1 1** | Soprano-1.1-80M released 2026-01-14 (95% fewer hallucinations; 63% preference over 1.0) |
| **History 1 0** | Soprano-80M released 2025-12-22 |

**Features:** The defining trade-off of this release is **extreme on-device
efficiency at sub-100M scale**: an 80M-parameter backbone hits
**<250 ms CPU latency** and **<15 ms GPU** for lossless streaming
while keeping inference within <1 GB of memory — well under the
multi-billion-parameter budget that newer conversational TTS
systems require. The release pairs the model with `soprano-factory`
(open-source training/fine-tuning toolkit) so users can build their
own voices on top of the same backbone, and one installation can
drive OpenAI-compatible / ONNX / WebUI / CLI / ComfyUI inference.
The 1.1 update is a measured iteration: 95% fewer hallucinations
and a 63% preference over 1.0 at the same parameter budget, so the
measurable quality jump ships with no added inference cost.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/ekwek/Soprano-1.1-80M)
[![GitHub][link-github]](https://github.com/ekwek1/soprano)
[![Demo][link-demo]](https://huggingface.co/spaces/ekwek/Soprano-TTS)

</details>
<!-- /MODEL:soprano.md -->
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
<!-- MODEL:echo-tts.md -->
<details id="echo-tts">
<summary>Echo-TTS</summary>

### Echo-TTS

**Description:** **Echo** is a 2.4B-parameter **diffusion-based diffusion transformer (DiT)** text-to-speech model. It conditions on target text and up to **two minutes of speaker reference audio**, generates Fish Speech S1-DAC latents, and decodes to **44.1 kHz** audio. Output length is up to **30 seconds per segment**. The model is fast at single-sample generation: on one A100, generating 30 seconds of audio from a 120-second prompt takes **~1.45 seconds** (RTF < 0.05) — substantially faster than frontier autoregressive approaches at similar quality. The architecture is a deliberate pivot from the author's prior autoregressive-in-DAC-space model **Parakeet**, which struggled with semantic-consistency retries and weak voice cloning; Echo's diffusion approach trades off real-time interactivity for **fast, high-fidelity zero-shot voice cloning** in offline synthesis. Trained via the TPU Research Cloud (TRC). Demo (preview) hosted on `jordand/echo-tts-preview` HF Space; base model on `jordand/echo-tts-base`.

**Release Date:** December 4, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 2.4B (DiT) |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Languages** | English (per demo samples) |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |
| **Architecture** | diffusion transformer (DiT) in Fish Speech S1-DAC latent space |
| **Max Segment Duration** | 30 s |
| **Sample Rate** | 44,100 Hz |
| **Speaker Reference Max** | 120 s |
| **Performance A100 Rt** | 30 s output in ~1.45 s (RTF < 0.05) |
| **Audio Codec** | Fish Speech S1-DAC |
| **Prior Model** | Parakeet (autoregressive in DAC space) |
| **Training Infrastructure** | TPU Research Cloud (TRC) |
| **Inference Requirements** | CUDA-capable GPU with at least 8 GB VRAM; Python 3.10+ |
| **Sampler** | euler CFG with independent guidances for text (3.0) and speaker (8.0); 40 steps; sequence_length 640 default |
| **License Clarification** | MIT (per GH repo license) |

**Features:** Echo is a deliberate **next-step pivot from autoregressive-in-DAC-space
TTS to a full diffusion approach**. The author's prior model,
Parakeet, generated DAC tokens autoregressively but suffered the
classic AR weakness — semantic-consistency retries — and weak
voice cloning. Echo keeps Fish Speech S1-DAC latents (so the audio
representation is the same proven codec) but moves the generator
*upstream* to a 2.4B DiT operating directly on those latents,
conditioned on a long (up to 2-minute) speaker reference. The
result: 30-second outputs in ~1.45 s on a single A100 (RTF < 0.05)
with high-fidelity zero-shot cloning — fast enough that the
"diffusion is too slow" objection no longer applies at the segment
length that matters for offline content generation, while the AR
class's retry-induced inconsistency is gone by construction.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/jordand/echo-tts-base)
[![GitHub][link-github]](https://github.com/jordandare/echo-tts)
[![Demo][link-demo]](https://huggingface.co/spaces/jordand/echo-tts-preview)
[![Blog][link-blog]](https://jordandarefsky.com/blog/2025/echo/)

</details>
<!-- /MODEL:echo-tts.md -->
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
<!-- MODEL:marvis-tts.md -->
<details id="marvis-tts">
<summary>Marvis-TTS</summary>

### Marvis-TTS

**Description:** **Marvis** is a conversational real-time streaming TTS from Marvis-Labs. The architecture inherits Sesame's **CSM-1B** (Conversational Speech Model): a 250M-parameter **multimodal backbone** that processes interleaved text + audio tokens and a smaller 60M-parameter **audio decoder** that models the remaining 31 RVQ codebook levels to reconstruct high-quality speech from the backbone's representations. Audio tokens come from **Kyutai's mimi codec** (RVQ tokens). The dual-transformer split — semantic backbone + small decoder — yields sub-second latency, and the model is built for **on-edge / on-device** deployment (Apple Silicon / iPad / iPhone / Mac). Two operational choices distinguish Marvis:

**Release Date:** November 6, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 250M (multimodal backbone) + 60M (audio decoder) = 310M total |
| **Voice Cloning** | ✅ |
| **Asr** | ❌ |
| **Languages** | English, French, German |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Architecture** | dual-transformer CSM-1B (Conversational Speech Model) — multimodal backbone + audio decoder |
| **Audio Codec** | Kyutai mimi codec (RVQ tokens; backbone models codebook 0, decoder models codebook 1–31) |
| **Quantized Size** | ~500 MB (4-bit MLX) |
| **Training Dataset** | amphion/Emilia-Dataset |
| **Library Name** | transformers, mlx, mlx-audio |
| **Inference Cli** | `mlx_audio.tts.generate --model Marvis-AI/marvis-tts-250m-v0.2 --stream --text "..." [--ref_audio ./x.wav]` |
| **Variants In Collection** | 250m-v0.2, 250m-v0.2-MLX-{4bit,6bit,8bit}, 100m-v0.2 (+ MLX variants), 250m-v0.2-transformers |
| **Emits Text Chunking** | no (full-sequence contextual processing) |

**Features:** Two operational choices make Marvis stand out among conversational
TTS. First, **no regex chunking**: most streaming TTS engines
pre-split sentences by regex patterns before feeding them to the
generator, which can disrupt flow / intonation; Marvis processes
the entire text contextually, treating the text as a single
interleaved multimodal sequence. Second, the **dual-transformer
CSM-1B design** — a 250M backbone for codebook 0 (semantic) and a
smaller 60M audio decoder for codebooks 1-31 (acoustic) — produces
a quantized footprint of ~500 MB, enabling **on-device Apple-Silicon
inference** (iPad / iPhone / Mac) with real-time streaming. The
architecture makes a high-quality CSM-style TTS with zero-shot
cloning actually deployable at the edge, while the official
collection's 4 / 6 / 8-bit MLX variants let users trade footprint
for fidelity on a per-device basis.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/Marvis-AI/marvis-tts-250m-v0.2)
[![GitHub][link-github]](https://github.com/Marvis-Labs/marvis-tts)

</details>
<!-- /MODEL:marvis-tts.md -->
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
<!-- MODEL:kani-tts.md -->
<details id="kani-tts">
<summary>KaniTTS</summary>

### KaniTTS

**Description:** **KaniTTS** is a 370M-parameter two-stage text-to-speech model from nineninesix-ai. The architecture pairs an **LFM-2 backbone LLM** (Liquid Foundation Model v2 — a non-transformer, structured state-space architecture) with a **neural audio codec** for output waveform synthesis. The LLM generates compressed audio-token representations and the codec renders them to 22 kHz waveforms, yielding low-latency generation: **~1 s to produce 15 s of audio on a single RTX 5080**, with **2 GB GPU VRAM** at inference, and **MOS 4.3 / WER < 5%** quality on the project's benchmarks. Languages covered: **English, German, Chinese, Korean, Arabic, Spanish** across multiple per-language voices (English, German, Chinese, Korean, Arabic, Spanish each ship a 400M checkpoint; Japanese ships a 370M "Expo-2025-Osaka" variant; a multilingual 370M checkpoint is also available). MLX variants exist for Apple-Silicon inference. The codec is the same author's `nemo-nano-codec-22kHz-0.6kbps-12.5fps-MLX` (NVIDIA NeMo NanoCodec, MLX-ported to ~12.5 fps / 0.6 kbps). The model is part of the nineninesix-ai family alongside Gepard.

**Release Date:** September 30, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 370M (kani-tts-370m multilingual); 400M per-language (en / de / zh / ko / ar / es); 370M (expo2025-osaka-ja) |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Languages** | English, German, Chinese, Korean, Arabic, Spanish (multilingual 370M checkpoint); Japanese (Expo-2025-Osaka variant) |
| **Streaming** | ✅ |
| **License** | ![Unknown][license-unknown] |
| **Sample Rate** | 22,000 Hz |
| **Backbone Llm** | LFM-2 (Liquid Foundation Model; non-transformer structured state-space architecture) |
| **Audio Codec** | nineninesix/nemo-nano-codec-22khz-0.6kbps-12.5fps-MLX (NVIDIA NeMo NanoCodec, MLX-ported) |
| **Performance Rt 5080** | ~1 s for 15 s audio on RTX 5080 |
| **Memory** | 2 GB GPU VRAM at inference |
| **Quality Mos** | 4.3 / 5 (naturalness) |
| **Quality Wer** | <5% (accuracy) |
| **Training Dataset** | ~80k hours (LibriTTS, Common Voice, Emilia) |
| **Training Hardware** | 8x H100 GPUs, 45 hours on Lambda AI |
| **Per Language Models** | kani-tts-400m-{en,zh,de,ar,es,ko} on HuggingFace |
| **Pretrained Checkpoints** | 0.2-pt (450M), 0.3-pt (400M) for custom posttraining / fine-tuning |
| **Mlx Variants** | kani-tts-370m-MLX (Apple Silicon) |
| **Arxiv** | 2505.20506 |

**Features:** KaniTTS's design choice worth flagging: it pairs a **non-transformer
LFM-2 backbone** (Liquid Foundation Model — structured state-space
rather than attention) with a **neural audio codec for output** at
the **370M scale**. The choice lets the model hit a ~1 s / 15 s
audio generation rate on a **2 GB GPU VRAM budget** — sub-1B
parameters, sub-entry-tier GPU requirement, but still multilingual
across six languages. The two-stage approach (LLM → codec) is
conventional; what's less conventional is the choice of a
state-space backbone over the usual transformer decoder at this
scale, hitting latency / VRAM numbers that open up sub-1B real-time
TTS on consumer-grade hardware. The same author ships `soprano-factory`-style
companion assets (pretrained v0.2-pt / v0.3-pt checkpoints, a
NeMo NanoCodec MLX port) to lower the bar for fine-tuning on custom
datasets.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/nineninesix/kani-tts-370m)
[![GitHub][link-github]](https://github.com/nineninesix-ai/kani-tts)

</details>
<!-- /MODEL:kani-tts.md -->
<!-- MODEL:vibevoice-finetuning.md -->
<details id="vibevoice-finetuning">
<summary>VibeVoice-Finetuning</summary>

### VibeVoice-Finetuning

**Description:** This is an **unofficial, work-in-progress LoRA fine-tuning toolkit** for the VibeVoice TTS / speech model (1.5B-base and 7B-base checkpoints). The base VibeVoice checkpoints are the same ones covered in this list's [a separate entry](#modelvibevoice-realtimemd): audio-conditioned diffusion TTS for spoken dialogue, streaming, etc. This toolkit takes **pretrained VibeVoice** weights + a paired (text, audio, optional reference-audio) dataset and trains a **LoRA adapter** against two losses simultaneously:

**Release Date:** September 16, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 1.5B (LoRA-adapted) / 7B (LoRA-adapted) |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Languages** | inherits base VibeVoice coverage |
| **Streaming** | not directly (toolkit output is a LoRA adapter; the adapter inherits VibeVoice inference shape) |
| **License** | ![MIT][license-mit] |
| **Loss Text** | masked cross-entropy on text tokens |
| **Loss Acoustic** | diffusion MSE on acoustic latents |
| **Hardware 1 5B** | ≥16 GB VRAM |
| **Hardware 7B** | ≥48 GB VRAM |
| **Transformers Version** | 4.51.3 (known-good; other versions may break on Qwen2 architecture) |
| **Tested Docker Image** | runpod/pytorch:2.8.0-py3.11-cuda12.8.1-cudnn-devel-ubuntu22.04 |
| **Audio Target Format** | 24 kHz audio (paired dataset of target-audio + transcripts + optional reference-audio prompts) |
| **Training Entrypoint** | `python -m src.finetune_vibevoice_lora --model_name_or_path aoi-ot/VibeVoice-Large --processor_name_or_path src/vibevoice/processor --dataset_name <your/dataset> --text_column_name text [--voice_column_name audio_ref]` |
| **Supports Hf Dataset Loader** | yes |
| **Output** | LoRA adapter compatible with VibeVoice base |

**Features:** The dual-loss trick is the technical center of this toolkit. Naive
LoRA fine-tuning of a unified TTS model often specializes the
synthesis but **silently damages the text LLM capability** the
base inherited from its Qwen-class backbone; the
"masked CE on text tokens + diffusion MSE on acoustic latents"
two-headed loss preserves both competencies at training time. Pair
that with the careful pinning of Transformers 4.51.3 (other versions
break on the Qwen2 architecture) and a documented minimum-VRAM
budget per base size (16 GB for 1.5B, 48 GB for 7B), and you get a
reproducible recipe for **community fine-tuning of VibeVoice** —
something the official Microsoft VibeVoice release doesn't ship
out-of-the-box.

**Links:**
[![GitHub][link-github]](https://github.com/voicepowered-ai/VibeVoice-finetuning)

</details>
<!-- /MODEL:vibevoice-finetuning.md -->
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
<!-- MODEL:espeak-ng.md -->
<details id="espeak-ng">
<summary>eSpeak-NG</summary>

### eSpeak-NG

**Description:** **eSpeak NG** is a compact open-source software text-to-speech synthesizer for Linux, Windows, Android, and other operating systems. It supports **more than 100 languages and accents**, is a fork of Jonathan Duddington's original eSpeak engine, and uses the **formant synthesis** method: the model produces speech by explicitly computing the acoustic resonances (formants) of each phoneme, not by concatenating human-speech recordings. The trade is well-known — the speech is clear and usable at high playback speeds, but **not as natural or smooth** as larger neural or concatenative synthesizers. The compensation is size: the program and its data, including many languages, total a few megabytes. Other synthesis methods supported: **Klatt formant synthesis** and **MBROLA diphone back-end** via the documented integration.

**Release Date:** December 8, 2015

| Feature | Value |
|---------|-------|
| **Parameters** | n/a (formant-synthesis engine; not a neural model) |
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Languages** | 100+ languages and accents (see docs/languages.md) |
| **Streaming** | ✅ |
| **License** | ![Unknown][license-unknown] |
| **Synthesis Method** | formant synthesis (primary); Klatt formant synthesis (secondary); MBROLA diphone backend (optional) |
| **Footprint** | a few MB (program + data + many languages) |
| **Audio Output** | WAV file (CLI), direct playback, or shared-library API |
| **Input Formats** | text from file / stdin (CLI), SSML (partial), HTML (partial) |
| **Packages** | CLI (espeak-ng man page), shared library (libespeak-ng), SAPI5 Windows module |
| **Supersedes** | eSpeak (Jonathan Duddington's original engine) |
| **Downstream Usage** | G2P / phonemizer for neural TTS pipelines (e.g. sanoTTS bundles espeak-ng for its duration model) |
| **Platforms** | Linux, Windows, Android, Solaris, Mac OS X |

**Features:** eSpeak-NG is **the** canonical reference implementation of compact
multi-language formant synthesis. Its 100+-language coverage in a
few megabytes, plus SSML / SAPI5 / MBROLA / shared-library / CLI
surfaces, are matched only by neural TTS systems that are **orders
of magnitude larger**. The reason it belongs in a list whose other
entries are neural TTS systems is its continued quiet role in the
neural stack as a **G2P / phonemizer front-end** — the phoneme
inventory and grapheme-to-phoneme rules that sanoTTS and similar
sub-1B neural TTS engines bundle are often just a port of
eSpeak-NG's language-data files. So even if the formant-synthesis
audio output itself has been surpassed for naturalness, the
**phoneme infrastructure** underneath many of the smaller neural
TTS entries on this list still traces back to eSpeak-NG.

**Links:**
[![GitHub][link-github]](https://github.com/espeak-ng/espeak-ng)

</details>
<!-- /MODEL:espeak-ng.md -->

---

## Anything to Audio

Models that can generate audio from multiple input modalities (video, text, image, audio). These are unified frameworks for multimodal audio synthesis.

### Anything to Audio Quick Comparison

| Model | Text | Video | Audio | Max Duration | Sample Rate | License |
| :--- | :---: | :---: | :---: | :--- | :--- | :--- |
| [ScenA](#scena) | ✅ | ❌ | ✅ | — | — | ![Unknown][license-unknown] |
| [Nemotron-Labs-Audex-2B](#nemotron-labs-audex-2b) | ✅ | ❌ | ✅ | — | — | ![Unknown][license-unknown] |
| [Nemotron-Labs-Audex-30B-A3B](#nemotron-labs-audex-30b-a3b) | ✅ | ❌ | ✅ | — | — | ![NVIDIA NC][license-nvidia-noncommercial] |
| [MOSS-SoundEffect](#moss-soundeffect) | ✅ | — | — | 30 s | 48 kHz | ![Apache 2.0][license-apache-2.0] |
| [Omni2Sound (Omni2Audio)](#omni2sound) | ✅ | ✅ | ✅ | — | — | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [ControlFoley](#controlfoley) | ✅ | ✅ | ✅ | — | 44,100 Hz | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [Woosh](#woosh) | ✅ | ✅ | — | — | — | ![Apache 2.0][license-apache-2.0] |
| [Chroma-4B](#chroma-4b) | ✅ | ❌ | ✅ | — | — | ![Apache 2.0][license-apache-2.0] |
| [Uni-MoE (Audio)](#uni-moe-audio-any2audio) | ✅ | ✅ | — | — | — | ![Apache 2.0][license-apache-2.0] |
| [AudioX / Audio-Omni](#audiox) | ✅ | ✅ | ✅ | — | — | ![Apache 2.0][license-apache-2.0]<br>![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| [HunyuanVideo-Foley](#hunyuanvideo-foley) | ✅ | ✅ | — | — | 48 kHz | ![Unknown][license-unknown] |
| [PrismAudio](#prismaudio) | — | ✅ | — | — | — | ![Apache 2.0][license-apache-2.0] |
| [ThinkSound](#thinksound) | ✅ | — | ✅ | — | — | ![Apache 2.0][license-apache-2.0] |
| [MMAudio](#mmaudio) | ✅ | ✅ | — | — | — | ![Apache 2.0][license-apache-2.0] |

<!-- MODEL:scena.md -->
<details id="scena">
<summary>ScenA</summary>

### ScenA

**Description:** **ScenA** generates multi-speaker audio *scenes* — dialogue and conversation with sound effects and ambience — from a text prompt, conditioned on one or more **reference-audio** clips that set the speakers' voices. Unlike prior multi-speaker dialogue systems it uses **no** per-turn tags, multi-stream transcripts, or speaker embeddings: a free-form natural-language prompt alone describes the scene. The text prompt determines which reference voice speaks where, allowing overlapping speech, spontaneous paralinguistic events, and scene-level ambient sound — all inherited from the in-the-wild text-to-audio pretraining distribution. The architecture is an audio-only, reference-conditioned flow-matching DiT built on the LTX-2 backbone (~4B parameters, 48 layers). Reference latents are concatenated into the token sequence and distinguished by lightweight identity-aware positional encodings. The training tackles a specifically identified "Reference Shortcut" failure mode — under standard noise schedules the model can identify the matching reference by noisy-target acoustic similarity, bypassing the text prompt — by using a high-noise-biased timestep distribution that forces reliance on the prompt for speaker assignment. Evaluator: CoVoMix2-Dialogue benchmark. Project page, code, paper, and HuggingFace checkpoint are linked below.

**Release Date:** July 7, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | ~4B (DiT, 48 layers; built on LTX-2 architecture) |
| **Text** | ✅ |
| **Video** | ❌ |
| **Audio** | ✅ |
| **Max Duration** | not stated (scene-level generation) |
| **Sample Rate** | (not stated; inherits LTX-2 audio VAE) |
| **Voice Cloning** | ✅ |
| **Multi Speaker** | yes |
| **Ambient Sound** | yes (SFX, room acoustics, overlapping speech) |
| **Architecture** | flow-matching DiT (LTX-2 backbone, audio-only) |
| **Speaker Assignment** | natural language (no per-turn tags / identity encoders) |
| **Training Fix** | high-noise-biased timestep distribution (defeats Reference Shortcut) |
| **Text Encoder** | google/gemma-3-12b-it |
| **Audio Vae** | bundled (~365 MB; encodes+decodes so full LTX-2 not needed) |
| **Checkpoint Size** | ~8.2 GB (scena.safetensors) + ~365 MB (audio_vae.safetensors) |
| **License** | ![Unknown][license-unknown] |
| **Training Data** | in-the-wild text-to-audio pretrained, then reference-conditioned fine-tune |
| **Evaluation** | CoVoMix2-Dialogue (speaker-binding metrics) |

**Features:** The "Reference Shortcut" failure-mode identification is the
technical center of the work: under standard diffusion noise
schedules, a multi-speaker reference-conditioned model can match
each reference to the noisy-target segment by acoustic similarity
alone, bypassing the text prompt entirely. ScenA's high-noise-biased
timestep distribution forces the model to rely on the prompt for
speaker assignment at training time. Combined with the absence of
any per-turn speaker structure (tags / transcripts / identity
encoders) and the prompt's role as the *only* speaker-routing
signal, this yields multi-speaker conversational scenes with
overlapping speech, paralinguistic events, and ambient texture
that previous structured-supervision multi-speaker systems filter
out by design.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/mifinkelson/scena)
[![GitHub][link-github]](https://github.com/finmickey/scena)
[![Website][link-website]](https://finmickey.github.io/scena/)
[![Paper][link-paper]](https://arxiv.org/abs/2606.19325)

</details>
<!-- /MODEL:scena.md -->
<!-- MODEL:nemotron-labs-audex-2b.md -->
<details id="nemotron-labs-audex-2b">
<summary>Nemotron-Labs-Audex-2B</summary>

### Nemotron-Labs-Audex-2B

**Description:** **Nemotron-Labs-Audex-2B** is NVIDIA's smaller sibling of the Audex unified audio-text LLM. Like the **30B-A3B** flagship, the 2B is a single model family that both **understands audio** (audio QA, speech recognition, speech translation) and **generates audio** (text-to-speech, text-to-audio, speech-to-speech). It is built on the same audio-vocabulary-extended transformer stack as the 30B-A3B but at a **densely-parameterized 2B scale** (no MoE), so the compute and memory footprint are lowered to a budget tractable on more modest hardware. The 2B checkpoint is the project-tagged **SFT variant** in the Audex collection — instruction-tuned and ready for inference. Both sizes preserve text reasoning, alignment, knowledge, long-context, and agentic capabilities of the text backbone while adding discrete-token audio I/O.

**Release Date:** July 6, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 2B (dense; SFT fine-tune, instruct + reasoning-ready) |
| **Text** | ✅ |
| **Video** | ❌ |
| **Audio** | ✅ |
| **Modalities** | text + audio (input and output) |
| **Max Duration** | not stated |
| **Sample Rate** | not stated (decoder output) |
| **Voice Cloning** | ❌ |
| **Audio Understanding** | yes (audio QA, classification) |
| **Asr** | ✅ |
| **Speech Translation** | yes |
| **Text To Speech** | yes |
| **Text To Audio** | yes |
| **Speech To Speech Generation** | yes |
| **Reasoning Mode** | yes (thinking + instruct modes inherited from text backbone) |
| **License** | ![Unknown][license-unknown] |
| **Pipeline Tag** | text-generation |
| **Library Name** | transformers |
| **Derived From** | same family as Nemotron-Labs-Audex-30B-A3B |
| **Companion 30B** | nvidia/Nemotron-Labs-Audex-30B-A3B (MoE: 30B total, 3B active) |
| **Spaces** | nvidia/Nemotron-Labs-Audex, WaveCut/Nemotron-Labs-Audex, hugging-apps/nemotron-labs-audex-2b |
| **Createdat** | 2026-07-06T16:21:07Z |
| **Downloads** | ~2.4k |

**Features:** The 2B sibling matters because it preserves the *central thesis* of
the Audex paper — **unified audio-text LLM intelligence without
regressing on text intelligence** — while dropping the parameter
budget substantially. The 30B-A3B MoE hits a 1M-context, agentic
flagship tier; the 2B dense version is the same audio-aware
architecture extended down to a budget that doesn't require a
high-end MoE serving stack. The pair lets users choose on
deployment cost rather than on capability sub-selection: the 2B
ships the same audio-to-audio + text-to-audio + audio-understanding
+ ASR + speech-translation coverage as the MoE flagship, just at
the cost of longer-context / reasoning depth that the MoE was
specifically tuned for. Both share the **discrete-audio-token
vocabulary extension** of the text backbone so they can be reasoned
about interchangeably.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/nvidia/Nemotron-Labs-Audex-2B)
[![Paper][link-paper]](https://arxiv.org/abs/2607.05196)
[![Collection][link-collection]](https://huggingface.co/collections/nvidia/nemotron-labs-audex)
[![Demo][link-demo]](https://huggingface.co/spaces/nvidia/Nemotron-Labs-Audex)

</details>
<!-- /MODEL:nemotron-labs-audex-2b.md -->
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

**Description:** **ControlFoley** (Xiaomi MiLM Plus) is a unified controllable video-to-audio (foley) generation model. It supports four conditioning combinations under one architecture:

**Release Date:** April 13, 2026

| Feature | Value |
|---------|-------|
| **Conditioning** | Text / Video / Text + Video / Video + Reference Audio |
| **Modalities** | Video (visual), Audio (foley) |
| **Asr** | ❌ |
| **Voice Cloning** | ❌ |
| **Text** | ✅ |
| **Video** | ✅ |
| **Image** | ❌ |
| **Audio** | ✅ |
| **Sample Rate** | 44,100 Hz |
| **License** | ![CC BY-NC 4.0][license-cc-by-nc-4.0] |
| **Pipeline Tag** | text-to-audio |
| **Library** | diffusers |
| **Cross Modal Conflict** | handled via modality-specific control (no explicit router) |
| **Inference Skill** | ClawHub ControlFoley Audio Generator |
| **Upcoming** | ComfyUI nodes (in preparation, expanding to V2A / TV2A / TC-V2A / AC-V2A / T2A) |

**Features:** **Modality-specific cross-modal conflict resolution** in a single
generative stack: text governs semantics, reference audio governs
timbre/acoustic style, and video governs temporal synchronization.
Rather than routing to a single user-trusted modality, the model
**decouples control axes** so an input disagreement (video shows a
dog barking, text asks for a cat) is decomposed into a coherent
output that respects each modality's responsibility. Trained with
all-modality dropout for modality-robustness, ControlFoley is the
first foley system that brings all four conditioning modes — T2A,
V2A, TV2A, AC-V2A — under one model.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/YJX-Xiaomi/ControlFoley)
[![GitHub][link-github]](https://github.com/xiaomi-research/controlfoley)
[![Demo][link-demo]](https://yjx-research.github.io/ControlFoley/)
[![Website][link-website]](https://yjx-research.github.io/ControlFoley_web_page/)
[![arXiv][link-arxiv]](https://arxiv.org/abs/2604.15086)
[![Skill][link-skill]](https://clawhub.ai/yjx-research/controlfoley-audio-generator)

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
<!-- MODEL:chroma-4b.md -->
<details id="chroma-4b">
<summary>Chroma-4B</summary>

### Chroma-4B

**Description:** **Chroma 1.0** (FlashLabs' `Chroma-4B` on HuggingFace) is the first open-source, real-time, **end-to-end spoken dialogue model** that achieves both **sub-second end-to-end latency** and **high-fidelity personalized voice cloning**. The pipeline is end-to-end — no separate ASR → LLM → TTS stitch — speech goes in, speech comes out. The architectural centerpiece is an **interleaved text-audio token schedule (1 text : 2 audio)** that supports streaming generation, so the model can begin emitting audio while the user is still talking (broken-off turns / barge-in handled). Experimental results from the project's paper:

**Release Date:** November 28, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 4B |
| **Voice Cloning** | ✅ |
| **Asr** | ✅ |
| **Languages** | English (per benchmark reporting) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Architecture** | end-to-end spoken-dialogue LLM; interleaved text-audio token schedule (1:2); custom_code modules |
| **Pipeline Tag** | any-to-any (HF classification) |
| **Audio Tokenization** | chroma tokenizer (RVQ-style per project's tag) |
| **Latency Rtf** | 0.43 (speech out ~2.3× wall-clock) |
| **Speaker Similarity** | +10.96% relative improvement over human baseline |
| **Inference Library** | transformers (custom_code) |
| **Correlations With Larger Class** | matches full dialogue turn at streaming latency |
| **Pretrained** | yes (safetensors weights) |
| **Hf Space Demos** | hysts/Chroma-4B, Pnevka/Chroma-4B |
| **History** | paper arXiv 2601.11141 (2026-01) |

**Features:** Two bets together produce the dual property that no prior
open-source spoken-dialogue model has hit simultaneously. First,
an **interleaved text-audio token schedule (1:2)** — text tokens
and audio tokens are interleaved at a fixed 1:2 ratio through the
sequence, which gives the model a structured place to emit audio
*while still consuming user audio + text context*, supporting
sub-second end-to-end latency without a separate ASR / LLM / TTS
pipeline. Second, **personalized voice cloning baked into the
spoke-dialogue model** — the cloned voice is not bolted on top by
a separate TTS stage (as is the default pattern), it's in-model
at the audio-token-generation layer. The empirical payoff is a
**10.96% relative speaker-similarity gain over the human
baseline** (i.e. the cloned voice is closer to the reference
speaker than two of the same human speaker's recordings are to
each other), while hitting RTF 0.43 — a floor that prior systems
exceeded either in *latency* (no streaming) or in *cloning
fidelity* (parrot the speaker poorly), rarely both.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/FlashLabs/Chroma-4B)
[![Paper][link-paper]](https://arxiv.org/abs/2601.11141)
[![Demo][link-demo]](https://huggingface.co/spaces/hysts/Chroma-4B)

</details>
<!-- /MODEL:chroma-4b.md -->
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
| [QuarkAudio-UniSE](#quarkaudio-unise) | Universal Speech Enhancement | ❌ | ❌ | ![Apache 2.0][license-apache-2.0] |
| [PASE](#pase) | Speech Enhancement | ❌ | ❌ | ![Apache 2.0][license-apache-2.0] |
| [DTT-BSR](#dtt-bsr) | Music Source Restoration | ❌ | ❌ | ![MIT][license-mit] |
| [NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)](#nvidia-a2sb) | High-Resolution Audio Restoration | ✅ | ✅ | ![NVIDIA NC][license-nvidia-noncommercial] |
| [ZipEnhancer](#zipenhancer) | Acoustic Noise Suppression | ❌ | ❌ | ![Apache 2.0][license-apache-2.0] |
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
<!-- MODEL:quarkaudio-unise.md -->
<details id="quarkaudio-unise">
<summary>QuarkAudio-UniSE</summary>

### QuarkAudio-UniSE

**Description:** **UniSE** is a unified, prompt-free autoregressive speech-enhancement framework built on a decoder-only language model. A single model performs multiple speech-enhancement tasks — speech restoration (SR / denoising), target-speaker extraction (TSE), source separation (SS), and acoustic echo cancellation (AEC, in development) — without explicit task-specific instructions or prompt conditioning; the language model infers the task from the input context. Stack: WavLM as the feature extractor, BiCodec as the discrete codec, and a decoder-only LM as the middle autoregressive backbone. Outputs reconstructed waveform from predicted discrete token sequences.

**Release Date:** December 22, 2025

| Feature | Value |
|---------|-------|
| **Voice Cloning** | ❌ |
| **Asr** | ❌ |
| **Streaming** | ❌ |
| **Languages** | English (paper demo) |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Tasks** | Speech Restoration, Target Speaker Extraction, Source Separation, AEC (developing) |
| **Architecture** | WavLM (feature extractor) + BiCodec (discrete codec) + decoder-only AR-LM |
| **Unified** | yes (single model handles SE, SR, TSE, SS without explicit task prompts) |
| **Prompt Free** | yes (LM infers task from input context) |
| **Dataset Signals** | noise + reverb + packet-loss + clean (configurable per task) |
| **Training** | Speech-enhancement SFT, then multitask joint training |

**Features:** A single decoder-only LM that learns the speech-enhancement task
distribution and **infers which task to perform from the input
context** — eliminating the need for task-specific prompts, modules,
or fine-tuning when switching between denoising, target-speaker
extraction, and separation. Built as an autoregressive discrete-token
predictor over a WavLM-extracted / BiCodec-quantised representation,
it moves the speech-enhancement workflow from a zoo of specialist
models into one generalist.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/QuarkAudio/QuarkAudio-UniSE)
[![GitHub][link-github]](https://github.com/alibaba/unified-audio/tree/main/QuarkAudio-UniSE)
[![Paper][link-paper]](https://arxiv.org/abs/2510.20441)

</details>
<!-- /MODEL:quarkaudio-unise.md -->
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
<!-- MODEL:zipenhancer.md -->
<details id="zipenhancer">
<summary>ZipEnhancer</summary>

### ZipEnhancer

**Description:** **ZipEnhancer** (`speech_zipenhancer_ans_multiloss_16k_base`) is Alibaba DAMO Academy's next-generation **single-channel speech intelligent denoising** model. It is a 16 kHz-in → 16 kHz-out acoustic-noise-suppression (ANS) system that:

**Release Date:** October 12, 2024

| Feature | Value |
|---------|-------|
| **Type** | Acoustic Noise Suppression / Speech Enhancement (single-channel denoising) |
| **Bandwidth Extension** | ❌ |
| **Inpainting** | ❌ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Model Type** | dual-path (per ModelScope metadata) |
| **Training Objective** | multi-loss (per model id `..._multiloss_...`) |
| **Input Sample Rate** | 16,000 Hz |
| **Output Sample Rate** | 16,000 Hz |
| **Channels** | single-channel (mono) |
| **Task** | acoustic-noise-suppression (ANS) |
| **Use Cases** | denoise any audio source; improve acoustic quality; vocal extraction from background |
| **Host Org** | Alibaba DAMO Academy (iic on ModelScope) |
| **Ecosystem** | ModelScope; Hugging Face Spaces not hosted on HF, demo available through ModelScope's widget |
| **Release Date Evidence** | ModelScope CreatedTime = unix 1728713079 = 2024-10-12 06:04 UTC |

**Features:** Alibaba's ZipEnhancer is among the few open **single-channel speech
denoising** models that ships both an explicit **dual-path
architecture** and a published **multi-loss training objective** at
the 16 kHz single-channel baseline. The dual-path split — a common
modern architectural pattern in speech enhancement — separates
the model's processing path for short-time-frame local acoustic
features from its longer-context path, which lets the system keep
a sharp response to sudden transient noise while still modeling
the slow envelope of stationary backgrounds. Combined with the
multi-loss objective (the model id suffix `_multiloss` indicates
multiple supervision signals during training, e.g. spectral /
waveform / perceptual losses), the result is one of the few openly
hosted ANS checkpoints that handles **arbitrary-source audio
quality improvement**, not just narrow-band microphone cleanup —
the documented use case extends to vocal extraction from full
mixes, which most ANS-only pipelines can't do without a separate
source-separation model.

**Links:**
[![ModelScope][link-modelscope]](https://modelscope.cn/models/iic/speech_zipenhancer_ans_multiloss_16k_base)

</details>
<!-- /MODEL:zipenhancer.md -->
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
| [GigaAM-Multilingual](#gigaam-multilingual) | 70+ | ❌ | ![MIT][license-mit] |
| [GigaChat3.1-Audio](#gigachat3-audio) | Russian, English | ❌ | ![MIT][license-mit] |
| [MOSS-Transcribe-Diarize](#moss-transcribe-diarize) | Multilingual | ✅ | ![Apache 2.0][license-apache-2.0] |
| [Mega-ASR](#mega-asr) | English, Chinese | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Cohere Transcribe](#cohere-transcribe) | 14 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [VibeVoice-ASR](#vibevoice-asr) | 50+ | ✅ | ![MIT][license-mit] |
| [SYMPHONY-ASR](#symphony-asr) | English, Korean | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Fun-ASR](#fun-asr) | 31 | ✅ | ![Apache 2.0][license-apache-2.0] |
| [GLM-ASR-Nano-2512](#glm-asr-nano) | 17 | ❌ | ![MIT][license-mit] |
| [SYMPHONY](#symphony) | English, Korean | ❌ | ![Apache 2.0][license-apache-2.0] |
| [Moonshine](#moonshine) | English | ❌ | ![MIT][license-mit] |
| [SenseVoice](#sensevoice) | Multilingual | ✅ | ![Unknown][license-unknown] |
| [FunASR](#funasr) | 50+ | ✅ | ![MIT][license-mit] |

<!-- MODEL:gigaam-multilingual.md -->
<details id="gigaam-multilingual">
<summary>GigaAM-Multilingual</summary>

### GigaAM-Multilingual

**Description:** **GigaAM Multilingual** is a family of Conformer-based ASR foundation models from ai-sage (Sber). Two parameter scales ship (`ssl` / `ctc` at 220M and `large_ssl` / `large_ctc` at 600M). The encoder is pretrained with a HuBERT-style self-supervised objective on **2M hours** of speech across **70+ languages**, then fine-tuned for speech recognition with character-wise CTC decoders on 50K hours. The `ssl`/`large_ssl` variants are encoder-only checkpoints for downstream fine-tuning; the `ctc`/`large_ctc` variants add a character-wise CTC decoder ready for inference. The model reports best-in-class open-source quality on Russian, Kazakh, Kyrgyz, and Uzbek ASR, and moderate quality on English — beating Seamless M4T large v2 and Omnilingual 1B on Russian Common Voice (7.1%/5.1% WER vs 9.2%/13.6%). A live demo Space is hosted at [hugging-apps/gigaam-multilingual-asr](https://huggingface.co/spaces/hugging-apps/gigaam-multilingual-asr).

**Release Date:** July 14, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 220M (`ssl` / `ctc`); 600M (`large_ssl` / `large_ctc`) |
| **Asr** | ✅ |
| **Languages** | 70+ pretrained, fine-tuned for ru / en / kk / ky / uz |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |
| **Architecture** | Conformer encoder + (optional) character-wise CTC decoder |
| **Pretraining Objective** | HuBERT-style self-supervised |
| **Pretraining Hours** | 2,000,000 hours |
| **Fine Tuning Hours** | 50,000 hours |
| **Variants** | ssl (encoder-only), ctc (encoder + CTC decoder), large_ssl (600M encoder-only), large_ctc (600M + CTC decoder) |
| **Evaluation Cv Russian** | WER 7.1% (220M) / 5.1% (600M) |
| **Evaluation Cv Kazakh** | best-in-class (see paper) |
| **Evaluation Fleurs English** | WER 12.2% (220M) / 9.4% (600M) |
| **Training Library** | pytorch, custom_code |

**Features:** Two things set GigaAM-Multilingual apart from prior multilingual
ASR foundation work. First, the scale of pretraining — **2M hours
across 70+ languages** under a HuBERT-style self-supervised
objective — paired with a *character-wise* CTC decoder fine-tune
(no word-piece lexicon dependency) lets a single checkpoint cover
languages with very different phonotactics and orthographies
(Turkic + Slavic + Indo-Aryan families) without a language-tagged
decoding head per family. Second, the **two-tier release** — encoder-only
(`ssl`/`large_ssl`) for downstream fine-tuning and encoder+CTC
(`ctc`/`large_ctc`) ready for inference — gives the community both
a drop-in recognizer and a foundation for task-specific adaptation.
On Russian Common Voice it beats Seamless M4T large v2 and
Omnilingual 1B, the closest open baselines.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/ai-sage/GigaAM-Multilingual)
[![Paper][link-paper]](https://arxiv.org/abs/2607.10371)
[![Demo][link-demo]](https://huggingface.co/spaces/hugging-apps/gigaam-multilingual-asr)

</details>
<!-- /MODEL:gigaam-multilingual.md -->
<!-- MODEL:gigachat3-audio.md -->
<details id="gigachat3-audio">
<summary>GigaChat3.1-Audio</summary>

### GigaChat3.1-Audio

**Description:** `GigaChat Audio 10B` is an audio-native LLM built on top of the GigaChat 3.1 Lightning text model (10B total parameters, A1.8B active). A Conformer speech encoder and a modality adapter feed audio embeddings directly into the existing Mixture-of-Experts decoder, so the model retains the text quality of its base while adding speech understanding. Capabilities include audio question answering and classification, **temporal grounding** (event localization in long audio with timestamped descriptions and timestamped audio summarization), emotion recognition (Dusha benchmarks), tool-use, and text-only tasks. The temporal-grounding skills are trained on the purpose-built [TimeGround-1M](https://huggingface.co/datasets/ai-sage/TimeGround-1M) dataset of long-form audio paired with time-aligned annotations. On Russian ASR (Golos crowd), the model reports WER ≈14.7 versus Whisper-large-v3 ≈9.1; on temporal localization it scores mIoU 40.3 / 48.3 on ≤10min / 20–60min clips — substantially above Voxtral (3B) and Phi-4 (4B). Multiple HF Spaces (e.g. `hugging-apps/gigaam-multilingual-asr`) host live demos of the related GigaAM-Multilingual family.

**Release Date:** July 13, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 10B total (A1.8B active, MoE) |
| **Asr** | ✅ |
| **Languages** | Russian, English |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |
| **Architecture** | audio-native MoE LLM — Conformer speech encoder + modality adapter + MoE decoder |
| **Base Model** | ai-sage/GigaChat3.1-10B-A1.8B (GigaChat 3.1 Lightning text model) |
| **Capabilities** | audio QA, classification, temporal grounding, emotion recognition, speech translation, tool-use, text-only |
| **Temporal Grounding** | yes (timestamped event localization in long audio) |
| **Training Data Audio Grounding** | ai-sage/TimeGround-1M (1M long-form audio + time-aligned annotations) |
| **Evaluation Mmau** | 62.2 (vs Voxtral 3B 59.8, Phi-4 4B 68.3) |
| **Evaluation Mmlu Speech** | 50.3 |
| **Evaluation Audio Math Mqa** | 72.5 |
| **Evaluation Emotion Dusha Crowd** | 90.0 acc |
| **Evaluation Emotion Dusha Podcast** | 92.4 acc |
| **Evaluation Asr Ru Golos** | WER 14.7 |
| **Evaluation Temporal Localization 10M** | mIoU 40.3 |
| **Evaluation Temporal Localization 20 60M** | mIoU 48.3 |

**Features:** Two things make GigaChat3.1-Audio stand out among audio LLMs.
First, **modality-injection into an existing MoE**: rather than
training a smaller speech-text model from scratch, it taps a
10B-A1.8B MoE text LLM (GigaChat 3.1 Lightning) by inserting a
Conformer encoder + linear adapter that project audio embeddings
into the existing decoder sequence — so text quality is inherited
rather than re-learned. Second, **timestamped temporal grounding
on long audio**: trained on the TimeGround-1M dataset, the model
produces event-localization mIoU scores (40.3 / 48.3 on ≤10min /
20–60min clips) that are an order of magnitude above comparable
open models (Voxtral 3B 3.4 mIoU on ≤10min; 0.1 on 20–60min), and
its audio-summarization output is timestamped rather than just a
flat transcript.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/ai-sage/GigaChat3.1-Audio-10B-A1.8B)
[![Paper][link-paper]](https://arxiv.org/abs/2607.10387)
[![Demo][link-demo]](https://huggingface.co/spaces/hugging-apps/gigaam-multilingual-asr)

</details>
<!-- /MODEL:gigachat3-audio.md -->
<!-- MODEL:moss-transcribe-diarize.md -->
<details id="moss-transcribe-diarize">
<summary>MOSS-Transcribe-Diarize</summary>

### MOSS-Transcribe-Diarize

**Description:** **MOSS-Transcribe-Diarize 0.9B** is OpenMOSS's open-source SOTA end-to-end audio-understanding model for long-form multi-speaker transcription. Instead of stitching a separate ASR and diarization system, the model **jointly** transcribes speech and assigns speaker labels, producing time-aligned text with precise timestamps and consistent speaker tags such as `[S01]`, `[S02]` in a single pass. Built for meetings, calls, podcasts, interviews, lectures, and video content. Optional acoustic-event annotations extend the output to "[start][Sxx]text[end]" segments plus `[event]` tags for non-speech sounds. Architecture: Qwen3-style 0.6B text backbone + Whisper-Medium audio encoder (16 kHz, 80 mel bins, 30 s chunks) joined by a 4× temporal merge + MLP audio-text adaptor.

**Release Date:** July 9, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | 0.9B total |
| **Voice Cloning** | ❌ |
| **Asr** | ✅ |
| **Pronunciation** | ✅ |
| **Emotion Control** | ❌ |
| **Languages** | Multilingual (model card: long-form speech unspecified languages; English demo) |
| **Streaming** | ✅ |
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Output Format** | "[start_seconds][Sxx]text[end_seconds]" segments |
| **Diarization** | built-in ([S01], [S02], ...) |
| **Acoustic Event Tags** | yes (optional) |
| **Text Backbone** | Qwen3-0.6B causal decoder |
| **Audio Encoder** | Whisper-Medium, 16 kHz, 80 mel bins, 30 s chunks |
| **Audio Text Bridge** | 4× temporal merge + MLP adaptor |
| **Inference** | vLLM, SGLang Omni, transformers, HF inference API |

**Features:** **Joint** speech transcription + speaker diarization in a **single
end-to-end checkpoint** with the canonical `[Sxx]` output format
embedded in the transcript. Most production pipelines stitch a
separate ASR model to a separate diarization model (and reconcile
speaker turns post-hoc) — MOSS-Transcribe-Diarize folds them into
one model so the timestamps, speaker labels, and event tags come out
of the same forward pass. Adding a Qwen3-style text decoder on top
of Whisper-Medium audio features lets the model explicitly reason
about speaker continuity in the textual stream rather than as a
postprocess.

**Links:**
[![GitHub][link-github]](https://github.com/OpenMOSS/MOSS-Transcribe-Diarize)
[![HuggingFace][link-huggingface]](https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize)
[![Paper][link-paper]](https://arxiv.org/abs/2601.01554)

</details>
<!-- /MODEL:moss-transcribe-diarize.md -->
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
<!-- MODEL:glm-asr-nano.md -->
<details id="glm-asr-nano">
<summary>GLM-ASR-Nano-2512</summary>

### GLM-ASR-Nano-2512

**Description:** **GLM-ASR-Nano-2512** is a 1.5B-parameter open-source speech recognition model from Zhipu AI. The "Nano" model is built for real-world complexity: it produces the **lowest average error rate (4.10)** among comparable open-source ASR models while keeping the checkpoint at the compact 1.5B scale. Key capabilities:

**Release Date:** December 9, 2025

| Feature | Value |
|---------|-------|
| **Parameters** | 1.5B |
| **Asr** | ✅ |
| **Languages** | 17 supported (WER ≤ 20%); Mandarin, English, Cantonese specially optimized |
| **Streaming** | ❌ |
| **License** | ![MIT][license-mit] |
| **Architecture** | speech-encoder + text decoder (transformers framework) |
| **Wer Avg** | 4.10 (lowest among comparable open-source ASR) |
| **Benchmarks** | Wenet Meeting (real-world meeting scenarios, noise / overlapping speech); Aishell-1 (Mandarin) |
| **Licensed Channels** | Hugging Face, ModelScope |
| **Companion Repo** | https://github.com/zai-org/GLM-ASR |
| **Inference Lib** | transformers (v4.x from source; v5 support planned; vLLM, SGLang planned) |
| **Input Modes** | audio URL (via processor.apply_transcription_request) or raw audio arrays |
| **Download Count** | ~150k (as of mid-2026) |
| **Model Class** | GlmAsrForConditionalGeneration (custom_code) / AutoModelForSeq2SeqLM |
| **Demo Spaces** | YatharthS/GLM-ASR-Nano, Pevernow/GLM-ASR-Nano, yakoudev/GLM-ASR-Nano, naicoi/GLM-ASR-Nano |

**Features:** Two design decisions set GLM-ASR-Nano apart from the Whisper-V3
class of multilingual ASR. First, **explicit dialect-support
training**: rather than treating dialectal Mandarin as noise to be
suppressed, the model was tuned for Cantonese and other regional
variants as first-class targets — a capability gap that most prior
ASR systems left untouched. Second, **specifically trained
robustness on low-volume / quiet-speech audio** — the regime where
conventional ASR often falls back on aggressive denoising that
removes the very signal the model needs. The result: the lowest
average error rate (4.10) among comparable open-source ASR models,
with the strongest advantage on Chinese benchmarks (Wenet Meeting,
Aishell-1) — in a 1.5B-parameter checkpoint that integrates
directly with the `transformers` v4.x / v5.x stack.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/zai-org/GLM-ASR-Nano-2512)
[![GitHub][link-github]](https://github.com/zai-org/GLM-ASR)
[![Demo][link-demo]](https://huggingface.co/spaces/YatharthS/GLM-ASR-Nano)

</details>
<!-- /MODEL:glm-asr-nano.md -->
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
| [DSA-Tokenizer](#dsa-tokenizer) | Disentangled Semantic-Acoustic Speech Tokenizer | 24 kHz | — | Audio | ![MIT][license-mit] |
| [KVAE-Audio](#kvae-audio) | Audio VAE | 48 kHz | 64 | Speech, Music, Sound | ![MIT][license-mit] |
| [LinaCodec](#linacodec) | Single-Stream Neural Audio Codec | 48 kHz | — | Audio | ![Unknown][license-unknown] |
| [QuarkAudio-HCodec](#quarkaudio-hcodec) | Dual-Stream Discrete Audio Codec | 16/48 kHz | - | Audio | ![Apache 2.0][license-apache-2.0] |

<!-- MODEL:dsa-tokenizer.md -->
<details id="dsa-tokenizer">
<summary>DSA-Tokenizer</summary>

### DSA-Tokenizer

**Description:** **DSA-Tokenizer** is a speech tokenizer that **explicitly disentangles semantic and acoustic speech information into independent discrete token streams**, designed as a building block for fully discrete Speech LLMs. The two token kinds are supervised with **distinct optimization constraints**: **semantic tokens** are trained to low WER/CER under ASR supervision (capturing linguistic content only), while **acoustic tokens** are trained to reconstruct mel-spectrograms (capturing speaker style / prosody / acoustic texture). The decoder is a **hierarchical Flow Matching** DiT trained with two strategies — **self-reconstruction** (predict the velocity field of the full mel-spectrogram from complete acoustic + semantic tokens) and **recombination / contextual inpainting** (predict the masked mel-spectrogram region given the unmasked acoustic context + the full semantic tokens). The DiT is **distilled to 4-step inference** and **fine-tuned with GAN** for synthesis quality, while supporting **cross-utterance voice clone** through the disentangled token streams.

**Release Date:** July 21, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | not stated (hierarchy of encoders + DiT decoder + vocoder) |
| **Type** | Disentangled Semantic-Acoustic Speech Tokenizer (dual-stream codec) |
| **Sample Rate** | 24,000 Hz (vocoder: flow2gan_mel_24k_base_50Hz) |
| **Latent Dim** | discrete semantic tokens + discrete acoustic tokens (separate codebooks; vocab.txt ships) |
| **Token Rate** | 50 Hz (mel2gan vocoder) |
| **Modalities** | Audio |
| **License** | ![MIT][license-mit] |
| **Architecture** | Two-stream encoder (semantic + acoustic branches) → hierarchical Flow Matching DiT decoder → GAN-fine-tuned vocoder (flow2gan_mel_24k_base_50Hz) |
| **Semantic Supervision** | ASR loss (low WER/CER) |
| **Acoustic Supervision** | mel-spectrogram reconstruction loss |
| **Decoder Optimisation** | Flow Matching + 4-step distillation + GAN fine-tuning |
| **Training Strategies** | self-reconstruction + recombination / contextual inpainting (joint) |
| **Inference Steps** | 4 (distilled) |
| **Inference Pattern** | `from f5_tts.dsa_api import DSATokenizer; DSATokenizer.from_pretrained('DiscreteSpeech/dsa-tokenizer', device='cuda:0')` |
| **Downstream Tasks Supported** | SpeechLLM-TTS (e.g. Llasa 1B/3B/8B, Spark-TTS), SpeechLLM-VC, speech reconstruction, voice clone across utterances |
| **Disentanglement Quality** | outperforms WavTokenizer/Mimi/Encodec/SpeechTokenizer/DualCodec/SAC on disentanglement probing (low WER + low speaker similarity on semantic; high WER + high speaker similarity on acoustic) |
| **Bundle Files** | `dsa_tokenizer/model_10000.pt`, `dsa_tokenizer/vocab.txt`, `dsa_tokenizer/config.yaml`; vocoder `flow2gan_mel_24k_base_50hz/epoch-20.pt` |
| **Pipeline Tag** | text-to-speech (the canonical use is LLM-TTS); tags include voice-cloning, tokenizer, speech |
| **Library** | zips under `f5_tts.dsa_api` integration |
| **Demo Url Format** | anonymous.4open.science uses `/w/.../index.html` (root URL returns 400 folder_not_supported; index.html works) |
| **Downloads** | 0 (released July 21 2026) |

**Features:** Two bets together are the technical center of DSA-Tokenizer. The
first is **explicit semantic-acoustic disentanglement via distinct
optimization constraints**: rather than training a single
representational bottleneck and hoping semantic and acoustic
content separate (as prior fusing tokenizers do), DSA trains
semantic tokens against ASR supervision and acoustic tokens against
mel reconstruction as separate streams — so the disentanglement is
*engineered into the loss surface*, not extracted post-hoc. The
second is a **hierarchical Flow Matching decoder with joint
self-reconstruction + contextual-inpainting training**, which lets
the same decoder both reconstruct complete utterances and **inpaint
missing regions using surrounding acoustic context** (the
characteristic operation needed for voice conversion / segment
editing). Coupled with **4-step distillation** and **GAN
fine-tuning** for inference speed and audio quality, the result is
a single tokenizer that supports high-fidelity speech reconstruction
*and* cross-utterance voice clone *and* LLM-TTS (paired with Llasa
8B, Spark-TTS, etc.) — and on the project's disentanglement
probing beats WavTokenizer / Mimi / Encodec / SpeechTokenizer /
DualCodec / SAC at producing a *truly* separable semantic /
acoustic representation.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/DiscreteSpeech/dsa-tokenizer)
[![Paper][link-paper]](https://arxiv.org/abs/2601.09239)
[![Demo][link-demo]](https://anonymous.4open.science/w/DSA_Tokenizer_demo/)

</details>
<!-- /MODEL:dsa-tokenizer.md -->
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
<!-- MODEL:linacodec.md -->
<details id="linacodec">
<summary>LinaCodec</summary>

### LinaCodec

**Description:** **LinaCodec** is a highly-compressive neural audio tokenizer designed for speech models. Audio is compressed to **just 12.5 tokens per second (171 bps)** and decoded back to **48 kHz** waveforms — roughly **60× more compressed than DAC** (774 tokens/sec, 44.1 kHz), **24× more than EnCodec** (300 tokens/sec, 24 kHz), **4× more than Xcodec2** (50 tokens/sec, 16 kHz), and **16× more than Mimi** (200 tokens/sec, 24 kHz). The encoder runs at **200× real-time**; the decoder at **400× real-time** (faster with batching). Although this is a tokenizer rather than a synthesis model, it supports indirect downstream tasks like voice conversion, audio super-resolution, and audio denoising. Designed for direct drop-in use as the audio tokenizer of TTS/ASR pipelines — reported use case is enabling TTS models to run at **800× real-time, ~8× faster than the same author's MiraTTS**, and faster training (high-quality TTS in < 1 day).

**Release Date:** January 2, 2026

| Feature | Value |
|---------|-------|
| **Parameters** | not stated (encoder + decoder transformer pair) |
| **License** | ![Unknown][license-unknown] |
| **Type** | Neural audio codec (single-stream discrete tokenizer) |
| **Sample Rate** | 48,000 Hz |
| **Latent Dim** | — (token-stream tokenizer; discrete codebook rather than continuous latent) |
| **Modalities** | Audio |
| **Tokens Per Second** | 12.5 (171 bps) |
| **Compression Vs Dac** | ~60× tighter (vs DAC 774 tokens/s @ 44.1 kHz) |
| **Compression Vs Encodec** | ~24× tighter (vs EnCodec 300 tokens/s @ 24 kHz) |
| **Compression Vs Xcodec2** | ~4× tighter (vs Xcodec2 50 tokens/s @ 16 kHz) |
| **Compression Vs Mimi** | ~16× tighter (vs Mimi 200 tokens/s @ 24 kHz) |
| **Encoder Speed** | 200× real-time |
| **Decoder Speed** | 400× real-time (faster with batching) |
| **Downstream Tasks** | TTS, ASR, voice conversion (indirect), audio super-resolution (indirect), audio denoising (indirect) |
| **Inference Install** | `pip install git+https://github.com/ysharma3501/LinaCodec.git` |
| **Usage Inference** | `from linacodec.codec import LinaCodec` |
| **Author Other Work** | MiraTTS (https://github.com/ysharma3501) |
| **Inference Speed Claim** | enables TTS at 800× real-time (~8× faster than MiraTTS) |
| **Training Speed Claim** | high-quality TTS in < 1 day |
| **Variants** | single 48 kHz checkpoint at HF |

**Features:** The architectural decision that drives LinaCodec's pitch is the
**12.5 tokens-per-second target rate**. That number sits
substantially below every comparable neural audio codec
(Xcodec2 50, Mimi 200, EnCodec 300, DAC 774) — an order-of-magnitude
compression jump relative to EnCodec / DAC and ~4× tighter than
the previous state-of-the-art at the time of release. The pragmatic
consequence for TTS pipelines is that the **sequence length the
LLM decoder has to traverse is proportionally shorter**, so
attention cost collapses quadratically, and the same TTS backbone
sped up by 8× vs the author's MiraTTS hit "~800× real-time"
with the codec swap. The "codec isn't a TTS model" caveat matters:
LinaCodec shows up here as a **drop-in tokenizer for TTS / ASR
pipelines**, not a dialogue or voice-synthesis model itself —
the comparison-table columns reflect it isn't measuring the same
thing as the TTS rows above.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/YatharthS/LinaCodec)
[![GitHub][link-github]](https://github.com/ysharma3501/LinaCodec)

</details>
<!-- /MODEL:linacodec.md -->
<!-- MODEL:quarkaudio-hcodec.md -->
<details id="quarkaudio-hcodec">
<summary>QuarkAudio-HCodec</summary>

### QuarkAudio-HCodec

**Description:** **H-Codec** is a unified, dual-stream discrete audio tokenizer that quantizes acoustic and semantic features into **independent codebooks**, preserving both signal fidelity and linguistic content separately. Three versions release alongside the paper:

**Release Date:** December 23, 2025

| Feature | Value |
|---------|-------|
| **License** | ![Apache 2.0][license-apache-2.0] |
| **Modalities** | audio |
| **Zero Shot Voice** | no (tokenizer, not a synthesis model) |
| **Architectures** | Acoustic quantizer + Semantic quantizer (separate codebooks) |
| **Inference** | encoder → 2× quantizers → discrete tokens; decoder reconstructs waveform |
| **Variants** | 1.0 (16 kHz fixed), 1.5 (16 kHz adaptive), 2.0 (48 kHz fixed) |
| **Frame Rate** | Fixed (1.0, 2.0); Adaptive (1.5) |
| **Sample Rate** | 16 kHz (1.0, 1.5); 48 kHz (2.0) |
| **Ssl Backbone** | WavLM (used as encoder for semantic stream) |
| **Downstream** | TTS, VC, audio editing, TTA, SE |

**Features:** A **dual-stream neural audio codec** with separate codebooks for
acoustic and semantic quantization — instead of fusing the two before
discretizing. This separation lets the acoustic codebook preserve
high-frequency detail while the semantic codebook retains
linguistic content for downstream LLM-conditioned generation. The
adaptive-frame-rate variant (1.5) further reduces token count on
temporally simple content, lowering LLM training and inference cost.

**Links:**
[![HuggingFace][link-huggingface]](https://huggingface.co/QuarkAudio/QuarkAudio-HCodec)
[![GitHub][link-github]](https://github.com/alibaba/unified-audio/tree/main/QuarkAudio-HCodec/HCodec/)
[![Paper][link-paper]](https://arxiv.org/pdf/2512.20151)

</details>
<!-- /MODEL:quarkaudio-hcodec.md -->

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

- [🤗 Open ASR Leaderboard](https://huggingface.co/spaces/hf-audio/open_asr_leaderboard) · [Paper (arXiv 2510.06961)](https://arxiv.org/abs/2510.06961) — Hugging Face community benchmark ranking open and proprietary ASR models by average WER and RTFx across English and multilingual datasets.
- [Artificial Analysis — Speech-to-Text (Streaming) Leaderboard](https://artificialanalysis.ai/speech-to-text/streaming) — Compares streaming STT models and providers on the AA-WER Streaming index, latency, and pricing.
- [FFASR Leaderboard (Treble Technologies)](https://huggingface.co/spaces/treble-technologies/ffasr) — Far-field ASR multi-condition benchmark reporting WER and RTFx across noisy, reverberant, and SNR-stratified scenarios (measured & simulated RIRs).

### Voice Cloning & Speaker Privacy

- [RVCBench](https://github.com/Nanboy-Ronan/RVCBench) · [Paper (arXiv 2602.00443)](https://arxiv.org/abs/2602.00443) · [Dataset](https://huggingface.co/datasets/Nanboy/RVCBench) · [Demo](https://huggingface.co/spaces/Nanboy/RVCBench) — First large-scale robustness benchmark for voice cloning + speaker privacy: 27 TTS/VC adversary models, 10 dataset configurations, 5 audio protection methods, with standardised speaker-similarity, intelligibility, and perceptual-quality metrics.

---

## Contributing

This list is continuously evolving. If you have any models to add or updates to suggest, please feel free to contribute! See [CONTRIBUTING.md](./CONTRIBUTING.md) for the template-driven workflow.

---

*Last Updated: July 2026*

<!-- MARKDOWN LINKS & IMAGES -->
[license-mit]: https://img.shields.io/badge/MIT-green?style=flat-square&logo=openldap "MIT"
[license-apache-2.0]: https://img.shields.io/badge/Apache_2.0-green?style=flat-square&logo=apache "Apache 2.0"
[license-unknown]: https://img.shields.io/badge/Unknown-lightgrey?style=flat-square "Unknown"
[license-research-only]: https://img.shields.io/badge/Research_Only-orange?style=flat-square "Research Only"
[license-cc-by-nc-4.0]: https://img.shields.io/badge/CC_BY--NC_4.0-orange?style=flat-square&logo=creativecommons "CC BY-NC 4.0"
[license-openrail-m]: https://img.shields.io/badge/OpenRAIL--M-blueviolet?style=flat-square "OpenRAIL-M"
[license-lfm]: https://img.shields.io/badge/LFM-blue?style=flat-square "LFM"
[license-nvidia-noncommercial]: https://img.shields.io/badge/NVIDIA_NC-yellow?style=flat-square&logo=nvidia "NVIDIA NC"

[link-blog]: https://img.shields.io/badge/Blog-post-blue?style=flat-square "Blog post"
[link-collection]: https://img.shields.io/badge/Collection-darkblue?style=flat-square "Collection"
[link-demo]: https://img.shields.io/badge/Demo-live-blue?style=flat-square "Demo live"
[link-github]: https://img.shields.io/badge/GitHub-code-black?style=flat-square&logo=github "GitHub code"
[link-huggingface]: https://img.shields.io/badge/HuggingFace-models-yellow?style=flat-square&logo=huggingface "HuggingFace models"
[link-modelscope]: https://img.shields.io/badge/ModelScope-orange?style=flat-square "ModelScope"
[link-paper]: https://img.shields.io/badge/Paper-red?style=flat-square "Paper"
[link-pypi]: https://img.shields.io/badge/PyPI-package-blueviolet?style=flat-square&logo=pypi "PyPI package"
[link-skill]: https://img.shields.io/badge/Skill-lightgrey?style=flat-square&logo=puzzle "Skill"
[link-website]: https://img.shields.io/badge/Website-blue?style=flat-square "Website"
[link-arxiv]: https://img.shields.io/badge/arXiv-paper-red?style=flat-square&logo=arXiv "arXiv paper"
