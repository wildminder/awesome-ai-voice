---
release_date: "May 22, 2026"
model_name: "VoxFlash-TTS"
category: "tts"
summary: "VoxFlash — ultra-compressed latent-diffusion TTS for real-time zero-shot voice cloning in Chinese and English; VAE compresses 24 kHz waveforms to only 9 frames/s (≈8× tighter than EnCodec), so 10 s of audio = only 90 latent vectors to generate, enabling real-time cloning on consumer and edge GPUs."
slug: "voxflash-tts"
---

# VoxFlash-TTS

**VoxFlash-TTS** is a zero-shot voice-cloning text-to-speech
engine built around extreme latent compression. The VAE encodes
24 kHz waveforms into a **9 frames/s** latent space — roughly
8× more compressed than EnCodec (75 fps) and 2.4× more than Stable
Audio (21.5 fps). Generating 10 s of audio therefore requires the
diffusion model to produce just **90 latent vectors** rather than
hundreds or thousands of tokens, with downstream quadratic savings
in attention cost. A ConvNeXtV2-based phoneme encoder followed by
a novel coarse-alignment algorithm (cheaper than cross-attention)
maps text into the latent sequence; a modern diffusion head then
iteratively refines speech latents that the lightweight VAE
decoder renders back to waveforms. The architecture targets
low-latency, low-resource deployment — consumer-grade GPUs and
edge devices — with Chinese and English zero-shot cloning. The
project card lists `inference: false` on HF (no hosted inference
endpoint), but the project page at
[voxflash.github.io](https://voxflash.github.io/) carries the
abstract, demo examples, and ablations.

## Links

- HuggingFace: https://huggingface.co/VoxFlashTTS/VoxFlashTTS
- GitHub: https://github.com/VoxFlash/VoxFlashTTS
- Website: https://voxflash.github.io/
- Paper: https://arxiv.org/abs/2406.02430

## Features

- parameters: not stated (ConvNeXtV2 phoneme encoder + diffusion head + lightweight VAE decoder)
- voice_cloning: yes (zero-shot, Chinese + English)
- asr: no
- languages: Chinese, English
- streaming: no (offline; "real-time" = wall-clock, not chunked streaming)
- license: Apache-2.0
- audio_codec: VoxFlash VAE (9 Hz / 9 fps latent, 24 kHz input)
- compression_ratio: ~8× tighter than EnCodec (75 fps), ~2.4× tighter than Stable Audio (21.5 fps)
- phoneme_encoder: ConvNeXtV2 + coarse-alignment algorithm (no cross-attention)
- diffusion_head: modern multi-step iterative refinement
- decoder: lightweight VAE decoder
- sample_rate: 24,000 Hz
- inference: local CUDA ≥ 12.3.2; no HF hosted endpoint
- training_dataset: seed-tts-eval
- metrics: word_error_rate, speaker_similarity

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Chinese, English
- streaming: ❌
- license: Apache-2.0

## Innovation

The central technical move is **compressing the audio latent
space to 9 frames/s instead of the conventional 75 fps (EnCodec)
or 21.5 fps (Stable Audio)**. This is not a quantization tweak —
it is a temporal-decimation architectural choice that shrinks the
sequence length the diffusion model has to traverse, and because
attention cost scales quadratically with sequence length the
end-to-end compute drops by orders of magnitude. Combined with a
**coarse-alignment phoneme-to-latent map that avoids cross-attention
entirely** (using a ConvNeXtV2 phoneme encoder instead), VoxFlash
hits millisecond-level inference latency on consumer-grade and
edge hardware for zero-shot Chinese + English cloning, where
conventional latent-diffusion TTS systems are too slow for real-time
edge deployment.
