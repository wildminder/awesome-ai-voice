---
release_date: "August 25, 2026"
model_name: "Granite-Speech-5.0-470M-TurboCTC"
category: "asr"
summary: "IBM Granite Speech Team — a 470M encoder-only Conformer-CTC English ASR model built for raw inference speed: 8× temporal subsampling to a 12.5 Hz frame rate, block-diagonal attention, self-conditioned CTC and a Muon optimizer put it on the speed–accuracy Pareto frontier of the Open ASR leaderboard at 2× the speed of the fastest competitor, trained on ~60,000 hours of public audio only."
slug: "granite-speech-5-0-470m-turboctc"
---

# Granite-Speech-5.0-470M-TurboCTC

**Granite Speech 5.0 TurboCTC** is a compact **470 million parameter
English ASR model** whose explicit design target is the *speed* axis of the
speed–accuracy trade-off. It is an **encoder-only Conformer trained with
CTC** — no autoregressive decoder, no language-model head — and inference
is a single non-autoregressive pass with **greedy decoding**. The
architecture runs 16 Conformer blocks (hidden 1024, 8 heads × 128, conv
kernel 7) with **block-diagonal (chunk-wise) self-attention** over 128-frame
blocks, **self-conditioned CTC** (middle-layer predictions feed back as
conditioning), and a **16,384 BPE output head**. Aggressive **pyramidal
temporal subsampling** takes the frame rate from 100 Hz to **12.5 Hz**
(2× frame stacking/skipping, then 4× strided depthwise convolutions with
pooled residuals in the first two blocks). Training used **only public
data** — ~60,000 hours of English audio plus synthetic multi-speaker and
entity-rich subsets — with a **Muon optimizer** and balanced sampling, over
10 days on 8× H100. The result: on the speed–accuracy **Pareto frontier**
of the Open ASR leaderboard while being **twice as fast as the fastest
competitor**, with Apache-2.0 weights suited to laptops, smartphones and
other edge devices.

## Links

- HuggingFace: https://huggingface.co/ibm-granite/granite-speech-5.0-470m-turboctc
- arXiv: https://arxiv.org/abs/2609.20104
- Blog: https://huggingface.co/blog/ibm-granite/granite-speech-5-0-470m-turboctc
- GitHub: https://github.com/ibm-granite/granite-speech-models

## Features

- parameters: 473.0M (472,993,792 safetensors-measured; card rounds to 470M)
- languages: English only (en)
- streaming: no (single-pass non-autoregressive CTC; no streaming mode claimed)
- license: Apache-2.0
- architecture: encoder-only Conformer CTC — 16 blocks, hidden 1024, 8 attention heads × 128, conv kernel 7
- output_head: 16,384 BPE units
- input_dimension: 320 = (80 log-mels + 80 deltas) × 2
- temporal_subsampling: 8× (100 Hz → 12.5 Hz) via frame stacking/skipping (2×) then strided depthwise convolutions with pooled residuals in the first two Conformer blocks (4×)
- attention: block-diagonal (chunk-wise) self-attention, 128-frame blocks
- self_conditioning: CTC predictions from the middle layer feed back as conditioning
- training_data: ~60,000 hours of English audio, public corpora only
- training_breakdown: MLS 44,600 h; YODAS 8,900 h; CommonVoice-17 2,500 h; VoxPopuli 500 h; LibriSpeech 960 h; AMI 150 h; Earnings-22 100 h
- synthetic_data: 2,000 h multi-speaker concatenations (MLS/YODAS/CV-17/VoxPopuli/AMI); 500 h multi-speaker Earnings-22; 240 h numbers, currencies, URLs, phone numbers and addresses generated with gpt-oss-120b or gpt-oss-20b and synthesized with StyleTTS2
- optimizer: Muon (novel use for ASR training)
- sampling: balanced data sampling
- inference_speedups: 1×1 convolutions replaced with linear layers; optimized Conformer attention computation
- speed_claim: on the speed–accuracy Pareto frontier of the Open ASR leaderboard, 2× faster than the fastest competitor
- evaluations: Open ASR leaderboard (short-form English, RTFx on 1× H200) and FFASR leaderboard (noisy/reverberant speech, RTFx on 1× L4) — official results as of August 25, 2026
- deployment: transformers >= 5.16.0 native (`AutoModelForCTC`); mlx-audio >= 0.5.1 on Apple Silicon; transcribe.cpp GGUF (Q8_0) on Metal, Vulkan, CUDA, ROCm or CPU
- usage: `AutoProcessor` + `AutoModelForCTC`, then `model.generate(**inputs)` with greedy decoding
- training_compute: 10 days on 8× H100 (IBM Blue Vela)
- venue: technical report submitted to ICASSP 2027
- intended_use: enterprise low-latency / high-throughput English speech-to-text

## Comparison

- languages: English
- streaming: ❌
- license: Apache-2.0

## Additional Tools

| Tool | Type | Link |
|------|------|------|
| transcribe.cpp | GGUF inference engine (Metal, Vulkan, CUDA, ROCm, CPU) | https://github.com/handy-computer/transcribe.cpp |
| mlx-audio | Apple Silicon (MLX) runtime | https://github.com/Blaizzy/mlx-audio |

## Innovation

The contrarian move is deploying **plain CTC in 2026**, against a leaderboard
landscape dominated by LLM-based SpeechLLMs — and winning on the axis CTC
was always good at. An encoder-only model with greedy, fully parallel
decoding has no autoregressive token loop to pay for, and IBM then spends
the entire architecture budget making the encoder itself cheap: **8×
pyramidal subsampling to a 12.5 Hz frame rate** collapses the sequence the
encoder must traverse (the same low-frame-rate logic the audio-codec side of
this list converges on), **block-diagonal attention** caps quadratic cost at
chunk scale, **self-conditioned CTC** buys back accuracy lost to the small
output head, and inference-level micro-optimizations (1×1 convs → linear
layers, attention restructuring) squeeze the runtime further. Two quieter
choices matter for reproducibility: training on **public data only** (with
synthetic multi-speaker and entity-rich augmentation, including
StyleTTS2-synthesized numbers and addresses) makes the recipe auditable,
and the **first ASR use of the Muon optimizer** is a concrete, copyable
training contribution rather than a benchmark flex. The claim worth
remembering is calibrated honestly — not "best WER" but **on the Pareto
frontier while 2× faster than the fastest competitor**, which is the right
pitch for edge deployment where RTFx dominates.
