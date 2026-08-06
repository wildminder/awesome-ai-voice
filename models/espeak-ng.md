---
release_date: "December 8, 2015"
model_name: "eSpeak-NG"
category: "tts"
summary: "eSpeak NG — the compact open-source formant-synthesis TTS engine (C codebase) supporting 100+ languages and accents; <10 MB footprint total; available as CLI, shared library (libespeak-ng), SAPI5 on Windows, MBROLA back-end, SSML-supporting. Powering downstream neural TTS pipelines' G2P/phonemizer (including sanoTTS, which bundles its own port)."
slug: "espeak-ng"
---

# eSpeak-NG

**eSpeak NG** is a compact open-source software text-to-speech
synthesizer for Linux, Windows, Android, and other operating
systems. It supports **more than 100 languages and accents**, is a
fork of Jonathan Duddington's original eSpeak engine, and uses the
**formant synthesis** method: the model produces speech by
explicitly computing the acoustic resonances (formants) of each
phoneme, not by concatenating human-speech recordings. The trade
is well-known — the speech is clear and usable at high playback
speeds, but **not as natural or smooth** as larger neural or
concatenative synthesizers. The compensation is size: the program
and its data, including many languages, total a few megabytes.
Other synthesis methods supported: **Klatt formant synthesis** and
**MBROLA diphone back-end** via the documented integration.

eSpeak-NG ships as:

* A command-line program (`espeak-ng`) for Linux + Windows to
  speak text from a file or stdin.
* A shared library version (`libespeak-ng`) for use by other
  programs (DLL on Windows).
* A SAPI5 version for Windows — usable with screen-readers and
  other SAPI5-compatible software.
* Ports to Solaris, Mac OS X, and other platforms.

The engine's phoneme output and G2P rules are heavily reused in the
neural TTS ecosystem as a front-end phonemizer (e.g. sanoTTS bundles
espeak-ng to convert text → phonemes for its duration model).

## Links

- GitHub: https://github.com/espeak-ng/espeak-ng

## Features

- parameters: n/a (formant-synthesis engine; not a neural model)
- voice_cloning: no (formant synthesis has no concept of per-voice speaker embeddings)
- asr: no
- languages: 100+ languages and accents (see docs/languages.md)
- streaming: yes (text-to-speech in real time; CLI streaming output)
- license: GPL-3.0
- synthesis_method: formant synthesis (primary); Klatt formant synthesis (secondary); MBROLA diphone backend (optional)
- footprint: a few MB (program + data + many languages)
- audio_output: WAV file (CLI), direct playback, or shared-library API
- input_formats: text from file / stdin (CLI), SSML (partial), HTML (partial)
- packages: CLI (espeak-ng man page), shared library (libespeak-ng), SAPI5 Windows module
- supersedes: eSpeak (Jonathan Duddington's original engine)
- downstream_usage: G2P / phonemizer for neural TTS pipelines (e.g. sanoTTS bundles espeak-ng for its duration model)
- platforms: Linux, Windows, Android, Solaris, Mac OS X

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: 100+
- streaming: ✅
- license: Other

## Innovation

eSpeak-NG is **the** canonical reference implementation of compact
multi-language formant synthesis. Its 100+-language coverage in a
few megabytes, plus SSML / SAPI5 / MBROLA / shared-library / CLI
surfaces, are matched only by neural TTS systems that are **orders
of magnitude larger**. The reason it belongs in a list whose other
entries are neural TTS systems is its continued quiet role in the
neural stack as a **G2P / phonemizer front-end** — the phoneme
inventory and grapheme-to-phoneme rules that sanoTTS and similar
sub-1B neural TTS engines bundle are often just a port of
eSpeak-NG's language-data files. So even if the formant-synthesis
audio output itself has been surpassed for naturalness, the
**phoneme infrastructure** underneath many of the smaller neural
TTS entries on this list still traces back to eSpeak-NG.
