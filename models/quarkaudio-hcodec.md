---
release_date: "December 23, 2025"
model_name: "QuarkAudio-HCodec"
category: "audio_codecs"
summary: "Alibaba — unified discrete audio codec (dual-stream acoustic + semantic tokenization) with versions spanning 16 kHz fixed frame rate, 16 kHz adaptive frame rate, and 48 kHz full-bandwidth; foundation tokenizer for LLM-based audio generation."
slug: "quarkaudio-hcodec"
---

# QuarkAudio-HCodec

**H-Codec** is a unified, dual-stream discrete audio tokenizer that
quantizes acoustic and semantic features into **independent codebooks**,
preserving both signal fidelity and linguistic content separately.
Three versions release alongside the paper:

- **H-Codec-1.0** — dual-stream quantization at 16 kHz, fixed frame rate.
- **H-Codec-1.5** — adds adaptive temporal resolution atop 1.0: variable frame rates based on content complexity.
- **H-Codec-2.0** — extends sampling rate from 16 kHz to 48 kHz under a fixed frame rate, boosting high-frequency fidelity and reconstruction quality.

Unlike prior codecs that fuse modalities before quantization (e.g.
X-Codec), H-Codec uses separate codebooks for the acoustic and
semantic streams, allowing independent optimization and better
reconstruction quality. Designed as a foundational tokenizer for
LLM-based audio generation — supports TTS, voice conversion, audio
editing, text-to-audio, speech enhancement, and downstream LLM
training pipelines that consume discrete audio tokens.

## Links

- HuggingFace: https://huggingface.co/QuarkAudio/QuarkAudio-HCodec
- GitHub: https://github.com/alibaba/unified-audio/tree/main/QuarkAudio-HCodec/HCodec/
- Paper: https://arxiv.org/pdf/2512.20151

## Features

- license: Apache-2.0
- modalities: audio
- zero_shot_voice: no (tokenizer, not a synthesis model)
- architectures: Acoustic quantizer + Semantic quantizer (separate codebooks)
- inference: encoder → 2× quantizers → discrete tokens; decoder reconstructs waveform
- variants: 1.0 (16 kHz fixed), 1.5 (16 kHz adaptive), 2.0 (48 kHz fixed)
- frame_rate: Fixed (1.0, 2.0); Adaptive (1.5)
- sample_rate: 16 kHz (1.0, 1.5); 48 kHz (2.0)
- ssl_backbone: WavLM (used as encoder for semantic stream)
- downstream: TTS, VC, audio editing, TTA, SE

## Comparison

- type: Dual-Stream Discrete Audio Codec
- sample_rate: 16/48 kHz
- latent_dim: -
- modalities: Audio
- license: Apache-2.0

## Innovation

A **dual-stream neural audio codec** with separate codebooks for
acoustic and semantic quantization — instead of fusing the two before
discretizing. This separation lets the acoustic codebook preserve
high-frequency detail while the semantic codebook retains
linguistic content for downstream LLM-conditioned generation. The
adaptive-frame-rate variant (1.5) further reduces token count on
temporally simple content, lowering LLM training and inference cost.
