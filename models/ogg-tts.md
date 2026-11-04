---
release_date: "October 30, 2026"
model_name: "OGG TTS"
category: "tts"
summary: "FashionFlora — an expressive 0.8B multilingual TTS that generates Fish Audio codec tokens with block diffusion: 0.74 s blocks decoded in parallel and streamed left to right, 8 languages, 24 inline emotion and vocal-event tags, and zero-shot voice cloning."
slug: "ogg-tts"
---

# OGG TTS

**OGG TTS** is a 0.8B-parameter zero-shot text-to-speech model from FashionFlora, trained on about 8,200 hours of professionally acted speech in English, Polish, Spanish, German, Russian, French, Portuguese and Italian. It generates discrete tokens of the Fish Audio 44.1 kHz codec with **block diffusion**: each 16-frame (0.74 s) block is produced in parallel by iterative confidence-ordered unmasking, while blocks follow one another left to right, so finished blocks never change and can be played immediately. The backbone is initialised from OmniVoice (Qwen3-0.6B, masked discrete diffusion) and a 164M-parameter chained multi-token-prediction decoder fills in the nine residual codebooks of each block. Expression is controlled with 24 optional inline tags covering emotion, delivery and vocal events, and multi-speaker dialogue is generated in a single pass. This is a preview release — the published checkpoint is an intermediate step of a 400k-step pre-training run that is still in progress, and formal evaluation is withheld for the final checkpoint.

## Links

- HuggingFace: https://huggingface.co/FashionFlora/ogg-tts
- GitHub: https://github.com/FashionFlora/ogg-tts
- Demo: https://huggingface.co/spaces/FashionFlora/ogg-tts
- Predecessor: https://huggingface.co/k2-fsa/OmniVoice

## Features

- parameters: 0.81B (815,092,736 F32, safetensors-measured; codec excluded)
- voice_cloning: yes
- asr: no
- emotion_control: yes
- languages: 8 (English, Polish, Spanish, German, Russian, French, Portuguese, Italian)
- streaming: yes
- license: Fish Audio Community License
- architecture: OmniVoice / Qwen3-0.6B backbone, 28 layers, hidden 1024, bidirectional attention within a block and block-causal across blocks, plus a 9-layer chained MTP acoustic decoder of 164M parameters
- base_model: k2-fsa/OmniVoice (Qwen3-0.6B masked discrete diffusion)
- codec: Fish Audio Drama 3 / S2 codec, 44.1 kHz, 21.53 frames per second, 1 semantic codebook of 4096 plus 9 residual codebooks of 1024
- decoding: 6 or 8 confidence-ordered unmasking iterations per block with classifier-free guidance, then 4 MTP rounds per residual codebook; KV cache; length decided by an end-of-speech token
- block_size: 16 frames or 0.74 s; roughly 0.17 real-time factor on one GPU
- voice_cloning_detail: zero-shot from a few seconds of reference audio plus its transcript, or built-in speaker identities with no audio prompt
- control_tags: 24 optional inline tags in three groups — emotion [angry] [frustrated] [excited] [tired] [playful] [sad] [scared] [shouting]; delivery [whispering] [softly] [voice breaking] [singing] [pause] [slowly]; vocal events [laughing] [sighing] [gasping] [panting] [coughing] [clears throat] [sniffling] [scoffing] [yawning] [humming]
- multi_speaker: whole dialogue generated in one pass with per-voice prompts and turn markers such as S1 and S2
- tag_annotation: audio-language-model pass over 502,668 sentences under a closed 24-tag list, tagging only what is audible; 57,016 sentences or 11% received at least one tag; tags are dropped from part of training to keep them optional
- training_data: about 8.2k hours from 584 audiobooks and games, 16,628 speakers, 6.1M sentences, 559M codec frames, 5.6B codec tokens, about 112M text tokens
- language_hours: English ~2,610 h, Polish ~1,300 h, Spanish ~820 h, German ~750 h, Russian ~645 h, French ~500 h, Portuguese ~300 h, Italian ~290 h
- training: 400k steps planned at 16k tokens per step, AdamW with cosine decay in bf16 on one NVIDIA RTX PRO 6000 Blackwell 96 GB; roughly 190 hours of audio per training hour
- compute_cost: about 173 GPU hours and USD 1,040 projected total including about USD 455 of annotation; five discarded pilot runs consumed about 20 GPU hours
- evaluation: in progress — Seed-TTS (EN) and CV3 (PL, DE, FR, ES, IT, RU, PT) for WER/CER, speaker similarity, UTMOS, tag compliance and real-time factor
- release: GitHub repository and model card first published October 30, 2026 at the 20k checkpoint; the 40k checkpoint revision followed October 31, 2026
- license_terms: Apache-2.0 for the code, Fish Audio Community License Agreement v1.0 for the Fish Audio codec and software; research and non-commercial use is free and limited commercial use is permitted while annual revenue is below USD 500,000; hosted services need a separate written license
- license_note: the authors state that because the training data contains copyrighted recordings, the released weights are intended for research
- limitations: preview checkpoint with weak tag control and unfinished speaker similarity; Italian and Portuguese have the least data; rare tags such as [singing] are unreliable; very short multi-speaker turns can be dropped

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 8
- streaming: ✅
- license: Fish Audio Community License

## Innovation

OGG TTS swaps the usual autoregressive token-by-token speech decoder for **block diffusion** over Fish Audio codec tokens: a Qwen3-0.6B masked-diffusion backbone unmasks the semantic codes of a 0.74 s block in a handful of confidence-ordered, classifier-free-guided iterations, then a chained multi-token-prediction transformer fills all nine residual codebooks of that block in parallel. Blocks are generated left to right and once complete are immutable, which makes low-latency streaming a structural property rather than a chunking hack — roughly 0.17 real-time factor on one GPU while producing 44.1 kHz audio. The second bet is on data: 8.2k hours of professionally acted, multi-cast audiobook and AAA-game dialogue, with 24 emotion, delivery and vocal-event tags produced by an audio-language model instructed to label only what is audible, and tags deliberately dropped from part of the training set so control stays optional at inference. The release is unusually transparent about cost and status — a single RTX PRO 6000, about USD 1,040 of projected compute and annotation, five discarded pilot runs, and an explicit statement that this is an intermediate checkpoint of a run still in progress. That honesty cuts both ways: the architecture and recipe are fully documented, but there are no published WER, speaker-similarity or UTMOS numbers yet, so the quality claims remain unverified.
