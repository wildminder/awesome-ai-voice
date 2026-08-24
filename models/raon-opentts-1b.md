---
release_date: "May 21, 2026"
model_name: "Raon-OpenTTS-1B"
category: "tts"
summary: "KRAFTON — open-data, open-weight zero-shot English TTS (DiT / F5-TTS-style flow matching) trained on 510K curated hours; matches closed-data SOTA on Seed-TTS-Eval and CV3-Eval."
slug: "raon-opentts-1b"
---

# Raon-OpenTTS-1B

Raon-OpenTTS is an open-data, open-weight zero-shot TTS system from KRAFTON that performs on par with state-of-the-art closed-data models. This is the 1B variant (1048M parameters). Both model weights and training data are public: Raon-OpenTTS-Core is 510.1K hours of English speech, quality-filtered from the 615K-hour public Raon-OpenTTS-Pool using combined DNSMOS, WER, and VAD rank-based filtering. It ranks 1st or 2nd in WER and SIM among recent zero-shot TTS models on Seed-TTS-Eval and CV3-Eval, and achieves the best average WER/SIM on Raon-OpenTTS-Eval across Clean, Noisy, Wild, and Expressive regimes. A smaller [Raon-OpenTTS-0.3B](https://huggingface.co/KRAFTON/Raon-OpenTTS-0.3B) variant is also available.

## Links

- HuggingFace: https://huggingface.co/KRAFTON/Raon-OpenTTS-1B
- GitHub: https://github.com/krafton-ai/Raon-OpenTTS
- arXiv: https://arxiv.org/abs/2605.20830
- Dataset: https://huggingface.co/datasets/KRAFTON/Raon-OpenTTS-Pool

## Features

- voice_cloning: yes (zero-shot, robust across noisy/emotional/accented references)
- asr: no
- languages: English only (trained on 11 English speech datasets)
- license: CC BY-NC 4.0
- parameters: 1048M
- architecture: DiT (Diffusion Transformer) based on F5-TTS with flow matching; dim=1408, depth=28, heads=24
- audio_output: 80-ch mel-spectrogram at 16 kHz, HiFi-GAN vocoder (LibriTTS)
- training_data: Raon-OpenTTS-Core (510.1K hours), 520K updates on 48× B200

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English
- license: CC BY-NC 4.0

## Innovation

Demonstrates that fully open data + open weights can match proprietary SOTA: on Seed-TTS-Eval it reaches 1.78 WER / 0.749 SIM (vs Qwen3-TTS 1.46/0.715 at 1.7B), and best overall robustness (WER 2.81 / SIM 0.695) across four acoustic regimes on its own Raon-OpenTTS-Eval benchmark. The pipeline pairs large-scale rank-based data curation (DNSMOS + WER + VAD filtering of a 615K-hour pool) with an efficient F5-TTS-derived DiT.

## Additional Tools

| Tool | Type | Link |
|------|------|------|
| ComfyUI-Raon-OpenTTS | ComfyUI node | https://github.com/Saganaki22/ComfyUI-Raon-OpenTTS |
