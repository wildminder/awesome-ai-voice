---
release_date: "January 23, 2026"
model_name: "ACE-Step Transcriber"
category: "audio_transcribers"
summary: "ACE-Step — multilingual audio annotation model used to label ACE-Step v1.5 training data; transcribes speech AND singing voice (lyrics + song structure) in 50+ languages."
slug: "acestep-transcriber"
---

# ACE-Step Transcriber

ACE-Step Transcriber is the **annotation model** that ACE-Step used to label its v1.5 music-generation training data. It is a multilingual audio annotation model built on **Qwen2.5 Omni 7B** that transcribes both **speech** and **singing voice** with high accuracy, then automatically identifies song structural elements (verse, chorus, bridge, intro, outro, pre/post-chorus, instrumental interludes). Output is structured: `# Languages` + `# Lyrics` blocks with `[Section Tag - Optional Instrument]` markers.

Use cases include lyrics extraction from reference tracks, labelled-dataset creation for music AI models, and structured audio-to-text for accessibility.

## Links

- HuggingFace: https://huggingface.co/ACE-Step/acestep-transcriber
- Paper: https://arxiv.org/abs/2602.00744

## Features

- asr: yes
- languages: 50+
- streaming: no
- license: MIT
- architecture: Qwen2.5 Omni 7B base, multi-modal audio-text-to-text
- pipeline_tag: audio-text-to-text
- target_output: structured `# Languages` + `# Lyrics` with `[Section Tag]` markers (verse, chorus, bridge, intro, outro, pre-chorus, post-chorus, intro/outro, guiter interlude, instrumental, spoken)
- training_role: annotation / labeling model for ACE-Step v1.5 music data
- modalities: speech + singing voice + musical structure
- datasets: multilingual (50+), music + speech corpora

## Comparison

- use_case: Music data labeling
- input: Audio
- languages: 50+
- base_model: Qwen2.5 Omni 7B
- license: MIT

## Innovation

A *specialized audio annotator* that bridges speech recognition and music-structure understanding: it labels both what is being said and how the song is organized (verse/chorus/bridge and instrumental boundaries) in one pass — built specifically to label the training corpus of the ACE-Step v1.5 music model, but usable as a stand-alone multilingual lyrics / audio-structure transcriber.
