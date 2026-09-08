---
release_date: "July 13, 2026"
model_name: "sanoTTS"
category: "tts"
summary: "Ampixa — sano (सानो, Nepali for \"small\") is the smallest known neural TTS family: 294k–2.3M parameters per voice, 11 voices across 6 languages, running real-time on a $3 ESP32-S3 microcontroller (output through a GPIO into an LM386 + speaker) and live in the browser via WebAssembly, with under 4 MB per voice and zero dependencies."
slug: "sanotts"
---

# sanoTTS

**sanoTTS** is the smallest known neural text-to-speech family.
The name *sano* (सानो) is Nepali for **"small"**. Each voice weighs
**294k to 2.3M parameters** — smaller than the smallest voice in
prior families (TinyTTS at 1.62M; Inflect Nano at 4.63M; Kokoro at
82M) and the family fits in **under 4 MB per voice** with zero
runtime dependencies (the espeak-ng phonemizer is bundled). Voices
run **real-time on a ~$3 ESP32-S3 microcontroller** (output through
a GPIO into an LM386 and a speaker) and **live in the browser via
WebAssembly** — no server, no upload, no NPU. The full neural stack
is **duration → acoustic → decoder**, quantized to int8, with the
espeak-ng phonemizer included. **11 voices** across **6 languages**
ship: English, Nepali, Hindi, Vietnamese, Indonesian, and Chinese —
including the 294k `heart-nano` voice (337 KB) and the mel-based
`heart` / `heart-nano` pair that predicts a 100-band spectrogram
rendered by a noise-fed ConvNeXt + iSTFT decoder at 24 kHz. The
inference runtime was relicensed **MIT** (September 2026); the
project as a whole remains GPLv3 via espeak-ng. The project page at
[ampixa.github.io/sanoTTS](https://ampixa.github.io/sanoTTS/)
hosts a live browser synthesis demo for every voice.

## Links

- HuggingFace: https://huggingface.co/ampixa/sanoTTS
- GitHub: https://github.com/Ampixa/sanoTTS
- Website: https://ampixa.github.io/sanoTTS/

## Features

- parameters: 294k–2.3M per voice (smallest = the 294k "heart-nano" voice, 337 KB)
- voice_cloning: no (per-voice trained weights; own-voice training via distillation recipe, not zero-shot)
- asr: no
- languages: English, Nepali, Hindi, Vietnamese, Indonesian, Chinese (6 languages, 11 voices)
- streaming: no (full-utterance synthesis; real-time on device and browser)
- license: Other
- architecture: full neural stack — duration model → acoustic model → decoder
- quantization: int8 (W8/A12, corr 0.9995+; piperlite portable C99)
- runtime_microcontroller: ESP32-S3 (real-time RTF 0.41, GPIO → LM386 → speaker)
- runtime_browser: WebAssembly (no server, no upload, no NPU)
- runtime_footprint: under 4 MB per voice, zero dependencies
- voices: 11 (English: amy / kristin / hfc / amy-1p1m / amy-1p8m / robot / heart / heart-nano; one voice each for NE / VI / ID / ZH + shared lang voices)
- phonemizer: espeak-ng (bundled)
- license_split: inference runtime MIT; project overall GPL-3.0 (copyleft from espeak-ng)
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
The newest `heart` / `heart-nano` voices switch to a mel-based recipe
(100-band spectrogram + noise-fed ConvNeXt + iSTFT decoder at 24 kHz),
bringing the smallest voice down to **294k parameters / 337 KB** —
a per-voice footprint 100× smaller than Kokoro and 2× smaller than
TinyTTS while still leading SCOREQ / UTMOS in the sub-15M class —
and the demo synthesizes every voice **live in the browser via
WASM**, so the smallest-known neural TTS is also the only one that
runs unattended on a $3 chip and a $0 web page.
