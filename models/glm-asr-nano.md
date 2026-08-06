---
release_date: "December 9, 2025"
model_name: "GLM-ASR-Nano-2512"
category: "asr"
summary: "Zhipu AI (zai.org) — 1.5B-parameter open-source ASR foundation model that outperforms Whisper V3 on multiple benchmarks while supporting 17 languages (WER ≤ 20%) and showing exceptional robustness on Cantonese and other dialects plus low-volume / quiet-speech scenarios; lowest average error rate (4.10) among comparable open ASR models."
slug: "glm-asr-nano"
---

# GLM-ASR-Nano-2512

**GLM-ASR-Nano-2512** is a 1.5B-parameter open-source speech
recognition model from Zhipu AI. The "Nano" model is built for
real-world complexity: it produces the **lowest average error rate
(4.10)** among comparable open-source ASR models while keeping the
checkpoint at the compact 1.5B scale. Key capabilities:

* **Exceptional dialect support** — beyond standard Mandarin and
  English, the model is highly optimized for **Cantonese (粤语)**
  and other regional Chinese dialects, a capability gap most prior
  ASR systems leave untouched.
* **Low-volume / quiet-speech robustness** — specifically trained
  for "Whisper/Quiet Speech" scenarios, the model captures and
  accurately transcribes extremely low-volume audio that traditional
  ASR often misses.
* **17 languages supported** with WER ≤ 20%, with the strongest
  advantage on Chinese benchmarks (Wenet Meeting, Aishell-1).
* Outperforms OpenAI Whisper V3 on multiple benchmarks despite
  being much smaller.

The model integrates with HuggingFace `transformers` (v4.x, with
planned support for v5.x, vLLM, and SGLang), ships as a
`GlmAsrForConditionalGeneration` AutoModel with a custom processor,
and accepts both audio URLs and raw arrays. Multiple HF Spaces
host live demos of the model (e.g. `YatharthS/GLM-ASR-Nano`).

## Links

- HuggingFace: https://huggingface.co/zai-org/GLM-ASR-Nano-2512
- GitHub: https://github.com/zai-org/GLM-ASR
- Demo: https://huggingface.co/spaces/YatharthS/GLM-ASR-Nano

## Features

- parameters: 1.5B
- asr: yes (causal LLM-style seq2seq; AutoModelForSeq2SeqLM and GlmAsrForConditionalGeneration)
- languages: 17 supported (WER ≤ 20%); Mandarin, English, Cantonese specially optimized
- streaming: no (offline utterance transcription; transformers v5 + vLLM/SGLang integration planned)
- license: MIT
- architecture: speech-encoder + text decoder (transformers framework)
- WER_avg: 4.10 (lowest among comparable open-source ASR)
- benchmarks: Wenet Meeting (real-world meeting scenarios, noise / overlapping speech); Aishell-1 (Mandarin)
- licensed_channels: Hugging Face, ModelScope
- companion_repo: https://github.com/zai-org/GLM-ASR
- inference_lib: transformers (v4.x from source; v5 support planned; vLLM, SGLang planned)
- input_modes: audio URL (via processor.apply_transcription_request) or raw audio arrays
- download_count: ~150k (as of mid-2026)
- model_class: GlmAsrForConditionalGeneration (custom_code) / AutoModelForSeq2SeqLM
- demo_spaces: YatharthS/GLM-ASR-Nano, Pevernow/GLM-ASR-Nano, yakoudev/GLM-ASR-Nano, naicoi/GLM-ASR-Nano

## Comparison

- languages: 17
- streaming: ❌
- license: MIT

## Innovation

Two design decisions set GLM-ASR-Nano apart from the Whisper-V3
class of multilingual ASR. First, **explicit dialect-support
training**: rather than treating dialectal Mandarin as noise to be
suppressed, the model was tuned for Cantonese and other regional
variants as first-class targets — a capability gap that most prior
ASR systems left untouched. Second, **specifically trained
robustness on low-volume / quiet-speech audio** — the regime where
conventional ASR often falls back on aggressive denoising that
removes the very signal the model needs. The result: the lowest
average error rate (4.10) among comparable open-source ASR models,
with the strongest advantage on Chinese benchmarks (Wenet Meeting,
Aishell-1) — in a 1.5B-parameter checkpoint that integrates
directly with the `transformers` v4.x / v5.x stack.
