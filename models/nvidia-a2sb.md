---
release_date: "August 1, 2025"
model_name: "NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)"
category: "restoration"
summary: "NVIDIA — diffusion Schrödinger Bridge for high-resolution (44.1 kHz) music restoration: end-to-end, vocoder-free, multi-task bandwidth extension + inpainting that can restore hour-long audio without boundary artifacts."
slug: "nvidia-a2sb"
---

# NVIDIA A2SB (Audio-to-Audio Schrodinger Bridges)

A2SB is NVIDIA's audio-to-audio Schrödinger Bridge diffusion model for high-resolution (44.1 kHz) music restoration. It is the first long-audio restoration model that can restore hour-long inputs without boundary artifacts, and it's end-to-end — predicting waveform outputs directly without a separate vocoder. A single trained checkpoint handles both bandwidth extension (predicting high-frequency components) and inpainting (re-generating missing segments), training on permissively-licensed subsets of FMA, Medley-Solos-DB, MUSAN, Musical Instrument, MusicNet, Slakh, FreeSound, FSD50K, GTZAN, and NSynth.

## Links

- GitHub: https://github.com/NVIDIA/diffusion-audio-restoration
- HuggingFace: https://huggingface.co/nvidia/audio_to_audio_schrodinger_bridge
- Demo: https://research.nvidia.com/labs/adlr/A2SB/
- Paper: https://arxiv.org/abs/2501.11311

## Features

- type: High-Resolution Audio Restoration
- bandwidth_extension: yes (full-band HF reconstruction)
- inpainting: yes (segment re-generation for hour-long audio)
- license: NVIDIA NC (NVIDIA OneWay NonCommercial License)
- channels: stereo
- sample_rate: 44.1 kHz
- architecture: End-to-end vocoder-free diffusion Schrödinger Bridge (factorized audio representation)
- long_audio: yes (hour-scale restoration, no boundary artifacts)
- multi_task: yes (single model, joint bandwidth-extension + inpainting)
- training_data: FMA, Medley-Solos-DB, MUSAN, Musical Instrument, MusicNet, Slakh, FreeSound, FSD50K, GTZAN, NSynth (permissive subsets)

## Comparison

- type: High-Resolution Audio Restoration
- bandwidth_extension: ✅
- inpainting: ✅
- license: NVIDIA OneWay NonCommercial License

## Innovation

A diffusion Schrödinger Bridge formulation that is **end-to-end vocoder-free**: instead of generating a mel / MFCC / latent and then re-synthesising, the model predicts the waveform directly, which is what lets it stay boundary-free over hour-long inputs. The same checkpoint carries both bandwidth extension and inpainting — two distinct restoration tasks trained jointly on permissive-licensed music data and rolled out under NVIDIA NC.
