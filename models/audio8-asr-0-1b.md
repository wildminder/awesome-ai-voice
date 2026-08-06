---
release_date: "July 10, 2026"
model_name: "Audio8-ASR-0.1B"
category: "asr"
summary: "Audio8 (AutoArk-AI) — Audio8-ASR-0.1B: a compact autoregressive ASR model with only 0.1B LM parameters; multilingual (Chinese/English/French/German/Japanese/Korean/Cantonese); Open ASR Leaderboard composite WER 7.03% at RTFx 741 on H200; ships ONNX Runtime (~1.1 GB peak) and iOS ANE (~200 MB peak) deployment variants for edge and on-device transcription."
slug: "audio8-asr-0-1b"
---

# Audio8-ASR-0.1B

**Audio8-ASR-0.1B** is a compact autoregressive ASR model whose
language-model component has only **0.1B parameters**. It supports
multilingual speech recognition for **Chinese, English, French,
German, Japanese, Korean, and Cantonese**. The project positions
it as **one of the smallest usable performance ASR models in the
LLM era** — and backs that claim with Open ASR Leaderboard results:
a **composite WER of 7.03%** across seven English splits at
**RTFx 741.15** on H200 (LibriSpeech test-clean 2.70%, GigaSpeech
8.48%, AMI 10.99%, Earnings22 12.31%). On Chinese internal evals
it reports CER 8.84% (WenetSpeech meeting) and 7.98% (WenetSpeech
net).

Three deployment-focused releases ship alongside the base
Transformers checkpoint:

- **ONNX Runtime** — edge-device deployment, ~1.1 GB peak memory.
- **iOS ANE** — local iPhone transcription, ~200 MB peak runtime
  memory.
- **Base Transformers** — the HuggingFace checkpoint with custom
  `arkasr` remote code.

The model shares its paper (arXiv 2605.28139) and training code
(`AutoArk/open-audio-opd`) with the larger **ARK-ASR-3B** sibling.

## Links

- HuggingFace: https://huggingface.co/Audio8/Audio8-ASR-0.1B
- GitHub: https://github.com/AutoArk/open-audio-opd
- Paper: https://arxiv.org/abs/2605.28139
- Demo: https://huggingface.co/spaces/Audio8/audio8-asr-0-1b

## Features

- parameters: 0.1B (LM component)
- asr: yes (autoregressive; custom `arkasr` remote code)
- languages: Chinese, English, French, German, Japanese, Korean, Cantonese (7)
- streaming: no (offline utterance transcription; 30-second audio chunks per Open ASR Leaderboard protocol)
- license: CC BY-NC 4.0
- architecture: autoregressive ASR (Whisper-style encoder + MLP adapter + Qwen decoder, per shared paper)
- pipeline_tag: automatic-speech-recognition
- library_name: transformers (custom_code)
- open_asr_leaderboard_composite_wer: 7.03%
- open_asr_leaderboard_rtfx: 741.15 (H200, BF16, eager attention, greedy decoding)
- eval_librispeech_clean: WER 2.70%
- eval_librispeech_other: WER 6.59%
- eval_gigaspeech_clean: WER 8.48%
- eval_ami_cleaned: WER 10.99%
- eval_earnings22: WER 12.31%
- eval_spgispeech: WER 3.73%
- eval_voxpopuli: WER 4.39%
- eval_wenetspeech_meeting: CER 8.84%
- eval_wenetspeech_net: CER 7.98%
- deployment_variants: ONNX Runtime (~1.1 GB peak), iOS ANE (~200 MB peak), base Transformers
- hotword_support: yes (tagged in HF metadata)
- companion_model: ARK-ASR-3B (3B-scale sibling, same paper + repo)
- createdAt: 2026-07-10T06:57:05Z
- downloads: ~527

## Comparison

- languages: 7
- streaming: ❌
- license: CC BY-NC 4.0

## Innovation

Audio8-ASR-0.1B's pitch is **usable ASR quality at 0.1B LM
parameters** — a scale where most LLM-era ASR systems are either
too large for edge deployment or too low-quality for production.
The composite WER of 7.03% on the Open ASR Leaderboard (with
LibriSpeech clean at 2.70%) demonstrates that a 0.1B-parameter
autoregressive decoder, paired with a Whisper-style encoder and
MLP adapter, can hit competitive accuracy. The deployment-variant
strategy is the other half of the story: the same model ships as
**ONNX Runtime** (~1.1 GB peak for edge devices) and **iOS ANE**
(~200 MB peak for local iPhone transcription) — the latter being
a footprint that makes on-device ASR practical on consumer phones
without server roundtrips. The **hotword** support (tagged in HF
metadata) adds contextual biasing for domain-specific vocabulary,
which is critical for meeting / medical / legal transcription at
this parameter scale.
