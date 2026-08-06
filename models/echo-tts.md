---
release_date: "December 4, 2025"
model_name: "Echo-TTS"
category: "tts"
summary: "Jordan Darefsky — Echo: a 2.4B diffusion-DiT text-to-speech model conditioned on target text and up to two minutes of speaker reference audio; generates Fish Speech S1-DAC latents at 44.1 kHz with up to 30-second outputs; ~1.45 s to produce 30 s audio on a single A100 (RTF < 0.05). Trained via the Google TPU Research Cloud."
slug: "echo-tts"
---

# Echo-TTS

**Echo** is a 2.4B-parameter **diffusion-based diffusion transformer
(DiT)** text-to-speech model. It conditions on target text and up to
**two minutes of speaker reference audio**, generates Fish Speech
S1-DAC latents, and decodes to **44.1 kHz** audio. Output length is
up to **30 seconds per segment**. The model is fast at single-sample
generation: on one A100, generating 30 seconds of audio from a
120-second prompt takes **~1.45 seconds** (RTF < 0.05) —
substantially faster than frontier autoregressive approaches at
similar quality. The architecture is a deliberate pivot from the
author's prior autoregressive-in-DAC-space model **Parakeet**,
which struggled with semantic-consistency retries and weak voice
cloning; Echo's diffusion approach trades off real-time
interactivity for **fast, high-fidelity zero-shot voice cloning**
in offline synthesis. Trained via the TPU Research Cloud (TRC).
Demo (preview) hosted on `jordand/echo-tts-preview` HF Space;
base model on `jordand/echo-tts-base`.

## Links

- HuggingFace: https://huggingface.co/jordand/echo-tts-base
- GitHub: https://github.com/jordandare/echo-tts
- Demo: https://huggingface.co/spaces/jordand/echo-tts-preview
- Blog: https://jordandarefsky.com/blog/2025/echo/

## Features

- parameters: 2.4B (DiT)
- voice_cloning: yes (zero-shot; up to 2 min speaker reference audio)
- asr: no
- languages: English (per demo samples)
- streaming: no (offline; produces 30-second segments at a time)
- license: MIT
- architecture: diffusion transformer (DiT) in Fish Speech S1-DAC latent space
- max_segment_duration: 30 s
- sample_rate: 44,100 Hz
- speaker_reference_max: 120 s
- performance_a100_rt: 30 s output in ~1.45 s (RTF < 0.05)
- audio_codec: Fish Speech S1-DAC
- prior_model: Parakeet (autoregressive in DAC space)
- training_infrastructure: TPU Research Cloud (TRC)
- inference_requirements: CUDA-capable GPU with at least 8 GB VRAM; Python 3.10+
- sampler: euler CFG with independent guidances for text (3.0) and speaker (8.0); 40 steps; sequence_length 640 default
- license_clarification: MIT (per GH repo license)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English
- streaming: ❌
- license: MIT

## Innovation

Echo is a deliberate **next-step pivot from autoregressive-in-DAC-space
TTS to a full diffusion approach**. The author's prior model,
Parakeet, generated DAC tokens autoregressively but suffered the
classic AR weakness — semantic-consistency retries — and weak
voice cloning. Echo keeps Fish Speech S1-DAC latents (so the audio
representation is the same proven codec) but moves the generator
*upstream* to a 2.4B DiT operating directly on those latents,
conditioned on a long (up to 2-minute) speaker reference. The
result: 30-second outputs in ~1.45 s on a single A100 (RTF < 0.05)
with high-fidelity zero-shot cloning — fast enough that the
"diffusion is too slow" objection no longer applies at the segment
length that matters for offline content generation, while the AR
class's retry-induced inconsistency is gone by construction.
