---
release_date: "October 31, 2026"
model_name: "Iroha-TTS-V1"
category: "tts"
summary: "Iroha Studios — a Japanese emotional speech model adapted from Fish Audio S2-Pro with seven controls on one set of weights: whole-line emotion and intensity, mid-line emotion changes, voice cloning, laughter/sighs/crying, whispering and kana pronunciation."
slug: "iroha-tts-v1"
---

# Iroha-TTS-V1

**Iroha-TTS-V1** is an expressive Japanese text-to-speech model for character dialogue from Iroha Studios, adapted from Fish Audio S2-Pro by supervised fine-tuning and policy optimisation. A single set of weights exposes seven controls: whole-line emotion (joy, anger, sadness, surprise), experimental emotion intensity via activation steering, mid-line emotion changes with inline tags, zero-shot voice cloning from a short reference recording and its transcript, placed vocal events ([laugh], [sigh], [cry]), whispering, and explicit kana readings for names and heteronyms. The slow and fast S2-Pro transformers predict discrete audio codes decoded to 44.1 kHz WAV; adaptation uses LoRA on both transformers followed by policy optimisation on the slow model's MLP only. Released as model weights plus runnable inference code — no training data or training pipeline — it targets character dialogue, audio drama and voice agents, and is benchmarked specifically on Japanese emotion control rather than general TTS quality.

## Links

- HuggingFace: https://huggingface.co/IrohaStudio/Iroha-TTS
- Demo: https://huggingface.co/spaces/cyacya8023/Iroha-TTS
- Blog: https://irohastudios.github.io/blog/irohattsv1/en/
- Paper: https://irohastudios.github.io/blog/research/en/
- Predecessor: https://huggingface.co/fishaudio/s2-pro

## Features

- parameters: not stated; shipped as LoRA, adapter and intensity safetensors on top of Fish Audio S2-Pro, whose base weights are about 10 GB in BF16 and about 11 GB are downloaded on first run
- voice_cloning: yes
- asr: no
- emotion_control: yes
- pronunciation: yes
- languages: Japanese
- streaming: no
- license: Fish Audio Research License
- base_model: fishaudio/s2-pro (revision 1de9996b6be38b745688de084d87a5633f714e4e)
- architecture: Fish S2-Pro slow and fast transformers over discrete audio codes, 9 residual codebooks of 1024, model context 4096, max 400 frames, 44.1 kHz output
- adaptation: SFT with LoRA rank 32 alpha 16 on attention and MLP in both transformers (2,700 plus 1,600 steps), then policy optimisation with rsLoRA rank 16 alpha 64 on the slow MLP only, 8 candidates per request, KL weight 0.02
- output: single-pass full-utterance WAV capped at 400 frames or about 18.6 s, with no automatic sentence splitting
- voice_cloning_detail: a short reference recording plus its exact transcript; speaker similarity 0.694 without emotion and 0.636 with emotion
- emotion_tags: whole-line joy, anger, sadness and surprise, plus inline [happy] [angry] [sad] [surprised] tags for mid-line transitions
- intensity: activation steering at layers 20 and 22 with coefficients -0.06, -0.03, 0 and 0.045; experimental, only 70.83% of 72 contexts followed the full four-level ordering
- vocal_events: [laugh], [sigh] and [cry] placed inline; sighs detected in 56 of 60 requests (93.3%) and laughter in 44 of 59 evaluable clips (74.6%)
- whisper: [whisper] tag or a whispered reference; inference guidance 1.5 raised detections from 4 to 32 of 60 while lowering speaker similarity and UTMOS
- pronunciation_detail: explicit kana in brackets such as 水神[みずかみ] rewrites the input text before generation; 94.7% of 264 outputs correct versus 39.4% without, though the base model with the same frontend reached 93.9%
- emotion_accuracy: 85.6% on emo2vec large and 93.3% on EmoRuler, versus 17.9% and 6.0% for the original Fish S2-Pro
- paired_comparison: with engine, inputs, reference encodings and seeds fixed and only the weights changed, EmoRuler accuracy rises from 6.04% to 89.17% and emotion2vec+ from 17.92% to 83.54%, with CER essentially unchanged
- mos: Japanese listening test overall 3.85 and 31.7% win share, ahead of Fish Audio Drama 3 at 3.69 and 23.2%; pairwise win rates 69.3% vs S2-Pro, 58.0% vs Drama 3, 58.7% vs Irodori-TTS v4-Large and 82.7% vs IndexTTS-2.5
- japanese_benchmarks: 4.80% CER on CV3-Eval versus 5.30% for the original model rerun in the same environment; 3.33% CER and 0.745 speaker similarity on the MiniMax Japanese set
- binaural: optional spatial post-processing via spatial/binaural.py with TH Köln HRIRs; a separate CPU step, not a model feature
- vram: NVIDIA GPU with at least 28 GB free VRAM, Linux and Python 3.12
- release: launch post published October 31, 2026; technical notes dated October 29, 2026 with an October 30 listening-study snapshot; HF repository created October 20, 2026
- access: as of launch, anonymous access to the model repository and online Space is restricted and downloads require a Hugging Face account with access
- license_terms: Fish Audio Research License, Copyright 39 AI, INC.; research and non-commercial use is free but commercial use requires a separate license from Fish Audio; new inference code in emotts/ and infer.py is MIT; S2-Pro base weights are downloaded separately under the same research license
- limitations: Japanese only; intensity control is experimental and cannot combine with inline tags; no segment-level evaluation of mid-line transitions; training data and pipeline are not released; the development panel was reused for model selection and four of its six voices appeared in EmoRuler training

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: Japanese
- streaming: ❌
- license: Fish Audio Research License

## Innovation

Iroha-TTS-V1 treats expression as a set of **explicit, composable inputs over one shared set of weights** rather than a collection of separate specialist models. Seven controls ride on the same S2-Pro adaptation: whole-line emotion, an experimental intensity dial, mid-line tag transitions, reference-based voice cloning, placed vocal events, whispering and kana readings. The training is deliberately paired — a teacher model generates happy, angry, sad and surprised versions of the same line with the same reference audio, candidates are filtered for emotion, wording, voice and quality, and LoRA plus policy optimisation then learns the tag's acoustic effect instead of guessing emotion from word choice. The most interesting result is the strictly paired comparison: with the inference engine, inputs, reference encodings and random seeds held fixed and only the weights changed, emotion accuracy rises from 6.04% to 89.17% on EmoRuler while character error rate stays essentially unchanged, which isolates the adaptation from the surrounding pipeline. The release is also candid about what did not work — more unpaired data gave limited gains, intensity labels without acoustic differences taught nothing, emotion rewards induced unrequested laughter in 11.7% of happy samples, and explicit kana rewriting rather than a learned reading tag produced most of the pronunciation gain. That honesty matters because the headline numbers come from a development panel reused for model selection, with four of six voices present in the classifier's training data: this is strong evidence for controllable Japanese character dialogue, not a claim of general TTS superiority.
