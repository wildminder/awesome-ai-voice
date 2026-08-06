---
release_date: "January 2, 2026"
model_name: "LinaCodec"
category: "audio_codecs"
summary: "Yatharth Sharma — LinaCodec: a highly-compressive neural audio tokenizer (12.5 tokens/sec, 171 bps, 48 kHz output) for speech models; encoder runs 200× real-time, decoder 400× real-time, scheduled for TTS-pipeline integration with a reported 8x speed-up over MiraTTS."
slug: "linacodec"
---

# LinaCodec

**LinaCodec** is a highly-compressive neural audio tokenizer designed
for speech models. Audio is compressed to **just 12.5 tokens per
second (171 bps)** and decoded back to **48 kHz** waveforms —
roughly **60× more compressed than DAC** (774 tokens/sec, 44.1 kHz),
**24× more than EnCodec** (300 tokens/sec, 24 kHz), **4× more than
Xcodec2** (50 tokens/sec, 16 kHz), and **16× more than Mimi** (200
tokens/sec, 24 kHz). The encoder runs at **200× real-time**;
the decoder at **400× real-time** (faster with batching). Although
this is a tokenizer rather than a synthesis model, it supports
indirect downstream tasks like voice conversion, audio
super-resolution, and audio denoising. Designed for direct drop-in
use as the audio tokenizer of TTS/ASR pipelines — reported use case
is enabling TTS models to run at **800× real-time, ~8× faster than
the same author's MiraTTS**, and faster training (high-quality TTS in
< 1 day).

## Links

- HuggingFace: https://huggingface.co/YatharthS/LinaCodec
- GitHub: https://github.com/ysharma3501/LinaCodec

## Features

- parameters: not stated (encoder + decoder transformer pair)
- license: not stated (GitHub repo has no LICENSE file as of mid-2026; SPDX NOASSERTION)
- type: Neural audio codec (single-stream discrete tokenizer)
- sample_rate: 48,000 Hz
- latent_dim: — (token-stream tokenizer; discrete codebook rather than continuous latent)
- modalities: Audio
- tokens_per_second: 12.5 (171 bps)
- compression_vs_dac: ~60× tighter (vs DAC 774 tokens/s @ 44.1 kHz)
- compression_vs_encodec: ~24× tighter (vs EnCodec 300 tokens/s @ 24 kHz)
- compression_vs_xcodec2: ~4× tighter (vs Xcodec2 50 tokens/s @ 16 kHz)
- compression_vs_mimi: ~16× tighter (vs Mimi 200 tokens/s @ 24 kHz)
- encoder_speed: 200× real-time
- decoder_speed: 400× real-time (faster with batching)
- downstream_tasks: TTS, ASR, voice conversion (indirect), audio super-resolution (indirect), audio denoising (indirect)
- inference_install: `pip install git+https://github.com/ysharma3501/LinaCodec.git`
- usage_inference: `from linacodec.codec import LinaCodec`
- author_other_work: MiraTTS (https://github.com/ysharma3501)
- inference_speed_claim: enables TTS at 800× real-time (~8× faster than MiraTTS)
- training_speed_claim: high-quality TTS in < 1 day
- variants: single 48 kHz checkpoint at HF

## Comparison

- type: Single-Stream Neural Audio Codec
- sample_rate: 48 kHz
- latent_dim: —
- modalities: Audio
- license: Unknown

## Innovation

The architectural decision that drives LinaCodec's pitch is the
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
