---
release_date: "November 28, 2025"
model_name: "Chroma-4B"
category: "a2a"
summary: "FlashLabs — Chroma 1.0: an open-source real-time end-to-end spoken-dialogue model achieving both sub-second latency (RTF 0.43) and high-fidelity personalized voice cloning; interleaved text-audio token schedule (1:2) supports streaming generation; 10.96% relative improvement in speaker similarity over the human baseline."
slug: "chroma-4b"
---

# Chroma-4B

**Chroma 1.0** (FlashLabs' `Chroma-4B` on HuggingFace) is the first
open-source, real-time, **end-to-end spoken dialogue model** that
achieves both **sub-second end-to-end latency** and **high-fidelity
personalized voice cloning**. The pipeline is end-to-end — no
separate ASR → LLM → TTS stitch — speech goes in, speech comes out.
The architectural centerpiece is an **interleaved text-audio token
schedule (1 text : 2 audio)** that supports streaming generation,
so the model can begin emitting audio while the user is still
talking (broken-off turns / barge-in handled). Experimental results
from the project's paper:

* Speaker similarity: a **10.96% relative improvement over the
  human baseline** — meaning the model's cloned voice is closer
  to the reference speaker than two of *the same* human speaker's
  recordings are to each other on the project's test apparatus.
* Real-Time Factor (RTF): **0.43** — the model produces speech at
  ~2.3× the speed of wall clock, comfortably real-time.
* Maintains strong reasoning and dialogue capability at this
  low-latency + cloning-form fidelity setting — i.e. the trade
  is not at the cost of LLM-quality.

Demo Space: `hysts/Chroma-4B`.

## Links

- HuggingFace: https://huggingface.co/FlashLabs/Chroma-4B
- Paper: https://arxiv.org/abs/2601.11141
- Demo: https://huggingface.co/spaces/hysts/Chroma-4B

## Features

- parameters: 4B
- voice_cloning: yes (high-fidelity personalized cloning; zero-shot per-paper)
- asr: yes (end-to-end speech dialogue includes implicit ASR)
- languages: English (per benchmark reporting)
- streaming: yes (interleaved text-audio token schedule 1:2 enables streaming generation)
- license: Apache-2.0
- architecture: end-to-end spoken-dialogue LLM; interleaved text-audio token schedule (1:2); custom_code modules
- pipeline_tag: any-to-any (HF classification)
- audio_tokenization: chroma tokenizer (RVQ-style per project's tag)
- latency_rtf: 0.43 (speech out ~2.3× wall-clock)
- speaker_similarity: +10.96% relative improvement over human baseline
- inference_library: transformers (custom_code)
- correlations_with_larger_class: matches full dialogue turn at streaming latency
- pretrained: yes (safetensors weights)
- hf_space_demos: hysts/Chroma-4B, Pnevka/Chroma-4B
- history: paper arXiv 2601.11141 (2026-01)

## Comparison

- text: ✅
- video: ❌
- audio: ✅
- max_duration: —
- sample_rate: —
- license: Apache-2.0

## Innovation

Two bets together produce the dual property that no prior
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
