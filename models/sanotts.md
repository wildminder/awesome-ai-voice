---
release_date: "July 13, 2026"
model_name: "sanoTTS"
category: "tts"
summary: "Ampixa — sano (सानो, Nepali for \"small\") is the smallest known neural TTS family: 745k–1.8M parameters per voice, 9 voices across 6 languages, running real-time on a $3 ESP32-S3 microcontroller (output through a GPIO into an LM386 + speaker) and live in the browser via WebAssembly, with under 4 MB per voice and zero dependencies."
slug: "sanotts"
---

# sanoTTS

**sanoTTS** is the smallest known neural text-to-speech family.
The name *sano* (सानो) is Nepali for **"small"**. Each voice weighs
**745k to 1.8M parameters** — smaller than the smallest voice in
prior families (TinyTTS at 1.62M; Inflect Nano at 4.63M; Kokoro at
82M) and the family fits in **under 4 MB per voice** with zero
runtime dependencies (the espeak-ng phonemizer is bundled). Voices
run **real-time on a ~$3 ESP32-S3 microcontroller** (output through
a GPIO into an LM386 and a speaker) and **live in the browser via
WebAssembly** — no server, no upload, no NPU. The full neural stack
is **duration → acoustic → decoder**, quantized to int8, with the
espeak-ng phonemizer included. **9 voices** across **6 languages**
ship: English (4 voices — including a 745k on-device "robot"
voice), Nepali, Hindi, Vietnamese, Indonesian, and Chinese. The
project page at [ampixa.github.io/sanoTTS](https://ampixa.github.io/sanoTTS/)
hosts a live browser synthesis demo for every voice.

## Links

- HuggingFace: https://huggingface.co/ampixa/sanoTTS
- GitHub: https://github.com/Ampixa/sanoTTS
- Website: https://ampixa.github.io/sanoTTS/

## Features

- parameters: 745k–1.8M per voice (smallest = the 745k on-device "robot" voice)
- voice_cloning: no (per-voice trained weights; no zero-shot cloning)
- asr: no
- languages: English, Nepali, Hindi, Vietnamese, Indonesian, Chinese (6 languages, 9 voices)
- streaming: no (full-utterance synthesis; real-time on device and browser)
- license: GPL-3.0
- architecture: full neural stack — duration model → acoustic model → decoder
- quantization: int8
- runtime_microcontroller: ESP32-S3 (real-time, GPIO → LM386 → speaker)
- runtime_browser: WebAssembly (no server, no upload, no NPU)
- runtime_footprint: under 4 MB per voice, zero dependencies
- voices: 9 (English: amy / kristin / hfc / amy-small / robot; one voice each for NE / HI / VI / ID / ZH)
- phonemizer: espeak-ng (bundled)
- library_name: sanotts
- training_method: distillation (per voice)

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: English, Nepali, Hindi, Vietnamese, Indonesian, Chinese
- streaming: ❌
- license: Other

## Innovation

The hard constraint — be the smallest neural TTS family known,
real-time on a $3 microcontroller — drives the entire stack.
Conventional sub-100M TTS systems are too large for an ESP32's flash
and RAM. sanoTTS keeps the full **duration → acoustic → decoder**
neural pipeline (no espeak-NG-only fallback, no concatenative
hybrid), quantizes everything to int8, and *bundles the phonemizer*
so the whole voice ships in under 4 MB with zero runtime dependencies.
The result is a per-voice footprint 100× smaller than Kokoro and
2× smaller than TinyTTS while still scoring competitively on the
authors' SCOREQ / UTMOS / DNSMOS-SIG no-reference 24-sentence harness
— and the demo synthesizes every voice **live in the browser via
WASM**, so the smallest-known neural TTS is also the only one that
runs unattended on a $3 chip and a $0 web page.
