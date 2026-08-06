---
release_date: "June 22, 2026"
model_name: "ARK-ASR-3B"
category: "asr"
summary: "Audio8 (AutoArk-AI) — ARK-ASR-3B: a 3B-scale multilingual ASR model achieving current state-of-the-art on the Hugging Face Open ASR Leaderboard English short-form benchmark (avg WER 5.04%, RTFx 490.98); Whisper-style encoder + MLP adapter + Qwen decoder with custom arkasr code; supports 19 languages including Chinese, English, German, Japanese, French, Korean, Spanish, Polish, Italian, Romanian, Hungarian, Czech, Dutch, Finnish, Croatian, Slovak, Slovene, Estonian, Lithuanian."
slug: "ark-asr-3b"
---

# ARK-ASR-3B

**ARK-ASR-3B** is a 3B-scale audio-capable autoregressive
Transformers model for automatic speech recognition. It achieves
**current state-of-the-art results on the Hugging Face Open ASR
Leaderboard English short-form benchmark**, with an average WER of
**5.04%** and RTFx of **490.98** across AMI, Earnings22,
GigaSpeech, LibriSpeech, SPGISpeech, and VoxPopuli. On Chinese
benchmarks it reports CER 1.80% (AISHELL-1), 4.97% (WenetSpeech
test meeting), and 4.58% (WenetSpeech test-net).

The architecture combines a **Whisper-style audio encoder** (with
RoPE), an **MLP adapter**, and a **Qwen decoder** with custom
`arkasr` remote code. Audio is encoded by the Whisper-style
encoder, merged through the MLP adapter, and injected into the
Qwen decoder by replacing audio placeholder token embeddings
before transcript generation. The model supports **19 languages**:
Chinese, English, German, Japanese, French, Korean, Spanish, Polish,
Italian, Romanian, Hungarian, Czech, Dutch, Finnish, Croatian,
Slovak, Slovene, Estonian, and Lithuanian. Inference runs via
HuggingFace Transformers (`trust_remote_code=True`) or **vLLM**
serving. Input audio is **16 kHz**.

The model shares its paper (arXiv 2605.28139) and training code
(`AutoArk/open-audio-opd`) with the smaller **Audio8-ASR-0.1B**
sibling.

## Links

- HuggingFace: https://huggingface.co/Audio8/ARK-ASR-3B
- GitHub: https://github.com/AutoArk/open-audio-opd
- Paper: https://arxiv.org/abs/2605.28139
- Demo: https://huggingface.co/spaces/Audio8/ark-asr-3b

## Features

- parameters: 3B (decoder LLM + Whisper-style encoder + MLP adapter)
- asr: yes (autoregressive; custom `arkasr` remote code)
- languages: 19 (Chinese, English, German, Japanese, French, Korean, Spanish, Polish, Italian, Romanian, Hungarian, Czech, Dutch, Finnish, Croatian, Slovak, Slovene, Estonian, Lithuanian)
- streaming: no (offline utterance transcription; vLLM serving available for batch)
- license: Apache-2.0
- architecture: Whisper-style audio encoder (RoPE) + MLP adapter + Qwen decoder
- pipeline_tag: automatic-speech-recognition
- library_name: transformers (custom_code); vLLM serving supported
- input_sample_rate: 16,000 Hz
- checkpoint_format: safetensors
- open_asr_leaderboard_avg_wer: 5.04% (current SOTA on English short-form)
- open_asr_leaderboard_rtfx: 490.98
- eval_ami: WER 8.79%
- eval_earnings22: WER 8.23%
- eval_gigaspeech: WER 6.98%
- eval_librispeech_clean: WER 1.03%
- eval_librispeech_other: WER 2.35%
- eval_spgispeech: WER 2.46%
- eval_voxpopuli: WER 5.47%
- eval_aishell1: CER 1.80%
- eval_wenetspeech_meeting: CER 4.97%
- eval_wenetspeech_net: CER 4.58%
- companion_model: Audio8-ASR-0.1B (0.1B-scale sibling, same paper + repo)
- createdAt: 2026-06-22T07:04:45Z
- downloads: ~7,109

## Comparison

- languages: 19
- streaming: ❌
- license: Apache-2.0

## Innovation

ARK-ASR-3B's headline result is **5.04% average WER on the Open
ASR Leaderboard** — the current state of the art on that benchmark
at the time of release, beating the project's own 0.6B variant
(5.97%) and prior open ASR systems. The architecture is a
straightforward but well-tuned combination: a **Whisper-style
encoder with RoPE** (proven audio representation), an **MLP adapter**
(dimension bridging), and a **Qwen decoder** (strong multilingual
text LLM). The key design choice is **injecting audio embeddings
by replacing audio placeholder token embeddings in the Qwen
decoder** before transcript generation — this lets the model
inherit the Qwen LLM's multilingual text capability (19 languages
including low-resource Baltic and Slavic languages) while adding
speech input through a minimal-modification adapter rather than
a full architecture redesign. The **vLLM serving** support makes
the 3B model practical for production batch transcription, and
the shared training repo (`AutoArk/open-audio-opd`) with the 0.1B
sibling lets users trade accuracy for footprint on the same code
base.
