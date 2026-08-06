---
release_date: "June 25, 2026"
model_name: "Inflect-Nano-v2"
category: "tts"
summary: "Owen Song — Inflect-Nano-v2: complete local text-to-waveform speech synthesis under 4M parameters (3,966,721 deployable); VITS architecture, fixed-voice English TTS with deterministic seeds, long-text handling, 24 kHz mono output, CPU or CUDA inference; 15.97 MB FP32 footprint with PyTorch and ONNX export."
slug: "inflect-nano-v2"
---

# Inflect-Nano-v2

**Inflect-Nano-v2** is a complete local text-to-waveform speech
synthesis model with **3,966,721 deployable parameters** — under
4M total. It is a **VITS**-architecture fixed-voice English TTS
designed for **CPU or CUDA inference** with deterministic seeds,
long-text handling, and **24 kHz mono output**. The full FP32
checkpoint is **15.97 MB**, making it one of the smallest complete
neural TTS systems that produces natural-sounding speech without
a separate vocoder or phonemizer dependency. The model ships with
a public **adaptation toolkit** for preparing data, auditing
train/validation splits, adapting a fixed voice or language,
resuming training, evaluating checkpoints, and exporting PyTorch
or ONNX packages. A sibling **Inflect-Micro-v2** (9.36M parameters)
prioritizes quality below 10M; Nano prioritizes footprint below 4M.
Both share one public API.

## Links

- HuggingFace: https://huggingface.co/owensong/Inflect-Nano-v2
- GitHub: https://github.com/owenawsong/Inflect
- Demo: https://huggingface.co/spaces/owensong/Inflect-v2

## Features

- parameters: 3,966,721 (3.97M deployable)
- voice_cloning: no (fixed-voice; adaptation toolkit enables custom voice/language training)
- asr: no
- languages: English
- streaming: no (full-utterance synthesis; long-text handling via automatic splitting)
- license: Apache-2.0
- architecture: VITS (end-to-end text-to-waveform)
- sample_rate: 24,000 Hz
- footprint: 15.97 MB FP32
- inference: CPU or CUDA; PyTorch + ONNX export
- determinism: deterministic seeds for reproducible generation
- long_text: automatic text splitting and handling
- input_format: text (no phonemizer or system dependencies)
- adaptation_toolkit: data prep, split auditing, voice/language adaptation, training resume, checkpoint eval, PyTorch/ONNX export
- sibling_model: Inflect-Micro-v2 (9.36M params, quality-prioritized below 10M)
- api: one public API across Micro and Nano sizes
- library: pytorch
- metrics: WER
- inference_false_on_hf: yes (no hosted HF inference endpoint; local-only)

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: English
- streaming: ❌
- license: Apache-2.0

## Innovation

Inflect-Nano-v2's defining constraint is **completeness under 4M
parameters**: the entire text-to-waveform pipeline — no separate
vocoder, no phonemizer, no system dependencies — fits in 3.97M
deployable parameters and a 15.97 MB FP32 checkpoint. This is
smaller than even sanoTTS's smallest voice (745k) when measured
by *complete-pipeline* footprint, though sanoTTS ships per-voice
weights rather than a single fixed-voice checkpoint. The VITS
end-to-end architecture is the enabler: by folding the acoustic
model and vocoder into a single jointly-trained network, Inflect
avoids the multi-stage pipeline overhead that makes most neural
TTS systems larger. The public **adaptation toolkit** extends the
fixed-voice design into a customizable platform — users can
prepare data, adapt a voice or language, resume training, and
export PyTorch or ONNX packages — making the 4M-parameter
footprint a starting point for domain-specific TTS rather than a
dead-end fixed-voice release.
