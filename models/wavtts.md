---
release_date: "May 28, 2026"
model_name: "WavTTS"
category: "tts"
summary: "Chen et al. — end-to-end zero-shot TTS that generates speech directly in the raw waveform space, bypassing mel/VAE/codec tokens via a flow-matching DiT with multi-scale mel supervision."
slug: "wavtts"
---

# WavTTS

WavTTS is an end-to-end zero-shot TTS framework that synthesizes speech directly in the raw waveform space — explicitly skipping the intermediate mel-spectrogram, VAE-latent, or codec-token representations that most modern TTS stacks use. It is built on a flow-matching diffusion transformer (DiT) with waveform patchification, multi-scale mel-spectrogram supervision, and an optimized noise schedule. Forked from F5-TTS at the codebase level but replaces the whole acoustic pipeline.

## Links

- HuggingFace: https://huggingface.co/worstchan/WavTTS
- GitHub: https://github.com/cwx-worst-one/WavTTS
- Demo: https://wavtts.github.io/
- Paper: https://arxiv.org/abs/2606.03455

## Features

- voice_cloning: yes (zero-shot, prompt audio + reference transcript)
- asr: no
- languages: English, Chinese
- streaming: no
- license: CC BY-NC 4.0 (weights; CC-BY-NC-4.0 due to Emilia dataset license) / MIT (codebase)
- sample_rate: 16 kHz
- training_data: Emilia
- architecture: Flow-matching DiT, raw waveform patchification, multi-scale mel supervision
- training_steps: 1.2M

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English, Chinese
- streaming: ❌
- license: CC BY-NC 4.0

## Innovation

Skip every intermediate waveform representation (no mel, no VAE, no codec tokens): a flow-matching DiT produces raw-waveform patches directly, supervised at multiple mel scales and an optimized noise schedule — yielding high-quality zero-shot TTS at 16 kHz from a single end-to-end stack.
