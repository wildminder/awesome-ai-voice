---
release_date: "May 25, 2026"
model_name: "MOSS-SoundEffect"
category: "a2a"
summary: "OpenMOSS / MOSI.AI — high-fidelity text-to-sound-effect generation. v2.0 (DiT + Flow Matching + DAC VAE + Qwen3 encoder) supersedes v1 (MossTTSDelay discrete-token AR); English + Chinese, up to 30 s at 48 kHz."
slug: "moss-soundeffect"
---

# MOSS-SoundEffect

MOSS-SoundEffect is the dedicated **text-to-sound** model in the OpenMOSS / MOSI.AI MOSS-TTS family. It turns natural-language captions into high-fidelity non-speech audio (ambience, urban scenes, creatures, human actions, and short music-like clips).

Two public releases sit on the same `MOSS-TTS` umbrella: **v1** (`MOSS-SoundEffect`) with a discrete-token autoregressive backbone (`MossTTSDelay`), and **v2.0** (`MOSS-SoundEffect-v2.0`) that supersedes v1 with a continuous-latent **DiT + Flow Matching** backbone paired with a DAC VAE and a Qwen3 (1.7B) text encoder. v2.0 covers broad SFX (natural environments, urban, animals, human actions, short percussive clips), supports up to **30 s** stable generation per call, and accepts both **English and Chinese** captions.

## Links

- HuggingFace: https://huggingface.co/OpenMOSS-Team/MOSS-SoundEffect-v2.0
- HuggingFace: https://huggingface.co/OpenMOSS-Team/MOSS-SoundEffect (legacy v1 checkpoint)
- GitHub: https://github.com/OpenMOSS/MOSS-TTS/tree/main/moss_soundeffect_v2

## Features

- type: Text-to-Sound / SFX generation
- conditioning: Text
- max_duration: 30 seconds
- sample_rate: 48 kHz
- license: Apache-2.0
- architecture: DiT + Flow Matching + DAC VAE + Qwen3 text encoder
- parameters: 1.3B (DiT variant 1.3B)
- languages: English, Chinese
- inference_defaults: 100 flow-match steps, cfg 4.0, sigma_shift 5.0
- library: diffusers

## Comparison

- text: ✅
- max_duration: 30 s
- sample_rate: 48 kHz
- license: Apache-2.0

## Innovation

Replaces the discrete-token autoregressive v1 (which bottlenecked on vocabulary) with a continuous-latent DiT + Flow Matching paired with a DAC VAE — yielding **30 s** stable audio, bilingual English + Chinese prompts, and a clean CFG/sigma-shift inference schedule (cfg 4.0, shift 5.0) that works straight out of the box on the `diffusers` library.
