---
release_date: "January 12, 2026"
model_name: "SYMPHONY-ASR"
category: "asr"
summary: "Okestro AI Lab — Korean+English ASR-specialized LLM-ASR built on Qwen3-4B with HFQ-Former audio encoder; ASR-focused architecture with long-form handling."
slug: "symphony-asr"
---

# SYMPHONY-ASR

SYMPHONY-ASR is Okestro AI Lab's ASR-specialized speech-recognition model built from the earlier SYMPHONY base. It is an LLM-ASR design using **Qwen3-4B** as the language head, an HFQ-Former audio frontend (hierarchically compressing high-frame-rate audio features), and an audio-text-to-text interface that supports both Korean and English in a single model. The architecture is deliberately ASR-specialized rather than multi-task, allowing it to land anywhere the standard long-form benchmarks (AMI, Earnings-22, GigaSpeech, LibriSpeech clean & other, VoxPopuli, TedLium-3, SPGI Speech) are tracked, with public WER numbers reported on the model card.

## Links

- HuggingFace: https://huggingface.co/okestro-ai-lab/SYMPHONY-ASR
- GitHub: (not stated on this card)
- Predecessor: https://huggingface.co/okestro-ai-lab/SYMPHONY

## Features

- parameters: 4B (Qwen3-4B backbone)
- languages: English, Korean
- streaming: no
- license: Apache-2.0
- architecture: HFQ-Former audio encoder + Qwen3-4B LLM adapter + ASR head
- base_model: Qwen/Qwen3-4B
- pipeline_tag: audio-text-to-text
- wer_benchmarks: AMI 9.56, Earnings-22 9.45, GigaSpeech 9.96, LS-clean 1.91, LS-other 4.43, VoxPopuli-en 6.30, TedLium-3 3.39, SPGI 2.29

## Comparison

- languages: English, Korean
- streaming: ❌
- license: Apache-2.0

## Innovation

An ASR-specialized cut of LLM-ASR (Qwen3-4B backbone + HFQ-Former + Adapter) that explicitly trades generalist audio-text flexibility for tighter ASR performance: pinned public WER scores across the canonical long-form English benchmarks plus Korean support in the same model.
