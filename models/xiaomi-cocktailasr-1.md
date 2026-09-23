---
release_date: "September 10, 2026"
model_name: "Xiaomi-CocktailASR-1"
category: "asr"
summary: "Xiaomi — a target-speaker ASR SpeechLLM that takes a reference voiceprint clip plus mixed audio and transcribes only the target speaker, without speech separation; adds negative-sample rejection and chain-of-thought reasoning, and reaches SOTA on AliMeeting / AMI / LibriMix-style benchmarks while staying competitive with mainstream single-speaker ASR."
slug: "xiaomi-cocktailasr-1"
---

# Xiaomi-CocktailASR-1

**Xiaomi-CocktailASR-1** is a **target-speaker ASR (TS-ASR) SpeechLLM**.
Given a reference clip of the speaker you want and either mixed or
single-speaker audio, it transcribes **only that speaker** — using the
reference as a **voiceprint prompt**, with no explicit speech separation
stage. It is built on large-scale multi-speaker data and addresses the two
failure modes the paper calls out in prior TS-ASR work: **degraded
single-speaker accuracy** (a dedicated TS-ASR model that breaks on ordinary
audio) and **the inability to reject** when the target speaker is absent.
Xiaomi-CocktailASR-1 does both in one architecture — it stays comparable to
mainstream ASR on single-speaker sets, and it outputs **empty text** when the
reference speaker is not in the mixture. It also supports a **Chain-of-Thought
mode** that emits explicit reasoning steps. On simulated multi-speaker
benchmarks it reaches **4.11% WER** on LibriMix 2mix and **2.90%** on
LibriSpeechMix 2mix, where Qwen3-ASR scores 68.75% and 92.17% respectively.

## Links

- HuggingFace: https://huggingface.co/Ease3/Xiaomi-CocktailASR-1
- GitHub: https://github.com/xiaomi-research/xiaomi-cocktailasr-1
- arXiv: https://arxiv.org/abs/2609.11274

## Features

- languages: Chinese, English
- streaming: no
- license: Apache-2.0
- architecture: MicAsrModel SpeechLLM — inline D2V2 audio encoder + adapter + LLM, loaded via `trust_remote_code`
- parameters: not stated (single `pytorch_model.bin` holding D2V2 + adapter + LLM)
- input: reference speaker clip + target audio, auto-concatenated internally as reference + 1 s silence + target
- audio_format: 16 kHz mono (other rates are resampled automatically)
- capabilities: target-speaker ASR, negative-sample rejection, chain-of-thought reasoning
- cot: `<think>...</think>` reasoning plus `<answer>...</answer>` output, enabled with `cot=True`
- wer_librimix: 2mix 4.11 / 3mix 12.29
- wer_librispeechmix: 2mix 2.90 / 3mix 4.91
- wer_real_multispeaker: AMI SDM 21.81 / AliMeeting Far 20.63
- wer_single_speaker: LibriSpeech 1.73 / AliMeeting-near 6.57 / AMI-ihm 8.89 / WenetSpeech-meeting 5.81 / CommonVoice-zh 4.95
- frr_single_speaker: LibriSpeech 0.36 / AliMeeting-near 0.38 / AMI-ihm 0.01 / WenetSpeech 0 / CommonVoice-zh 0.73
- negative_rejection_rate: LibriSpeech neg 79.59 / Aishell neg 75.35 / Chinese in-house neg 68.54
- cot_gain: LibriMix 2mix 4.11 → 3.87 WER with CoT
- baselines_beaten: Qwen3-ASR, Gemini, StepAudio, Whisper Large-v2, SQ-Whisper, prior Conformer TS-ASR
- usage: `AutoModel.from_pretrained("Ease3/Xiaomi-CocktailASR-1", trust_remote_code=True, torch_dtype="bfloat16")` then `model("target.wav", "ref_speaker.wav")`
- batch: `tools/test_batch_scp.py` over a 5-column TSV, with `--cot` for reasoning mode
- runtime: `pip install torch torchaudio transformers soundfile`
- weights_host: HuggingFace repo `Ease3/Xiaomi-CocktailASR-1` (linked from the official xiaomi-research repo)
- upstream_license: Apache-2.0 per the xiaomi-research repository LICENSE

## Comparison

- languages: Chinese, English
- streaming: ❌
- license: Apache-2.0

## Innovation

The architectural bet is **prompt-based speaker conditioning instead of
separation**: rather than running a speech-separation front-end and then
transcribing the extracted stream, Xiaomi-CocktailASR-1 feeds the reference
voiceprint into the LLM's prompt path and lets attention do the selection, so
one model serves both cocktail-party and ordinary single-speaker audio with
no model switch. That unification is the point — the paper's complaint about
prior TS-ASR is precisely that specializing for mixtures *costs* you
single-speaker accuracy, and the single-speaker numbers here (1.73% on
LibriSpeech, 8.89% on AMI-ihm) sit alongside mainstream ASR rather than
behind it. The second, less common capability is **negative-sample
rejection**: because the model can emit empty output when the reference
speaker is absent, it becomes usable as a *verification* component — 79.59%
rejection on LibriSpeech negative pairs, where Qwen3-ASR and StepAudio score
0%. That is not free, and the report is candid about the cost: rejection
introduces a small **false-rejection rate** on true positives (0.36% on
LibriSpeech, 0.73% on CommonVoice-zh), which is why FRR is published next to
every WER number. CoT mode adds interpretability and a small accuracy gain
(4.11 → 3.87 WER on LibriMix 2mix) but not a transformation — the honest
framing for a reasoning mode whose value is legibility rather than raw score.
