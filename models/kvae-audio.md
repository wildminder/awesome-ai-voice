---
release_date: "June 29, 2026"
model_name: "KVAE-Audio"
category: "audio_codecs"
summary: "Kandinsky Lab (Sber) — continuous full-band (48 kHz) audio autoencoder (VAE) producing compact latent codes for downstream TTS / music / sound generative models."
slug: "kvae-audio"
---

# KVAE-Audio

KVAE-Audio is a continuous, full-band (48 kHz) audio autoencoder by Kandinsky Lab / SberBank. It compresses raw waveforms into compact continuous latents (64-dim) and reconstructs them with high fidelity across speech, music, and general sound. The model is intended both for reconstruction and as a latent space for downstream generative models — internal ablations show that swapping the autoencoder under a fixed generator (same DiT, same data, same steps) consistently improves generative quality.

## Links

- HuggingFace: https://huggingface.co/kandinskylab/KVAE-Audio
- GitHub: https://github.com/kandinskylab/kvae-audio
- Website: https://kandinskylab.ai/

## Features

- parameters: 166.9M
- sample_rate: 48 kHz full-band
- latent_dim: 64
- modalities: speech, music, sound
- reconstruction_quality: beats MMAudio/DACVAE/SAME-L on AudioCaps FAD
- architecture: VAE (continuous latents)
- related_papers: 2412.15322, 2410.13720, 2605.18613
- license: MIT

## Comparison

- type: Audio VAE
- sample_rate: 48 kHz
- latent_dim: 64
- modalities: Speech, Music, Sound
- license: MIT

## Innovation

Full-band 48 kHz continuous audio VAE with a comparatively tiny 64-dimensional latent space, designed as a drop-in replacement for prior codec/VAEs for *generative* pipelines — internal benchmarks show lower FAD on AudioCaps and Song Describer than MMAudio, DACVAE (MovieGen), and SAME-L under a fixed generator.
