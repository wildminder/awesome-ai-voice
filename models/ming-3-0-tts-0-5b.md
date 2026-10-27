---
release_date: "October 19, 2026"
model_name: "Ming-3.0-tts-0.5B"
category: "tts"
summary: "inclusionAI (Ant Ling) — dense 0.5B multilingual TTS with zero-shot cloning, text-described voice design, 14 inline paralinguistic tags, dialect control and free-form delivery instructions at 44.1 kHz."
slug: "ming-3-0-tts-0-5b"
---

# Ming-3.0-tts-0.5B

Ming-3.0-tts-0.5B is the dense half of inclusionAI's Ming-3.0-tts family: a 0.5B speech-generation model on a Qwen2.5-0.5B backbone, shipped as a single 1.48B-parameter checkpoint (safetensors-measured 1,479,454,868 in BF16) that bundles the backbone, a DiT patch head, an AudioVAE audio tokenizer inherited from the Ming-2.0 generation, a CAM++ speaker encoder and the text tokenizer. Output is 44.1 kHz. It speaks seven languages — Chinese, English, German, Spanish, French, Korean and Japanese — plus Sichuanese and Cantonese dialects, and exposes control as **task modes rather than arbitrary combinations**: zero-shot cloning from a reference clip, voice design from a natural-language description, free-form delivery instructions, 14 inline paralinguistic tags (breath, cough, sigh, laughter, hesitation, surprise, question and confirmation sounds, in Chinese or English), explicit emotion, speed/pitch/volume attributes, and built-in IP voices (100+ Chinese, five English; recommended US_James, US_Stella, 灵小柔, 灵楷). On the independent Artificial Analysis leaderboards (October 2026) it ranks **1st among open-weights models on Controlled Voice** (Elo 1069) and **1st overall on Pronunciation Robustness** (93.2%). It is MIT-licensed, with the technical report still pending; the honest weak spot is speaker similarity, which trails content accuracy across every language.

## Links

- HuggingFace: https://huggingface.co/inclusionAI/Ming-3.0-tts-0.5B
- GitHub: https://github.com/inclusionAI/Ming-3.0-tts
- Website: https://nomorecoding.github.io/Ming-3.0-tts/
- ModelScope: https://modelscope.cn/models/inclusionAI/Ming-3.0-tts-0.5b
- Predecessor: https://huggingface.co/inclusionAI/Ming-omni-tts-16.8B-A3B

## Features

- parameters: 1,479,454,868 (0.5B dense backbone + AudioVAE + DiT head + aggregator, safetensors-measured, BF16)
- voice_cloning: yes (zero-shot from a reference clip; CAM++ speaker embedding)
- asr: no
- languages: 7 (Chinese, English, German, Spanish, French, Korean, Japanese) + Sichuanese and Cantonese dialects
- license: MIT
- architecture: dense Qwen2.5-0.5B backbone + DiT patch head + AudioVAE audio tokenizer (Qwen2-style, 24 layers, hidden 896) + CAM++ speaker encoder (BailingMMNativeForConditionalGeneration)
- sample_rate: 44.1 kHz
- controls: emotion (7 categories), speed/pitch/volume, dialect, free-form natural-language instruction, text-described voice design
- paralinguistic_tags: 14 (breath, cough, sigh, laughter, hesitation, surprise, question/confirmation — Chinese or English)
- built_in_voices: 100+ Chinese, 5 English (recommended US_James, US_Stella, 灵小柔, 灵楷)
- tasks: TTS, FREEFORM, VOICE_DESIGN, MULTILINGUAL, BASIC, EMOTION, DIALECT, IP (task modes are mutually exclusive)
- text_normalization: FST grammars via pynini (--no_text_normalization to skip)
- sibling_model: Ming-3.0-tts-tiny (MoE on Ling V3, 7.9B total / 1.3B active) adds multi-speaker podcast synthesis
- seed_tts_zh: WER 0.800% / SIM 0.758 (Seed-TTS reference 1.110% / 0.796; 3rd on Chinese WER among compared open models)
- seed_tts_en: WER 1.584% / SIM 0.691
- multilingual_minimax: German 0.365% WER, Spanish 1.099% WER, French 4.264% WER (SIM 0.675), Korean 1.728% CER, Japanese 3.765% CER
- nvbench_single: zh CER 2.70 / PCER 22.80 / OCER 3.20; en CER 7.60 / PCER 37.00 / OCER 8.90 (SOTA on all six single-tag metrics jointly with tiny)
- dialect_wsc: easy CER 2.27% (SOTA) / SIM 0.689 / ACC 80.68%; hard CER 3.35% / SIM 0.691 / ACC 87.64%
- emotion_cv3: 72.33% average (3rd); emotion_cv3n: 37.33% average (2nd)
- voice_design_instructtts: 72.29% average (3rd; APS 78.54, DSD 77.28, RP 61.06)
- attribute_control: speed 99% / volume 95% / pitch 86% (avg 93.30%, leads the compared set), WER 0.317%, SIM 0.712
- leaderboard_aa: Controlled Voice 1069 (1st open-weights, 13th overall), Pronunciation Robustness 93.2% (1st overall), Provider Voice 1188 (3rd open-weights, 17th overall) — October 2026
- runtime: transformers 4.46.3, torch 2.6 / CUDA 12.4 Docker image, vLLM-Omni accelerated inference
- sampling: cfg_scale 2.0, temperature 0, flow_steps 10, sigma 0.25, seed 1234
- hardware: tested on NVIDIA H800-80GB and H20-96G
- limitations: speaker similarity weaker than content accuracy (French SIM is the clearest gap); pitch less accurate than speed and volume; emotion control harder when the words carry no emotional signal; open-ended voice design still behind Qwen3-TTS; technical report pending

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 7
- license: MIT

## Innovation

The interesting part is not the model size but the **control surface**: a 0.5B dense checkpoint that exposes voice cloning, text-described voice design, free-form delivery instructions, 14 inline paralinguistic tags, dialect selection and explicit emotion/attribute controls as distinct task modes, with the modes deliberately non-composable so a request never mixes incompatible conditioning. That design is what produces SOTA single-tag paralinguistic accuracy (zh CER 2.70) and SOTA Cantonese base CER (6.15% with 98.00% accuracy) from a model small enough for a single H800, and the independent arena results back it up — first among open-weights models on Controlled Voice and first overall on Pronunciation Robustness, where text normalization (96.5% on Expanding Shorthand) and sequence fidelity (90.6%) are the deciding axes. The honest caveat is that content accuracy and speaker similarity move independently here: intelligibility is excellent, voice identity is the weaker half, and the older Ming-omni-tts still holds the overall records for attribute-control accuracy, pitch and similarity.
