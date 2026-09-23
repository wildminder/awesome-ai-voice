---
release_date: "August 27, 2026"
model_name: "Coqui TTS Anonymizer"
category: "tts"
summary: "Romolo Muletta, Felix Matthias Saaro, Mark Cieliebak & Jan Deriu — a fork of Coqui TTS that repurposes XTTS v2 as a speaker anonymizer without retraining: resynthesize the target's words in a donor voice, with automatic most-distant donor selection from a voice pool, three quality modes, and WER / BLEU / speaker-similarity scoring."
slug: "coqui-tts"
---

# Coqui TTS Anonymizer (rm00cr/coqui-tts)

**Coqui TTS Anonymizer** is a fork of
[Coqui TTS](https://github.com/coqui-ai/TTS) whose headline capability is a
**speaker-anonymization pipeline**: give it a recording plus a donor voice,
and it returns *the same words spoken in the donor's voice*. The transcript
survives verbatim; the original speaker's vocal identity does not. The paper
behind it (*Your Voice Cloning System is Secretly a Voice Anonymizer*, arXiv
2608.27360) makes the mechanism explicit — **XTTS v2's voice cloning
preserves prosodic structure independently of speaker identity**, so the
cloning path can be repurposed as voice conversion by conditioning on a
pseudo-speaker, with **no retraining**. The fork adds an `anonymizer/`
package (pipeline, config, voice pools, donor selection, scoring, resumable
batch, CLI), anonymization entry points on the `Xtts` class, and a
weight-free unit-test suite. Evaluation covers **seven European languages**
across CommonVoice and Multilingual LibriSpeech, reporting near-optimal
privacy (**EER ≈ 0.49**) with substantially better speech quality than
dedicated anonymization baselines and no language-specific training.

## Links

- GitHub: https://github.com/rm00cr/coqui-tts
- arXiv: https://arxiv.org/abs/2608.27360
- Predecessor: https://github.com/coqui-ai/TTS

## Features

- parameters: XTTS v2 checkpoints (~2 GB, downloaded once); no new weights trained
- voice_cloning: yes (XTTS v2 zero-shot cloning — the same capability repurposed for anonymization)
- asr: no (no native ASR; the anonymization pipeline calls out to Whisper for the transcript)
- languages: 16 (XTTS v2)
- streaming: yes (upstream XTTS streams with <200 ms latency)
- license: MPL-2.0 (upstream Coqui TTS license, kept by the fork)
- base_model: coqui-ai/TTS (XTTS v2)
- pipeline: Whisper transcript → tokenize → XTTS GPT with reference conditioning → HiFi-GAN decode at 24 kHz
- modes: single (one forward pass, seconds) / refine (segment + rescore + regenerate weak segments + crossfade stitch, minutes, GPU) / iterate (N compounding passes, keeps the best-scoring, minutes, GPU)
- donor_selection: explicit file, directory, or comma-separated list; or a voice pool (directory of per-speaker folders, or a CSV manifest) with `most_distant` selection
- selection_metric: ECAPA2 mean cosine similarity; the pool speaker furthest from the target wins, then conditioning on its `select_top_k` least-similar clips (default 10)
- selection_preview: `anonymize select` ranks the pool without loading XTTS
- scoring: WER, BLEU, target_similarity, reference_similarity, overall_quality (weighted 0.05 / 0.05 / 0.30 / 0.60)
- iterate_tradeoff: on the bundled sample, three iterations moved similarity-to-original 0.198 → 0.141 while WER rose 0.00 → 0.07
- cli: `anonymize run` / `anonymize batch` / `anonymize select` / `anonymize config`
- batch: resumable, file-locked checkpoint, `manifest.csv` recording the chosen donor per file, per-file failure isolation
- config_precedence: CLI flag > `--config` file > environment variable > built-in default
- env_vars: `XTTS_MODEL_DIR`, `ANONYMIZER_DEVICE`, `ANONYMIZER_MODE`, `ANONYMIZER_WHISPER_MODEL`, `ANONYMIZER_VOICE_POOL`
- install: `uv sync` then `uv run anonymize download-model`
- api: `from anonymizer import Anonymizer` then `anon.anonymize("interview.wav", reference="donor.wav")`
- hardware: CUDA GPU strongly recommended; CPU is workable for `single` only
- limitations: transcript content is not redacted; language must be set explicitly; quality depends on the donor; Whisper errors propagate; prosody and timing shift; not a formal privacy guarantee
- upstream_models: ⓍTTS v2, VITS, YourTTS, Tortoise, Bark, ~1100 Fairseq models, plus the MelGAN / HiFi-GAN / UnivNet vocoder family

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 16
- streaming: ✅
- license: MPL-2.0

## Innovation

The paper's insight is a **capability inversion**: a voice *cloning* model is
a voice *anonymizer* in disguise. XTTS v2 was trained on 27k hours to keep
prosody and linguistic content while swapping speaker identity on demand —
which is precisely the operation anonymization needs, only with the
"speaker" axis pointed at a *pseudo*-speaker rather than a target identity.
Reframing it that way means **zero retraining and zero language-specific
data**, and it is why the released system is a ~300-line façade over an
existing checkpoint rather than a new model. Two engineering decisions make
it usable rather than merely clever. First, **donor choice is automated and
per-utterance**: a fixed donor is a weak default (if the donor resembles the
speaker being anonymized, almost no identity is removed), so the pool mode
embeds the target and every candidate with ECAPA2 and picks the speaker
furthest away, recording the choice in the batch manifest so a run stays
auditable. Second, **quality is a knob with a measured cost**: `refine`
resynthesizes only weak segments, while `iterate` compounds conversion — the
repo publishes the resulting similarity/WER trade-off rather than claiming a
free lunch. The honest framing of the limitation matters too: this hides
*who* is speaking, not *what* was said, and the authors are explicit that
empirical ECAPA2 similarity is not a formal privacy guarantee.
