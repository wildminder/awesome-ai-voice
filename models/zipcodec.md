---
release_date: "September 11, 2026"
model_name: "ZipCodec"
category: "audio_codecs"
summary: "Luca Della Libera, Cem Subakan & Mirco Ravanelli — ZipCodec: an ultra-low-frame-rate streaming neural speech codec at 6.25 Hz and 0.80 kbit/s, built from large-scale WavLM distillation with a scalar spherical quantizer and a latency-aware streaming decoder; 842M parameters yet real-time single-stream inference on a consumer-grade CPU."
slug: "zipcodec"
---

# ZipCodec

**ZipCodec** attacks the *frame rate* of neural speech coding rather than
only the bitrate. It runs at **6.25 Hz** — one token every **160 ms** —
at **0.80 kbit/s**, with a **theoretical latency of 160 ms**, by combining
large-scale **WavLM distillation** with a redesigned transformer-based
encoder/decoder, a **scalar spherical quantizer** (64 codebooks × 4 entries,
i.e. 2 bits per latent dimension) and a **latency-aware streaming decoder**.
The project page compares it head-to-head against EnCodec (1.50 kbps),
AudioDec (1.60 kbps), HILCodec (1.50 kbps), Mimi (0.83 kbps), PAST (1.00
kbps), FocalCodec-Stream (0.80 kbps) and FocalCodec (0.65 kbps) on speech
resynthesis and voice conversion, and the authors report it substantially
outperforms existing **streaming** codecs at comparable bitrates while
operating at a far lower frame rate. Despite **842M parameters**, it reaches
real-time single-stream inference on a consumer-grade CPU; ONNX, OpenVINO,
`torch.compile` and CUDA-graph backends ship as install extras.

## Links

- HuggingFace: https://huggingface.co/lucadellalib/zipcodec
- GitHub: https://github.com/lucadellalib/zipcodec
- arXiv: https://arxiv.org/abs/2609.11642
- Website: https://lucadellalib.github.io/zipcodec-web/
- Predecessor: https://github.com/lucadellalib/focalcodec

## Features

- parameters: 842M (842,154,100 F32 in the released checkpoint)
- license: Apache-2.0
- type: Streaming Neural Speech Codec (single-stream discrete tokenizer)
- sample_rate: 16,000 Hz
- latent_dim: 64 (scalar quantized; 64 codebooks × 4 entries = 2 bits per dimension)
- modalities: Audio
- frame_rate: 6.25 Hz (one frame per 160 ms)
- bitrate: 0.80 kbit/s
- theoretical_latency: 160 ms
- base_model: microsoft/wavlm-large (large-scale distillation)
- quantizer: scalar spherical quantizer (64 codebooks × 4 entries)
- decoder: latency-aware streaming decoder
- streaming: yes (single-stream)
- cpu_inference: real-time single-stream on a consumer-grade CPU despite 842M parameters
- tasks: speech resynthesis, voice conversion, streaming
- compared_against: EnCodec 1.50 kbps, AudioDec 1.60 kbps, HILCodec 1.50 kbps, Mimi 0.83 kbps, PAST 1.00 kbps, FocalCodec-Stream 0.80 kbps, FocalCodec 0.65 kbps
- related_work: FocalCodec (same author; 0.65 kbps, non-streaming)
- install: `pip install zipcodec` (extras: `zipcodec[onnx]`, `zipcodec[openvino]`, `zipcodec[streaming]`)
- usage: `torch.hub.load("lucadellalib/zipcodec", "zipcodec", config="lucadellalib/zipcodec", trust_repo=True)`
- api: `from zipcodec import ZipCodec` then `ZipCodec.from_pretrained("lucadellalib/zipcodec")`
- api_core: `codec.wav_to_toks(wav)` → `codec.toks_to_codes(toks)` → `codec.toks_to_wav(toks)`
- export_backends: eager, torch.compile, jit, CUDA graphs, ONNX, ONNX I/O binding, OpenVINO
- benchmark_default: five runs of 40.96 s with four CPU threads
- runtime_requirements: Python 3.10+, PyTorch, NumPy, safetensors, huggingface-hub
- training_data: not stated in the repository

## Comparison

- type: Streaming Neural Speech Codec
- sample_rate: 16 kHz
- latent_dim: 64
- modalities: Audio
- license: Apache-2.0

## Innovation

The central bet is that **frame rate, not bitrate, is the bottleneck** for
speech generation pipelines. At 6.25 Hz every token has to carry ~25× more
information than at a typical 50 Hz codec, which is why prior work treated
sub-10 Hz frame rates as a quality cliff. ZipCodec's arithmetic is unusually
legible: **64 scalar dimensions × 2 bits × 6.25 frames/s = 800 bit/s**, so
the 0.80 kbit/s headline is exactly what the quantizer geometry implies —
the compression is bought by making each latent dimension nearly binary
rather than by pruning the sequence. Two design choices do the heavy lifting
against the resulting reconstruction penalty: **large-scale WavLM
distillation** gives the encoder a strong, already-linguistic feature space
to compress into, and a **latency-aware streaming decoder** lets the decoder
exploit only causally available context, so the model is trained for the
streaming regime it will actually run in instead of being adapted to it.
The 842M parameter count is the counterintuitive part: rather than trading
size for latency, ZipCodec keeps a large distilled backbone and buys back
real-time CPU inference through backend engineering (ONNX / OpenVINO /
CUDA-graph exports are first-class in the repo). Like the other entries in
this category, ZipCodec is a **drop-in tokenizer** for TTS / ASR /
voice-conversion pipelines, not a synthesis model itself.
