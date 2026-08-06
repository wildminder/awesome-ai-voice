---
release_date: "July 21, 2026"
model_name: "NeuTTS-2E"
category: "tts"
summary: "Neuphonic — NeuTTS-2E: a super-fast, highly realistic on-device emotional TTS (0.2B parameters) with compact LM + codec design; English-only alpha release with four fixed speakers (emily/paul/sophie/steven) and six emotions plus neutral (angry/disgusted/fearful/happy/sad/surprised/neutral); ships as safetensors + Q4 GGUF + Q8 GGUF for CPU-first deployment."
slug: "neutts-2e"
---

# NeuTTS-2E

**NeuTTS-2E** is a super-fast, highly realistic, **on-device**
emotional text-to-speech model from Neuphonic. It is the next
generation after **NeuTTS Air / Nano** (which continue to ship for
multilingual + zero-shot-cloning contexts) — narrowed in scope to
an **English-only alpha** focused on:

* **Emotion control** — six emotions + neutral (`angry`,
  `disgusted`, `fearful`, `happy`, `sad`, `surprised`, `neutral`)
  selected with a single argument.
* **Four fixed speakers** — `emily`, `paul`, `sophie`, `steven` —
  no zero-shot cloning in this release (the project page points at
  NeuTTS Nano Multilingual Collection for cloning / multilingual
  alternatives).
* **Compact LM backbone + codec** at 0.2B parameters, designed for
  **real-time or better-than-real-time on laptop-class CPUs**.
* **No phonemizer** or other system dependencies — text in, audio
  out.

Three checkpoints ship in the official collection as **the same
model in different deployment formats** — the `safetensors` torch
version for full quality, and `q4-gguf` / `q8-gguf` quantizations
for CPU-first / embedded deployment via llama.cpp-compatible
runtimes. The project page notes a `safetensors` "torch" build is
the highest-quality release; Q4 GGUF is the smallest-footprint for
embedding into agents / toys / privacy-sensitive applications; Q8
GGUF sits between the two on the size/quality curve. A live demo
runs on the `neuphonic/neutts-2e` HF Space. The model is alpha —
Neuphonic explicitly warns about squatter domains like `neutts.com`
that are *not* affiliated with the project; the legitimate
landing is `neuphonic.com`.

## Links

- HuggingFace: https://huggingface.co/neuphonic/neutts-2e
- GitHub: https://github.com/neuphonic/neutts
- Demo: https://huggingface.co/spaces/neuphonic/neutts-2e
- Collection: https://huggingface.co/collections/neuphonic/neutts-2e

## Features

- parameters: 0.2B (compact LM backbone + codec)
- voice_cloning: no (fixed speakers only — emily/paul/sophie/steven)
- asr: no
- languages: English (English-only alpha)
- streaming: yes (no explicit token but real-time / better-than-real-time CPU inference is the headline)
- license: Other (HF tag `license:other`; no LICENSE file in the underlying Neuphonic GitHub repo)
- backbone: compact LM backbone tuned for emotional TTS token generation
- codec: efficient codec (compact, paired with the LM)
- speakers: 4 fixed (`emily`, `paul`, `sophie`, `steven`)
- emotions: 6 + neutral (`angry`, `disgusted`, `fearful`, `happy`, `sad`, `surprised`, `neutral`)
- emotion_control_mode: single-argument selection (no composable multi-axis axes like Scylla's Band)
- input_format: text only — no phonemizer, no system dependencies
- on_device: yes (laptop-class CPU real-time / better-than-real-time)
- distribution_formats: safetensors (torch), Q4 GGUF, Q8 GGUF
- formats_in_collection: `neuphonic/neutts-2e` (safetensors), `neuphonic/neutts-2e-q4-gguf` (smallest footprint), `neuphonic/neutts-2e-q8-gguf` (mid-tier compression)
- gguf_features: imatrix, conversational, endpoints_compatible
- pipeline_tag: text-to-speech
- library_name: (HF tag does not declare transformers / safetensors stem beyond safetensors itself)
- downloads: 194 / 241 / 216 (torch / q4 / q8)
- intended_use: embedded voice agents, on-device assistants, toys, privacy-sensitive applications
- comparison_with_air_nano: Air/Nano continue to ship for zero-shot cloning + multilingual contexts; 2E is the next-gen focused English emotional variant
- safety_note: model is alpha; legitimate project landing is `neuphonic.com` (not `neutts.com`)

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: English
- streaming: ✅
- license: Other

## Innovation

The technical center of NeuTTS-2E is *maximum speed per parameter*
at on-device budgets — the 0.2B LM + codec pair delivers
**real-time-or-better on laptop-class CPUs** while exposing
**discrete categorical emotion control** (`angry` / `disgusted` /
`fearful` / `happy` / `sad` / `surprised` / `neutral`) plus a
**fixed four-speaker cast** for consistency in agent / toy /
accessibility voice personas. Two design choices distinguish it from
the surrounding TTS field:

First, the **categorical emotion surface is single-axis and
discrete** (one emotion per call), not the continuous multi-axis
composable vector surface used by models like Scylla's Band
([neurotica base + 6-axis continuous strengths]). The project's
positioning — production-grade agents + toys + accessibility —
benefits from a one-argument API where `emotion="happy"` is the
explicit operational state. The release locks emotional mode at
generation time, which simplifies downstream filtering / guardrails.

Second, the **distribution-shape design** (one model, three
deployment formats) is a deliberate on-device-first posture: the
`safetensors` torch build for max-quality GPU/server; `Q8 GGUF` for
mid-tier compression; `Q4 GGUF` for the small-footprint embedded
target. All three are direct llama.cpp-compatible drops of the
same model — no retraining-per-format — letting users pick size vs
quality at deployment time without changing the production API.
The combined CPU-first + GGUF-first design pattern is the
opposite of the cloud-first TTS systems in this list — and is what
makes 2E suitable for embedded voice agents, toys, and
privacy-sensitive applications where audio + text must remain
on-device.
