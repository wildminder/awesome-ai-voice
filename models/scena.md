---
release_date: "July 7, 2026"
model_name: "ScenA"
category: "a2a"
summary: "Lightricks / Tel Aviv University — reference-driven multi-speaker audio *scene* generation (dialogue + ambient + SFX) from a free-form natural-language prompt conditioned on one or more reference voice clips; an audio-only flow-matching DiT built on the LTX-2 architecture (~4B params, 48 layers)."
slug: "scena"
---

# ScenA

**ScenA** generates multi-speaker audio *scenes* — dialogue and
conversation with sound effects and ambience — from a text prompt,
conditioned on one or more **reference-audio** clips that set the
speakers' voices. Unlike prior multi-speaker dialogue systems it
uses **no** per-turn tags, multi-stream transcripts, or speaker
embeddings: a free-form natural-language prompt alone describes the
scene. The text prompt determines which reference voice speaks where,
allowing overlapping speech, spontaneous paralinguistic events,
and scene-level ambient sound — all inherited from the in-the-wild
text-to-audio pretraining distribution. The architecture is an
audio-only, reference-conditioned flow-matching DiT built on the
LTX-2 backbone (~4B parameters, 48 layers). Reference latents are
concatenated into the token sequence and distinguished by lightweight
identity-aware positional encodings. The training tackles a
specifically identified "Reference Shortcut" failure mode — under
standard noise schedules the model can identify the matching
reference by noisy-target acoustic similarity, bypassing the text
prompt — by using a high-noise-biased timestep distribution that
forces reliance on the prompt for speaker assignment. Evaluator:
CoVoMix2-Dialogue benchmark. Project page, code, paper, and HuggingFace
checkpoint are linked below.

## Links

- HuggingFace: https://huggingface.co/mifinkelson/scena
- GitHub: https://github.com/finmickey/scena
- Website: https://finmickey.github.io/scena/
- Paper: https://arxiv.org/abs/2606.19325

## Features

- parameters: ~4B (DiT, 48 layers; built on LTX-2 architecture)
- text: yes (free-form natural-language scene description)
- video: no
- audio: yes (one or more reference-audio clips for speaker voices)
- max_duration: not stated (scene-level generation)
- sample_rate: (not stated; inherits LTX-2 audio VAE)
- voice_cloning: yes (reference-conditioned prompt-driven speaker voice assignment)
- multi_speaker: yes
- ambient_sound: yes (SFX, room acoustics, overlapping speech)
- architecture: flow-matching DiT (LTX-2 backbone, audio-only)
- speaker_assignment: natural language (no per-turn tags / identity encoders)
- training_fix: high-noise-biased timestep distribution (defeats Reference Shortcut)
- text_encoder: google/gemma-3-12b-it
- audio_vae: bundled (~365 MB; encodes+decodes so full LTX-2 not needed)
- checkpoint_size: ~8.2 GB (scena.safetensors) + ~365 MB (audio_vae.safetensors)
- license: LTX-2 Community License (other)
- training_data: in-the-wild text-to-audio pretrained, then reference-conditioned fine-tune
- evaluation: CoVoMix2-Dialogue (speaker-binding metrics)

## Comparison

- text: ✅
- video: ❌
- audio: ✅
- max_duration: —
- sample_rate: —
- license: Other

## Innovation

The "Reference Shortcut" failure-mode identification is the
technical center of the work: under standard diffusion noise
schedules, a multi-speaker reference-conditioned model can match
each reference to the noisy-target segment by acoustic similarity
alone, bypassing the text prompt entirely. ScenA's high-noise-biased
timestep distribution forces the model to rely on the prompt for
speaker assignment at training time. Combined with the absence of
any per-turn speaker structure (tags / transcripts / identity
encoders) and the prompt's role as the *only* speaker-routing
signal, this yields multi-speaker conversational scenes with
overlapping speech, paralinguistic events, and ambient texture
that previous structured-supervision multi-speaker systems filter
out by design.
