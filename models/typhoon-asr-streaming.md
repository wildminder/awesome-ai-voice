---
release_date: "July 5, 2026"
model_name: "Typhoon ASR Streaming"
category: "asr"
summary: "SCB DataX — cache-aware streaming FastConformer-Transducer Thai ASR with decode-time shallow fusion: two checkpoints (115M converted from Typhoon ASR Real-time, 0.6B adapted from NVIDIA Nemotron) that cut CER by up to 4.5× versus a streamed full-context baseline while running 42–50× faster than real time and serving ~300 concurrent streams per H100."
slug: "typhoon-asr-streaming"
---

# Typhoon ASR Streaming

**Typhoon ASR Streaming** is SCB DataX's system for **steerable, low-latency
Thai speech recognition**. Open Thai ASR had been dominated by offline
Whisper-style models that read the whole utterance before transcribing; this
release replaces them with **cache-aware streaming encoders** that stay
accurate at low latency, plus a **decode-time shallow-fusion layer** (GPU
4-gram LM + phrase boosting) that steers the vocabulary toward names and
domain terms at runtime — **no retraining, and under a 3% change in the
real-time factor**. At a 1040 ms look-ahead, forcing the old full-context
Typhoon ASR Real-time model to stream collapses to **62.8% CER** on TVSpeech;
the cache-aware models reach **19.4%** (115M) and **14.1%** (0.6B) — a 4.5×
CER reduction. The release ships the two acoustic checkpoints, paired
sub-word 4-gram fusion LMs, an OpenAI-Realtime-style WebSocket ASR server, a
LiveKit Agents STT adapter, a Gradio demo and a Next.js steering front-end.

## Links

- HuggingFace: https://huggingface.co/typhoon-ai/typhoon-asr-streaming-nemotron-0.6b
- HuggingFace: https://huggingface.co/typhoon-ai/typhoon-asr-streaming-115m
- GitHub: https://github.com/warit-s/typhoon-asr-streaming
- Website: https://warit-s.github.io/typhoon-asr-streaming/

## Features

- languages: Thai (th-TH); the 0.6B tokenizer also carries English sub-word units for code-switched terms
- streaming: yes (cache-aware FastConformer-Transducer encoders)
- license: CC BY 4.0 (115M weights); OpenMDW-1.1 (0.6B weights — inherited from its Nemotron base); Apache-2.0 (code — © 2026 SCB DataX)
- parameters: 115M (converted) / 0.6B (adapted, best accuracy, default)
- architecture: FastConformer-Transducer with cache-aware streaming encoders
- variants: typhoon-asr-streaming-115m (converted from Typhoon ASR Real-time, single 2048-token Thai BPE, no prompt) and typhoon-asr-streaming-nemotron-0.6b (adapted from NVIDIA Nemotron streaming ASR, 15,135-token multilingual + Thai tokenizer, requires `target_lang="th-TH"`)
- fusion: GPU 4-gram LM shallow fusion + phrase boosting, applied at decode time (alpha = beta = 0.5)
- fusion_cost: < 3% RTF
- latency_options: 1040 / 480 / 80 ms look-ahead (minimum 80 ms)
- cer_streaming_1040ms_tvspeech: full-context forced to stream 62.8 → 115M 19.4 → 0.6B 14.1
- cer_streaming_1040ms_gigaspeech2: full-context forced to stream 39.8 → 115M 10.4 → 0.6B 9.3
- steering_0.6b: baseline 14.4% CER / 16.6% keyword recall → +n-gram 14.6 / 20.4 → +phrase boost 14.1 / 20.7
- efficiency: batch-1 RTF 0.020–0.024 (42–50× faster than real time); batch-16 ≈300 concurrent streams per H100
- first_token: ≈ look-ahead + ~25 ms
- serving: OpenAI Realtime-style WebSocket server, LiveKit Agents STT adapter, Gradio demo, Next.js front-end
- dependency: NVIDIA NeMo pinned to source commit `907edfd`
- evaluation_data: TVSpeech and GigaSpeech2-Thai
- ngram_rebuild: `scripts/` rebuilds the 0.6B n-gram from your own corpus
- provenance: the contaminated n-gram used as a memorization upper bound in the paper is not distributed
- venue: IEEE SLT 2026 system demo (SCB DataX, Bangkok)

## Comparison

- languages: Thai
- streaming: ✅
- license: CC BY 4.0 / OpenMDW-1.1

## Innovation

The interesting move is treating **latency as a runtime dial rather than a
training-time commitment**. Cache-aware streaming encoders make the
look-ahead a decode parameter, so one checkpoint spans 1040 ms down to 80 ms
— and the release exposes exactly that trade-off in an interactive demo that
streams the same Thai clip through the full-context baseline and both
cache-aware models side by side. The baseline is the argument: at 80 ms
look-ahead it "collapses into garble", which is the honest version of the
claim that cache-aware training is not optional for low-latency streaming.
The second bet is **decode-time vocabulary steering**: shallow fusion with a
GPU n-gram LM plus phrase boosting lets a user inject names like *Betagro* or
*กชพร* mid-stream, which matters disproportionately in Thai broadcast speech
where rare proper nouns and code-switched English jargon dominate the error
budget. Crucially the paper reports both halves of the trade — phrase
boosting pulls CER from 14.4% to 14.1% while lifting keyword recall from
16.6% to 20.7%, and the whole fusion layer costs under 3% RTF — rather than
reporting only the accuracy win. The repo also declines to ship the
contaminated n-gram it used as a memorization upper bound, keeping only the
honest fusion artifacts.
