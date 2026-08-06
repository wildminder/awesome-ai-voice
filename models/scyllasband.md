---
release_date: "July 19, 2026"
model_name: "Scylla's Band"
category: "tts"
summary: "Spybyscript — multilingual, multi-voice, expressive continuous-latent TTS designed for self-hosted ONNX Runtime inference; predicts phone durations and rectified acoustic latent flow, decodes 24 kHz via Scylla's Band acoustic adapter + Vocos vocoder; 10 managed voices across en_us/en_gb/es/it, 6 independently-scored affect axes (calm/joy/anger/sadness/sarcasm/questioning)."
slug: "scyllasband"
---

# Scylla's Band

**Scylla's Band** is a multilingual, multi-voice, **expressive** TTS
model from Spybyscript, designed specifically for **local and
self-hosted inference** through ONNX Runtime (with an experimental
LiteRT backend for explicit native / mobile use). The architecture
is a continuous-latent TTS family:

1. Phrase-level multilingual G2P produces phone IDs, punctuation,
   and boundary / context features in a fixed 512-text-token window
   with a 74-phone vocabulary.
2. A **duration predictor** (4 layers / 4 heads / hidden 192) predicts
   phone durations span-by-span with up to a 512-phone budget.
3. A **rectified-flow acoustic latent generator** (12 layers / 8 heads /
   hidden 512, AdaLN conditioning, QK normalization) emits
   **24-dimensional acoustic latents** at 100 mel bins, 256-sample /
   512-latent hop.
4. A **Scylla's Band acoustic adapter** + frozen
   `charactr/vocos-mel-24khz` vocoder render the latents into
   24 kHz waveforms.

The release ships **10 managed voices** — ariadne / felix / gwen /
ink / max / orpheus / rex / scylla / stone / tuesday — every voice
speaks **`en_us`, `en_gb`, `es`, `it`**. Beyond the standard TTS
matrix, the model exposes **6 continuously-scored affect axes**
(`calm`, `joy`, `anger`, `sadness`, `sarcasm`, `questioning`).
`calm / joy / anger / sadness` describe core delivery as
**composable continuous strengths**; `sarcasm` and `questioning`
are **overlays** that can be mixed with any core delivery. Affect
CFG acts on both duration and acoustic-flow prediction while
retaining voice / reference conditioning. Long-form narration has
automatic chunking with boundary metadata, punctuation pause
floors, prefix-latent carryover, and span context. Group-speak
input labels lines or inline spans with `[voice]`,
`[voice:language]`, or `[voice:language:axis=value,...]` annotations.

Defaults are tuned for CPU / desktop inference: **8-step Heun
sampling**, fixed graph budgets of 512 G2P text tokens / 512 phone
frames / 640 latent frames, latent-target buckets of 256 / 384 /
512 / 640 (smallest fit). Voice references are 128-dimensional
style + 32-dimensional prosody features. The model is explicitly
**not** an arbitrary-speaker cloning system — the 10 managed
voices ship as author-curated bundles; cloning is out of scope.

## Links

- HuggingFace: https://huggingface.co/spybyscript/scyllasband
- GitHub: https://github.com/lowkeytea/scyllasband
- Website: https://lowkeytea.github.io/scyllasband/

## Features

- parameters: not stated (architecture: 4-layer duration predictor (192 hidden) + 12-layer rectified-flow acoustic generator (512 hidden, AdaLN, QK norm))
- voice_cloning: no (10 **managed** voices only; explicit anti-cloning design choice)
- asr: no
- languages: en_us, en_gb, es, it (4 public text-input languages)
- streaming: yes (long-form chunking with span + prefix context; CLI `stream` subcommand)
- license: Apache-2.0
- sample_rate: 24,000 Hz
- managed_voices: 10 (ariadne, felix, gwen, ink, max, orpheus, rex, scylla, stone, tuesday)
- voice_default_locale: en_us for most; ink / orpheus / tuesday default to en_gb
- voice_style_dim: 128 (style features) + 32 (prosody features)
- affect_axes: 6 (calm, joy, anger, sadness, sarcasm, questioning — all continuous in `[0, 1]`)
- affect_overlay_axes: sarcasm, questioning (mixable with any core delivery)
- affect_cfg_scope: duration + acoustic-flow prediction (preserves voice / reference)
- encoders_default: ONNX Runtime (Python CLI / Python API / Android sample / `libscyllasband` native)
- encoders_experimental: LiteRT (experimental / explicit-selection)
- cli_quality_default: 8-step Heun sampling
- graph_budgets: 512 G2P text tokens / 512 phone frames / 640 latent frames
- latent_target_buckets: 256 / 384 / 512 / 640 (smallest-fit selection)
- vocoder: Scylla's Band acoustic adapter + frozen `charactr/vocos-mel-24khz`
- hop_lengths: 256 (waveform) / 512 (latent)
- text_frontend: phrase-level multilingual G2P (74-phone vocabulary)
- span_context: 3 segments over up to 768 phones with 512-dim context state
- prefix_context: up to 24 acoustic latent frames from preceding chunk
- long_form_features: boundary metadata + punctuation pause floors + prefix-latent carryover + span context
- group_speak_input: `[voice]`, `[voice:language]`, `[voice:language:axis=value,...]` annotations
- bundle_contract: 1.0.0 / `scyllasband-duration-flow`
- intended_use: single-voice speech synthesis (10 voices); en/es/it; long-form narration; multi-voice dialogue from tagged text; continuous affect control; ONNX desktop/server; ONNX + LiteRT native/mobile
- not_intended: arbitrary-speaker cloning / impersonation / fraud / deceptive speech
- distributions: training data, trainer checkpoints, and export tooling not distributed
- cli_commands: download, validate-bundle, list-voices, normalize-text, speak, group-speak, stream, plan
- library_name: onnxruntime (tags include onnx, tflite, litert, duration-flow)

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: en_us, en_gb, es, it
- streaming: ✅
- license: Apache-2.0

## Innovation

Three design decisions distinguish Scylla's Band in the multilingual
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
