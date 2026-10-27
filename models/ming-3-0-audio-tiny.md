---
release_date: "October 19, 2026"
model_name: "Ming-3.0-audio-tiny"
category: "a2a"
summary: "inclusionAI — compact 9.3B MoE native audio-language model (2.7B active) for speech recognition, audio understanding and spoken answers, runnable on a single GPU."
slug: "ming-3-0-audio-tiny"
---

# Ming-3.0-audio-tiny

Ming-3.0-audio-tiny is the compact member of inclusionAI's Ming-3.0 audio family: a **9.3B-parameter Mixture-of-Experts model with 2.7B activated per inference step** (8,871,306,016 measured across 2 BF16 shards), roughly a fourteenth of Flash's footprint. It keeps the same architecture and the same task surface — audio plus a text instruction in, text or text-plus-speech out through an optional Talker — but the whole checkpoint fits on a single GPU, which is the whole point: the SGLang-Omni profile colocates the thinker, the audio encoder and speech synthesis on one device (`--talker.gpu 0`), and the validated SGLang text profile uses one GPU. Recognition quality tracks Flash closely but sits below it: Chinese CER **3.79%** averaged over AISHELL-1/2, Common Voice 15zh, FLEURS and WenetSpeech, English WER **4.36%** over LibriSpeech, Common Voice 15 en, FLEURS and VoxPopuli, and **10.29%** CER across fifteen Mandarin dialects. On audio understanding it trails Flash across the board but stays usable — BigBenchAudio 99.20, MMAU 75.90, MMSU 73.06, MMAR 67.70, MMAU-Pro 56.42, VoiceBench 74.29, URO-Bench-Pro 54.15, BFCL-V3 Audio 79.80. It is released under MIT and shares the flash repository, benchmark tables and serving scripts.

## Links

- HuggingFace: https://huggingface.co/inclusionAI/Ming-3.0-audio-tiny
- GitHub: https://github.com/inclusionAI/Ming-3.0-audio-flash
- ModelScope: https://modelscope.cn/models/inclusionAI/Ming-3.0-audio-tiny
- Website: https://sgl-project.github.io/sglang-omni/cookbook/ming3_audio.html

## Features

- parameters: 9.3B total / 2.7B active per step (8,871,306,016 safetensors-measured, 2 BF16 shards)
- license: MIT
- text: yes (text instruction in; text or text-plus-speech out)
- video: no
- audio: yes (audio in, optional synthesized speech out via the Talker)
- voice_cloning: yes (reference-audio prompting with `ref_audio` + `prompt_text`)
- asr: yes (same model transcribes; validated prompt returns a language label + tab + text)
- languages: Chinese and English (varied accents, dialects, noisy and multi-speaker conditions)
- streaming: yes (vLLM-Omni streaming client, raw PCM audio output)
- architecture: audio encoder (32 layers, hidden 1280, 20 heads, 128 mel bins, 3000 audio-context tokens) + projector + BailingMoeV3Audio MoE text backbone + optional Talker for speech output
- chinese_asr_avg: CER 3.79 (AISHELL-1 1.47, AISHELL-2 Android 2.68 / iOS 2.60, Common Voice 15zh 5.64, FLEURS zh 2.99, WenetSpeech meeting 6.04 / net 5.14)
- english_asr_avg: WER 4.36 (LibriSpeech clean 1.42 / other 3.06, Multilingual LibriSpeech 4.78, Common Voice 15 en 7.89, FLEURS en 3.30, VoxPopuli 5.68)
- dialect_asr_avg: CER 10.29 across 15 Mandarin dialects (incl. Cantonese 4.49, Sichuanese/Chongqing 4.46, Anhui 5.42)
- long_form_asr: AA-Earnings22-clean WER 6.30, Earnings22 WER 18.29, AISHELL-4 CER 21.94, AMI WER 24.77
- context_asr: ContextLASR WER 2.12 / NE-WER 6.27 / NE-FNR 2.02
- audio_intelligence: BigBenchAudio 99.20, MMAU 75.90, MMAR 67.70, MMSU 73.06, MMAU-Pro 56.42, AudioMarathon 64.54, LongAudioSpan rubric 35.45, MuchoMusic 58.07
- spoken_interaction: URO-Bench-Pro 54.15, VoiceBench 74.29
- tool_calling: BFCL-V3 Audio 79.80, SpeechTCEval 69.80
- voices: built-in IP voices 灵小柔 (default), 灵楷, US_James, US_Stella; reference-audio cloning with prompt text
- serving: SGLang-Omni (single GPU, `--talker.gpu 0` colocates speech synthesis), SGLang (text output, 1 GPU), vLLM-Omni (MING_MODEL_VARIANT=tiny), Transformers with custom code (trust_remote_code)
- sibling_model: Ming-3.0-audio-flash (126B total / 6.5B active) — same architecture, larger, stronger

## Comparison

- text: ✅
- video: ❌
- audio: ✅
- max_duration: —
- sample_rate: —
- license: MIT

## Innovation

Ming-3.0-audio-tiny is what makes the Ming-3.0 audio line *deployable* rather than merely capable: the same `BailingMoeV3Audio` MoE thinker, the same 32-layer audio encoder and the same optional Talker as the 126B Flash checkpoint, distilled down to 9.3B total and 2.7B active, and small enough that the entire pipeline — audio encoder, thinker and speech synthesis — runs on one GPU behind an OpenAI-compatible server offering `/v1/audio/transcriptions`, `/v1/audio/speech` and `/v1/chat/completions` side by side. The quality gap to Flash is real but modest where it matters most: Chinese CER 3.79% vs 3.45%, English WER 4.36% vs 3.69%, dialect CER 10.29% vs 9.40%, while BigBenchAudio is essentially tied (99.20 vs 99.40). The gap widens on the harder audio-reasoning and spoken-interaction axes (MMAU-Pro 56.42 vs 66.41, VoiceBench 74.29 vs 86.74), which is the honest dividing line between the two tiers: Tiny for on-prem transcription and spoken chat, Flash when the audio reasoning has to be right.
