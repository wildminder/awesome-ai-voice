---
release_date: "July 8, 2026"
model_name: "WordVoice-base-0.5B"
category: "tts"
summary: "Sihang Nie et al. — a CosyVoice3-0.5B fine-tune that turns implicit end-to-end TTS into explicit, decoupled word-level control over five acoustic dimensions (duration, boundary, energy, pitch, tone), using a 'bound token' that makes the AR LLM plan each word's prosody before emitting its speech tokens."
slug: "wordvoice-base-0-5b"
---

# WordVoice-base-0.5B

**WordVoice** reframes LLM-based TTS from *implicit* to *explicit* control:
instead of asking the model to "just sound right", the user states **what
should happen acoustically, word by word**. Built on the
[CosyVoice3](https://github.com/FunAudioLLM/CosyVoice) framework, it supports
independent, **decoupled control of five acoustic dimensions per input word**:
⏱️ **duration** (per-word pronunciation length), ⏸️ **boundary** (a 5-level pause
class `b0`–`b4`), 🔊 **energy** (loudness, 0–1), 🎵 **pitch** (core f0,
−1–1) and 📈 **tone** (7 prosodic morphologies — flat, rise, strong rise,
fall, strong fall, peak, valley). The mechanism is an **"acoustic thinking"
bound token** (`<b>`): before the autoregressive model emits the speech tokens
for a given word, it first *predicts that word's acoustic attributes* — plan
the prosody, then generate the sound. Two inference modes are shipped:
**Free Mode**, where the LLM performs the prosodic planning itself for
reference-conditioned zero-shot speech, and **Control Mode**, where the caller
supplies the attributes. Weights are released per language —
`wordvoice_llm_en.pt` and `wordvoice_llm_zh.pt` alongside a shared
flow-matching module — trained on the **WordVoice-5A** dataset, whose five
"dimensions" are the five controllable attributes.

## Links

- HuggingFace: https://huggingface.co/XXH333/WordVoice-base-0.5B
- arXiv: https://arxiv.org/abs/2607.06461
- GitHub: https://github.com/XXH333/WordVoice-main
- Demo: https://huggingface.co/spaces/XXH333/wordvoice-tts
- Website: https://xxh333.github.io/wordvoice-demo/

## Features

- parameters: 0.5B (base and name); shipped as three checkpoints — flow matching 1.33 GB plus separate EN and ZH LLM weights at 2.03 GB each
- voice_cloning: yes (zero-shot, reference-audio conditioned — inherited from the CosyVoice3 base; no reference length or speaker-similarity result is stated)
- asr: no
- languages: 2 (Chinese and English, with separate per-language LLM checkpoints)
- license: Apache-2.0
- base_model: FunAudioLLM/Fun-CosyVoice3-0.5B-2512 (Qwen2.5-family LLM backbone per the project README)
- control_dimensions: duration, boundary (b0–b4), energy (0–1), pitch (−1 to 1), tone (7 categories)
- tone_categories: flat, rise, strong rise, fall, strong fall, peak, valley
- mechanism: bound token (`<b>`) — the AR LLM predicts a word's acoustic attributes before generating its speech tokens
- modes: Free Mode (model plans prosody for zero-shot speech) and Control Mode (caller supplies per-word attributes)
- training_data: WordVoice-5A (released alongside the model, with a separate preprocessing pipeline at XXH333/WordVoice-5A-Pipeline)
- datasets_note: speaker count, hours and utterance counts are not stated in the released documentation
- benchmarks: none — no WER, MOS, speaker-similarity or control-accuracy numbers are published; quality claims are qualitative
- sample_rate: not stated in the released documentation
- install: conda environment, `pip install -e .`, then `bash download_models.sh` (pulls CosyVoice3 and MMS-FA dependencies)
- inference: `python wordvoice_infer.py` for the out-of-the-box Free Mode / Control Mode demo
- release_notes: open-sourced with paper, model, dataset and pipeline on 2026/07/08; interactive Hugging Face Space demo added 2026/07/29

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 2
- license: Apache-2.0

## Innovation

Nearly every LLM-TTS system makes prosody a **latent**: the language model is
asked to produce fluent speech and the timing, pauses, energy and intonation
emerge as a side effect, so the user can influence them only through prompt
text — and cannot ask for "a long pause after this word" or "flat and quiet
here" in any reproducible way. WordVoice's move is to make those attributes
**first-class, discrete, per-word outputs** that the user writes down. The
subtle part is *where* the control lives: the **bound token** means the
attributes are predicted by the autoregressive LLM itself, autoregressively,
*before* the corresponding speech tokens are generated — "acoustic thinking".
That ordering is what makes the control compositional rather than a separate
classifier bolted on afterward; the model reasons about the prosodic shape of
the word it is about to say, in context with the words around it. The
five-dimension decomposition (duration / boundary / energy / pitch / tone) is
also a deliberate interface choice — boundary is a *category* while energy and
pitch are *scalars*, which is not how a generic "emotion" tag behaves, and is
far more useful for subtitle and dubbing work. Worth weighing alongside the
controls is what the release does **not** include: no objective results, no
MOS, no speaker-similarity figure, no stated reference-audio protocol, and no
sample rate. The controls are clearly specified and the code is open; the
accuracy of the control and the fidelity of the zero-shot cloning are
unmeasured in the published artifacts.
