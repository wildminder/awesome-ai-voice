---
release_date: "August 27, 2026"
model_name: "Ruby-ASR-1.7B"
category: "asr"
summary: "Hao Shi et al. (hshi-speech) — Japanese fine-tunes of Qwen3-ASR-1.7B that emit transcripts with inline furigana, supervised by a span-bound orthography-to-reading target so pronunciation is learned from audio instead of guessed by post-hoc G2P; an auxiliary mora-level CTC head reads the actual kana pronunciation straight off the encoder."
slug: "ruby-asr-1-7b"
---

# Ruby-ASR-1.7B

**Ruby-ASR-1.7B** is a pair of Japanese fine-tunes of
[Qwen/Qwen3-ASR-1.7B](https://huggingface.co/Qwen/Qwen3-ASR-1.7B) that
**carry their own pronunciation evidence**. The standard Japanese ASR target
is an orthographic transcript, but the same written span can be realized with
different readings — so acoustically different utterances get identical
targets, and the reading distinction is destroyed before the model ever sees
it. Ruby-ASR refines the target into a **span-bound orthography↔reading
sequence**, binding each written span to the reading actually realized in
speech (`七[なな]年間[ねんかん]でロスにも友達[ともだち]できたし、`), which
lets both the orthographic and the lexical-reading view be recovered
deterministically. Two variants ship in the repo: **Ruby-ASR-sub**
(`subtitle/`, subtitle-style) and **Ruby-ASR-ver** (`verbatim/`). Each adds
**two complementary outputs**: (1) the ruby transcript with inline furigana,
and (2) a **mora reading produced by CTC directly from the audio encoder** —
no LLM decoding at all. On a character-count-weighted average over B5K, CSJ,
JSUT-Book, Common Voice 8 and TEDx, Ruby-ASR-sub posts the best **Raw CER at
8.51%** (21.1% relative below Qwen3-ASR) and Ruby-ASR-ver the best **SA-CER
at 6.59%** and **Kana CER at 3.75%** (23.3% and 34.7% relative reductions).

## Links

- HuggingFace: https://huggingface.co/hshispeech/Ruby-ASR-1.7B
- arXiv: https://arxiv.org/abs/2609.27289
- GitHub: https://github.com/hshi-speech/Ruby-ASR-1.7B

## Features

- parameters: 1.7B (fine-tune of Qwen3-ASR-1.7B; weights shipped as a stock Qwen3-ASR checkpoint)
- languages: Japanese only (ja)
- streaming: no (no streaming mode documented)
- license: Apache-2.0 (same as the Qwen3-ASR base model)
- base_model: Qwen/Qwen3-ASR-1.7B
- variants: Ruby-ASR-sub (`subtitle/` — concise orthographic transcription) and Ruby-ASR-ver (`verbatim/` — script-aware and lexical-reading accuracy)
- output_modes: Mode 1 mora reading via encoder + CTC (no LLM decoding); Mode 2 ruby transcription with inline furigana
- ruby_output: every annotated word carries its reading, e.g. `七[なな]年間[ねんかん]でロスにも友達[ともだち]できたし、`
- mora_output: actual pronunciation as katakana morae, e.g. `ナナネンカンデロスニモトモダチデキタシ`
- mora_alphabet: katakana morae (キョ, ッ, ン, ー are single tokens) plus a–z for embedded English; long vowels unified to ー per the pyopenjtalk `g2p(kana=True)` convention
- ctc_branch: 2-layer Transformer adapter (nhead 8) + linear head on the audio encoder, trained jointly with CTC loss, stored separately under `ctc/`
- training_objective: joint loss 0.3·CTC + 0.7·CE (cross-entropy over the ruby transcript plus CTC over mora targets)
- decoupled_paths: the seq2seq path never sees the CTC adapter, so ruby decoding is bit-identical to a checkpoint without the branch
- benchmarks: character-count-weighted averages over B5K, CSJ, JSUT-Book, Common Voice 8 and TEDx
- raw_cer: Ruby-ASR-sub 8.51 (best) / Ruby-ASR-ver 9.10 / ReazonSpeech-k2 10.35 / Qwen3-ASR-1.7B 10.78
- sa_cer: Ruby-ASR-ver 6.59 (best) / Ruby-ASR-sub 6.64 / ReazonSpeech-k2 8.51 / Qwen3-ASR-1.7B 8.59
- kana_cer: Ruby-ASR-ver 3.75 (best) / Ruby-ASR-sub 4.01 / Kana-Whisper 4.66 / Qwen3-ASR-1.7B 5.74
- relative_gains: 21.1% Raw CER below Qwen3-ASR (sub); 23.3% SA-CER and 34.7% Kana CER below Qwen3-ASR (ver); 19.5% Kana CER below Kana-Whisper (ver)
- metric_definitions: Raw CER (orthographic, original script); SA-CER (kana scored by reading, kanji by orthography); Kana CER (lexical-reading transcription)
- serving: unmodified vLLM (>= 0.14) or the official qwen-asr toolkit for Mode 2; the ruby_asr package for Mode 1
- postprocessing: `to_surface`, `to_reading`, `to_html`, `brackets_to_parens` helpers emit plain text, kana-only text or HTML `<ruby>` markup
- vllm_note: use /v1/chat/completions, not /v1/audio/transcriptions — the transcriptions endpoint builds a different prompt and returns brackets-free text
- limitations: Japanese-only fine-tune (other Qwen3-ASR languages untested); Mode 1 returns pronunciation kana with no kanji, punctuation or word boundaries; furigana is learned behaviour rather than constrained decoding, so rare formatting slips are possible
- paper: Ruby-ASR: Evidence-Preserving Supervision for Joint Orthographic and Lexical-Reading Recognition

## Comparison

- languages: Japanese
- streaming: ❌
- license: Apache-2.0

## Innovation

The idea is a **target-representation fix, not an architecture change**, and
it is the kind of intervention that usually matters more than either. In
Japanese ASR, supervising on orthography throws away the acoustic evidence
that disambiguates readings — two utterances with identical kanji but
different pronunciations become one target, and no post-hoc text-only G2P can
recover what the label discarded. Ruby-ASR keeps that evidence by making the
target **span-bound**: reading is written *next to* the span that produced it
rather than as a separate parallel sentence, so orthography and reading stay
locally aligned and both views are deterministically recoverable. The
interesting second move is what they do with the **auxiliary CTC branch**: it
hangs off the audio encoder rather than the decoder, and its weights are
shipped in a *separate* `ctc/` subfolder so the main checkpoint stays a
**stock Qwen3-ASR file**. That is a deliberate systems compromise — reading
extraction becomes a fast encoder-side pass with no LLM decoding, while the
primary path remains byte-identical to a checkpoint without the branch and
still runs on **unmodified vLLM**. The joint `0.3·CTC + 0.7·CE` weighting plus
the explicit claim that the seq2seq path never sees the adapter is what makes
that decoupling honest rather than lossy. Benchmark reporting is careful in a
way most releases are not: all three metrics are defined, the two variants are
compared on all three axes (and each wins a different one), and the comparison
set includes both an orthographic ASR baseline and a reading-oriented one
(Kana-Whisper) so the gain cannot be explained by metric choice.
