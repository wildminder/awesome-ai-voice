---
release_date: "September 30, 2025"
model_name: "KaniTTS"
category: "tts"
summary: "nineninesix-ai — KaniTTS: a 370M-parameter two-stage TTS model (LFM-2 backbone LLM + neural audio codec) for English/German/Chinese/Korean/Arabic/Spanish; ~1 s to generate 15 s of audio on a single RTX 5080 with 2 GB VRAM and MOS 4.3 / WER <5%; ships MLX variants for Apple Silicon."
slug: "kani-tts"
---

# KaniTTS

**KaniTTS** is a 370M-parameter two-stage text-to-speech model
from nineninesix-ai. The architecture pairs an **LFM-2 backbone
LLM** (Liquid Foundation Model v2 — a non-transformer, structured
state-space architecture) with a **neural audio codec** for
output waveform synthesis. The LLM generates compressed audio-token
representations and the codec renders them to 22 kHz waveforms,
yielding low-latency generation: **~1 s to produce 15 s of audio
on a single RTX 5080**, with **2 GB GPU VRAM** at inference, and
**MOS 4.3 / WER < 5%** quality on the project's benchmarks.
Languages covered: **English, German, Chinese, Korean, Arabic,
Spanish** across multiple per-language voices (English, German,
Chinese, Korean, Arabic, Spanish each ship a 400M checkpoint;
Japanese ships a 370M "Expo-2025-Osaka" variant; a multilingual
370M checkpoint is also available). MLX variants exist for
Apple-Silicon inference. The codec is the same author's
`nemo-nano-codec-22kHz-0.6kbps-12.5fps-MLX` (NVIDIA NeMo NanoCodec,
MLX-ported to ~12.5 fps / 0.6 kbps). The model is part of the
nineninesix-ai family alongside Gepard.

## Links

- HuggingFace: https://huggingface.co/nineninesix/kani-tts-370m
- GitHub: https://github.com/nineninesix-ai/kani-tts

## Features

- parameters: 370M (kani-tts-370m multilingual); 400M per-language (en / de / zh / ko / ar / es); 370M (expo2025-osaka-ja)
- voice_cloning: no (per-voice trained weights, not zero-shot)
- asr: no
- languages: English, German, Chinese, Korean, Arabic, Spanish (multilingual 370M checkpoint); Japanese (Expo-2025-Osaka variant)
- streaming: yes (low-latency two-stage generation; chunked output supported)
- license: LFM 1.0 (Liquid Foundation Model license, liquid.ai)
- sample_rate: 22,000 Hz
- backbone_llm: LFM-2 (Liquid Foundation Model; non-transformer structured state-space architecture)
- audio_codec: nineninesix/nemo-nano-codec-22khz-0.6kbps-12.5fps-MLX (NVIDIA NeMo NanoCodec, MLX-ported)
- performance_rt_5080: ~1 s for 15 s audio on RTX 5080
- memory: 2 GB GPU VRAM at inference
- quality_mos: 4.3 / 5 (naturalness)
- quality_wer: <5% (accuracy)
- training_dataset: ~80k hours (LibriTTS, Common Voice, Emilia)
- training_hardware: 8x H100 GPUs, 45 hours on Lambda AI
- per_language_models: kani-tts-400m-{en,zh,de,ar,es,ko} on HuggingFace
- pretrained_checkpoints: 0.2-pt (450M), 0.3-pt (400M) for custom posttraining / fine-tuning
- mlx_variants: kani-tts-370m-MLX (Apple Silicon)
- arxiv: 2505.20506

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: English, German, Chinese, Korean, Arabic, Spanish
- streaming: ✅
- license: LFM

## Innovation

KaniTTS's design choice worth flagging: it pairs a **non-transformer
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
