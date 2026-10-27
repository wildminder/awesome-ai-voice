---
release_date: "September 26, 2026"
model_name: "Resona"
category: "tts"
summary: "MilannSharma — an ultra-compact 82M-parameter offline neural TTS engine for commodity CPUs (RTF 0.18x single-thread, ~420 MB RAM), with native Hinglish code-switching, 21 preset voice personas selected from 256-D style tensors, espeak-ng/IPA G2P routing across 10 declared languages, and a built-in breathing-cadence pause injector."
slug: "resona"
---

# Resona

**Resona** is an **82M-parameter neural TTS engine** built for the opposite of
the cloud: 100% air-gapped, no GPU, no telemetry, synthesized on a
commodity CPU. It targets the gap the author describes between cloud APIs
(which cost latency and privacy) and small open engines that sound robotic on
Indian languages and Hinglish code-switching. The pipeline is a text
normalizer feeding a **language router**; Hinglish text passes through a
custom transducer with a **protected technical-term whitelist** before hitting
a **Devanagari/IPA phonemizer** (built on `espeak-ng`, which must be installed
separately), then a token-and-rhythm alignment stage and an **AdaIN prosody
predictor** driven by a **256-D voice style tensor**, an 82M **neural
vocoder**, and finally a **breathing-cadence injector** that places 180 ms
clause pauses and 350 ms sentence boundaries. Two checkpoints ship
(`resona-v1.pth` and `resona-indic-v1.pth`, ~327 MB each) and **21 "Grade A"
voice personas** are selectable by name, each defined by a pre-rendered style
tensor rather than a reference clip. Speed is the headline metric: **RTF
0.18x** and a **180 ms cold start** measured on a single thread of an Intel
Core i7-12700H, at ~420 MB RAM, outputting 24 kHz WAV.

## Links

- HuggingFace: https://huggingface.co/milansharma94/Resona
- GitHub: https://github.com/MilannSharma/Resona-TTS

## Features

- parameters: 82M (two ~327 MB checkpoints — resona-v1.pth and resona-indic-v1.pth)
- voice_cloning: no (21 preset personas from pre-rendered 256-D style tensors; no reference-clip path)
- asr: no
- languages: 10 (Hinglish and Hindi are native; es/fr/it/pt/ja/zh and en-GB are routed through the espeak-ng IPA G2P front-end into the same vocoder)
- streaming: no (batch synthesis; the speed claim is throughput, not streaming)
- license: Apache-2.0
- output_sample_rate: 24 kHz
- voices: 21 "Grade A" personas, each with a persona character, pitch and speed; 8 Hinglish/Indic flagships include `anjura`, `divya`, `meera`, `priya`, `arjun`, `kabir`, `aman`, `atul`
- g2p: espeak-ng Devanagari/IPA for Hindi; American and British English IPA; Spanish, French, Italian, Portuguese IPA; Romaji/Kana for Japanese; Pinyin for Mandarin
- code_switching: custom Hinglish transducer with a protected technical-term whitelist so terms are not mis-transliterated
- prosody_control: AdaIN prosody predictor conditioned on a 256-D voice style tensor
- breathing_cadence: 180 ms clause pauses and 350 ms sentence boundaries inserted automatically
- pipeline: text normalizer → language router → Hinglish transducer / phonemizer → token and rhythm alignment → AdaIN prosody predictor → 82M neural vocoder → breathing cadence → 24 kHz WAV
- benchmarks: cold start 180 ms, RTF 0.18x, 48 words/s, ~420 MB RAM — measured on one thread of an Intel Core i7-12700H
- quality_metrics: none reported (no MOS, speaker similarity, intelligibility or third-party evaluation)
- requirements: Python 3.9–3.12 and `espeak-ng` installed on the host (auto-discovery plus CLI fallback)
- interfaces: Python API (`from resona import ResonaPipeline`) and a `resona-tts` CLI with `--list-voices`, `--voice`, `--lang`, `--speed`
- repository: self-contained Python package (core, preprocessing, voices, vocab, cli), bundled lexicons, example scripts, an automated test suite, and SHA-256 release integrity hashes
- provenance: the repository ships a NOTICE file describing upstream architectural foundations

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: 10
- streaming: ❌
- license: Apache-2.0

## Innovation

What Resona is really selling is a **budget**: 82M parameters and a
single-thread CPU RTF of 0.18x puts it in a class of its own in this list,
where most TTS models assume a GPU. The engineering consequence is visible in
the architecture — rather than a large autoregressive acoustic model, the
quality budget is spent on **deterministic post-processing** (the breathing-cadence
pause injector) and on **front-end robustness** (the Hinglish transducer plus
a protected technical-term whitelist, which is a surprisingly concrete
acknowledgment that code-switched text usually breaks on exactly the product
names, resolutions and menu items a tutorial voice needs to say). The 21
personas as **256-D style tensors with per-voice pitch and speed** is a
lightweight alternative to voice cloning: no reference audio, no training,
just a style vector per speaker. The "10 languages" figure deserves a careful
read, though — Hinglish and Hindi are the native path, while the remaining
eight come from `espeak-ng`'s existing IPA front-end feeding the same 82M
vocoder, so the breadth is inherited from the phonemizer rather than from
acoustic training in those languages. This is also a very young release:
first public commit 2026-09-26, no published quality metrics, no MOS or
speaker-similarity numbers, and speed figures that are self-reported on one
CPU. Treat the engineering and the licensing as the substance, and the
"studio-grade" quality claims as unverified.
