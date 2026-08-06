---
release_date: "July 14, 2026"
model_name: "GigaAM-Multilingual"
category: "asr"
summary: "ai-sage (Sber) — Conformer-based multilingual ASR foundation (220M / 600M variants) pretrained with a HuBERT-style objective on 2M hours across 70+ languages and character-wise-CTC fine-tuned on 50K hours; best-in-class open quality on Russian / Kazakh / Kyrgyz / Uzbek."
slug: "gigaam-multilingual"
---

# GigaAM-Multilingual

**GigaAM Multilingual** is a family of Conformer-based ASR
foundation models from ai-sage (Sber). Two parameter scales ship
(`ssl` / `ctc` at 220M and `large_ssl` / `large_ctc` at 600M).
The encoder is pretrained with a HuBERT-style self-supervised
objective on **2M hours** of speech across **70+ languages**,
then fine-tuned for speech recognition with character-wise CTC
decoders on 50K hours. The `ssl`/`large_ssl` variants are
encoder-only checkpoints for downstream fine-tuning; the
`ctc`/`large_ctc` variants add a character-wise CTC decoder ready
for inference. The model reports best-in-class open-source quality
on Russian, Kazakh, Kyrgyz, and Uzbek ASR, and moderate quality
on English — beating Seamless M4T large v2 and Omnilingual 1B on
Russian Common Voice (7.1%/5.1% WER vs 9.2%/13.6%). A live demo
Space is hosted at
[hugging-apps/gigaam-multilingual-asr](https://huggingface.co/spaces/hugging-apps/gigaam-multilingual-asr).

## Links

- HuggingFace: https://huggingface.co/ai-sage/GigaAM-Multilingual
- Paper: https://arxiv.org/abs/2607.10371
- Demo: https://huggingface.co/spaces/hugging-apps/gigaam-multilingual-asr

## Features

- parameters: 220M (`ssl` / `ctc`); 600M (`large_ssl` / `large_ctc`)
- asr: yes (character-wise CTC decoder)
- languages: 70+ pretrained, fine-tuned for ru / en / kk / ky / uz
- streaming: no (offline utterance inference; up to 30 s per HF Space)
- license: MIT
- architecture: Conformer encoder + (optional) character-wise CTC decoder
- pretraining_objective: HuBERT-style self-supervised
- pretraining_hours: 2,000,000 hours
- fine_tuning_hours: 50,000 hours
- variants: ssl (encoder-only), ctc (encoder + CTC decoder), large_ssl (600M encoder-only), large_ctc (600M + CTC decoder)
- evaluation_cv_russian: WER 7.1% (220M) / 5.1% (600M)
- evaluation_cv_kazakh: best-in-class (see paper)
- evaluation_fleurs_english: WER 12.2% (220M) / 9.4% (600M)
- training_library: pytorch, custom_code

## Comparison

- languages: 70+
- streaming: ❌
- license: MIT

## Innovation

Two things set GigaAM-Multilingual apart from prior multilingual
ASR foundation work. First, the scale of pretraining — **2M hours
across 70+ languages** under a HuBERT-style self-supervised
objective — paired with a *character-wise* CTC decoder fine-tune
(no word-piece lexicon dependency) lets a single checkpoint cover
languages with very different phonotactics and orthographies
(Turkic + Slavic + Indo-Aryan families) without a language-tagged
decoding head per family. Second, the **two-tier release** — encoder-only
(`ssl`/`large_ssl`) for downstream fine-tuning and encoder+CTC
(`ctc`/`large_ctc`) ready for inference — gives the community both
a drop-in recognizer and a foundation for task-specific adaptation.
On Russian Common Voice it beats Seamless M4T large v2 and
Omnilingual 1B, the closest open baselines.
