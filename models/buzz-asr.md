---
release_date: "September 8, 2026"
model_name: "BuzzASR"
category: "asr"
summary: "Shivam Singh, Aditya Yadavalli, Catherine Arnett & Alex Warstadt (with EleutherAI) — a swarm of 102 monolingual Whisper-large-v3 fine-tunes, one per FLEURS language, in two recipes (plain SFT and full fine-tuning with a native tokenizer); beats Whisper-large-v3 zero-shot on 89 of 102 languages and reaches the lowest CER among open systems on up to 41 of them."
slug: "buzz-asr"
---

# BuzzASR

**BuzzASR** is a swarm of **102 monolingual speech recognizers** — one
fine-tune of [openai/whisper-large-v3](https://huggingface.co/openai/whisper-large-v3)
per FLEURS language, MIT-licensed and shipped as fp16 safetensors so each
drops into any standard Whisper pipeline. The project scales up two
language-adaptation recipes that had previously been tried on only a handful
of languages: **Simple (SFT)**, plain fine-tuning, and **Full (FFT)**, full
fine-tuning behind a **native tokenizer** whose embeddings are warm-started
from Whisper's before training. The native tokenizer is the crux — Whisper's
BPE was built for English-heavy data and shreds other languages into many
small pieces, so replacing it both **raises accuracy and shortens the token
stream**, which means FFT also decodes faster. Results: **89 of 102**
languages beat Whisper-large-v3 zero-shot on FLEURS-test CER (77 in the paper
with an average CER reduction of more than 2.8×), **31 of 102** hold the
lowest CER of every open system compared on FLEURS-test, and **41 of 102** on
the combined FLEURS + Common Voice set. Compression improves **3.3× on
average** in characters per token, up to **21.7×**.

## Links

- HuggingFace: https://huggingface.co/BuzzASR
- GitHub: https://github.com/lemn-lab/buzz-asr
- arXiv: https://arxiv.org/abs/2609.09554
- Website: https://lemn-lab.github.io/buzz-asr/

## Features

- languages: 102 (one monolingual model per FLEURS language)
- streaming: no
- license: MIT
- parameters: 1.5B per model (1,545,548,800 F16 in each safetensors checkpoint)
- base_model: openai/whisper-large-v3
- models_released: 102 (the best recipe per language, chosen on validation — never on test)
- recipes: Simple (SFT, plain fine-tuning) and Full (FFT, native tokenizer + fine-tuning)
- fft_tokenizer: language-native tokenizer replacing Whisper's English-heavy BPE, with embeddings warm-started from Whisper's
- compression_gain: 3.3× average improvement in characters per token, up to 21.7×
- results_vs_whisper_zs: 89/102 languages better on FLEURS-test CER (paper reports 77/102 with >2.8× average CER reduction)
- sota_open_systems: 31/102 lowest CER on FLEURS-test; 41/102 on FLEURS + Common Voice (paper counts 27/102 on the combined set)
- compared_against: Whisper-large-v3, Omnilingual 1B/7B, MMS-1B, Qwen3-ASR, Cohere
- decoding_speed: FFT emits fewer tokens than Whisper/SFT, so it finishes first at equal time-per-token
- usage: `WhisperForConditionalGeneration.from_pretrained("BuzzASR/<language>")` with `WhisperProcessor`
- prompt: language/task prompt baked into each model's generation config, so no `language=` argument is needed
- compute_partner: EleutherAI
- venue: Findings of EMNLP 2026
- format: fp16 safetensors, compatible with the standard Transformers Whisper path

## Comparison

- languages: 102
- streaming: ❌
- license: MIT

## Innovation

Most multilingual ASR work tries to make **one model cover everything**;
BuzzASR bets the opposite way and **mass-produces specialists**. The
contribution is not the idea — monolingual fine-tuning is old news — but the
demonstration that it holds up at **102-language scale** with a uniform,
reproducible recipe, which converts a folk practice into a baseline others
have to beat. The genuinely technical part is the **tokenizer swap**. Because
decode latency is token count × time-per-token, and because Whisper's
tokenizer fragments non-English text, a language-native tokenizer pays twice:
fewer tokens to emit *and* better accuracy from keeping whole morphemes. The
engineering trick that makes it cheap is **warm-starting the new tokenizer's
embeddings from Whisper's** before fine-tuning, so the model does not have to
relearn its input representation from scratch — that is what turns a
from-scratch tokenizer change into an incremental fine-tune. The reporting is
also notably careful: recipes are selected on validation and never on test,
and the project publishes both the FLEURS-test count (31) and the combined
FLEURS + Common Voice count (41) rather than quoting the flattering one
alone.
