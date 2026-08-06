---
release_date: "July 21, 2026"
model_name: "DSA-Tokenizer"
category: "audio_codecs"
summary: "DiscreteSpeech / Anonymous-4open-science — DSA-Tokenizer: a disentangled semantic-acoustic speech tokenizer for fully-discrete Speech LLMs; semantic tokens supervised by ASR capture linguistic content while acoustic tokens supervised by mel-spectrogram restoration encode speaker/style; hierarchical Flow Matching DiT decoder distilled to 4-step inference with GAN fine-tuning."
slug: "dsa-tokenizer"
---

# DSA-Tokenizer

**DSA-Tokenizer** is a speech tokenizer that **explicitly
disentangles semantic and acoustic speech information into
independent discrete token streams**, designed as a building block
for fully discrete Speech LLMs. The two token kinds are supervised
with **distinct optimization constraints**: **semantic tokens** are
trained to low WER/CER under ASR supervision (capturing linguistic
content only), while **acoustic tokens** are trained to reconstruct
mel-spectrograms (capturing speaker style / prosody / acoustic
texture). The decoder is a **hierarchical Flow Matching** DiT
trained with two strategies — **self-reconstruction** (predict the
velocity field of the full mel-spectrogram from complete
acoustic + semantic tokens) and **recombination / contextual
inpainting** (predict the masked mel-spectrogram region given the
unmasked acoustic context + the full semantic tokens). The DiT is
**distilled to 4-step inference** and **fine-tuned with GAN** for
synthesis quality, while supporting **cross-utterance voice clone**
through the disentangled token streams.

The architecture is built to be a drop-in tokenizer for LLM-based
speech generation pipelines (LLM-TTS / LLM-VC); the demo page on
anonymous.4open.science shows Llasa-1B / 3B / 8B and Spark-TTS
paired with DSA for LLM-TTS, plus voice-conversion and
reconstruction comparisons against WavTokenizer / Mimi /
Encodec / SpeechTokenizer / DualCodec / SAC. Pretrained model
weights (decoder + flow2gan_mel_24k_base_50Hz vocoder + vocab) ship
on HF at `DiscreteSpeech/dsa-tokenizer`; the runnable code lives at
the Anonymous-4open-science demo (per the HF card: *"The code and
runnable examples live in the GitHub repository"*).

## Links

- HuggingFace: https://huggingface.co/DiscreteSpeech/dsa-tokenizer
- Paper: https://arxiv.org/abs/2601.09239
- Demo: https://anonymous.4open.science/w/DSA_Tokenizer_demo/

## Features

- parameters: not stated (hierarchy of encoders + DiT decoder + vocoder)
- type: Disentangled Semantic-Acoustic Speech Tokenizer (dual-stream codec)
- sample_rate: 24,000 Hz (vocoder: flow2gan_mel_24k_base_50Hz)
- latent_dim: discrete semantic tokens + discrete acoustic tokens (separate codebooks; vocab.txt ships)
- token_rate: 50 Hz (mel2gan vocoder)
- modalities: Audio
- license: MIT
- architecture: Two-stream encoder (semantic + acoustic branches) → hierarchical Flow Matching DiT decoder → GAN-fine-tuned vocoder (flow2gan_mel_24k_base_50Hz)
- semantic_supervision: ASR loss (low WER/CER)
- acoustic_supervision: mel-spectrogram reconstruction loss
- decoder_optimisation: Flow Matching + 4-step distillation + GAN fine-tuning
- training_strategies: self-reconstruction + recombination / contextual inpainting (joint)
- inference_steps: 4 (distilled)
- inference_pattern: `from f5_tts.dsa_api import DSATokenizer; DSATokenizer.from_pretrained('DiscreteSpeech/dsa-tokenizer', device='cuda:0')`
- downstream_tasks_supported: SpeechLLM-TTS (e.g. Llasa 1B/3B/8B, Spark-TTS), SpeechLLM-VC, speech reconstruction, voice clone across utterances
- disentanglement_quality: outperforms WavTokenizer/Mimi/Encodec/SpeechTokenizer/DualCodec/SAC on disentanglement probing (low WER + low speaker similarity on semantic; high WER + high speaker similarity on acoustic)
- bundle_files: `dsa_tokenizer/model_10000.pt`, `dsa_tokenizer/vocab.txt`, `dsa_tokenizer/config.yaml`; vocoder `flow2gan_mel_24k_base_50hz/epoch-20.pt`
- pipeline_tag: text-to-speech (the canonical use is LLM-TTS); tags include voice-cloning, tokenizer, speech
- library: zips under `f5_tts.dsa_api` integration
- demo_url_format: anonymous.4open.science uses `/w/.../index.html` (root URL returns 400 folder_not_supported; index.html works)
- downloads: 0 (released July 21 2026)

## Comparison

- type: Disentangled Semantic-Acoustic Speech Tokenizer
- sample_rate: 24 kHz
- latent_dim: —
- modalities: Audio
- license: MIT

## Innovation

Two bets together are the technical center of DSA-Tokenizer. The
first is **explicit semantic-acoustic disentanglement via distinct
optimization constraints**: rather than training a single
representational bottleneck and hoping semantic and acoustic
content separate (as prior fusing tokenizers do), DSA trains
semantic tokens against ASR supervision and acoustic tokens against
mel reconstruction as separate streams — so the disentanglement is
*engineered into the loss surface*, not extracted post-hoc. The
second is a **hierarchical Flow Matching decoder with joint
self-reconstruction + contextual-inpainting training**, which lets
the same decoder both reconstruct complete utterances and **inpaint
missing regions using surrounding acoustic context** (the
characteristic operation needed for voice conversion / segment
editing). Coupled with **4-step distillation** and **GAN
fine-tuning** for inference speed and audio quality, the result is
a single tokenizer that supports high-fidelity speech reconstruction
*and* cross-utterance voice clone *and* LLM-TTS (paired with Llasa
8B, Spark-TTS, etc.) — and on the project's disentanglement
probing beats WavTokenizer / Mimi / Encodec / SpeechTokenizer /
DualCodec / SAC at producing a *truly* separable semantic /
acoustic representation.
