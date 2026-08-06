---
release_date: "October 27, 2025"
model_name: "SYMPHONY"
category: "asr"
summary: "Okestro AI Lab — earlier general LLM-ASR design on Qwen3-4B with HFQ-Former audio frontend; superseded by SYMPHONY-ASR (Jan 12, 2026) as the ASR-specialized successor."
slug: "symphony"
---

# SYMPHONY

SYMPHONY is the earlier LLM-ASR design from Okestro AI Lab that pre-dates the ASR-specialized SYMPHONY-ASR. It uses the same Qwen3-4B backbone, an HFQ-Former audio frontend, and an audio-text-to-text interface for Korean + English. The model card self-identifies SYMPHONY-ASR as the `new_version`, and the SYMPHONY card itself is now minimal (auto-generated stub after the successor was published). Public WER numbers on the older release are slightly behind SYMPHONY-ASR — e.g. LibriSpeech-clean 2.26 vs 1.91, TedLium-3 3.97 vs 3.39.

## Links

- HuggingFace: https://huggingface.co/okestro-ai-lab/SYMPHONY
- Successor: https://huggingface.co/okestro-ai-lab/SYMPHONY-ASR

## Features

- parameters: 4B (Qwen3-4B backbone)
- languages: English, Korean
- streaming: no
- license: Apache-2.0
- architecture: HFQ-Former audio encoder + Qwen3-4B LLM adapter
- base_model: Qwen/Qwen3-4B
- pipeline_tag: audio-text-to-text
- status: superseded by SYMPHONY-ASR (Jan 12, 2026)

## Comparison

- languages: English, Korean
- streaming: ❌
- license: Apache-2.0

## Innovation

An earlier general-purpose LLM-ASR recipe (Qwen3-4B + HFQ-Former + Adapter) on the Korean + English bilingual target — preserved here as the version-history parent of the ASR-specialized SYMPHONY-ASR successor.
