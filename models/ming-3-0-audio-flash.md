---
release_date: "October 19, 2026"
model_name: "Ming-3.0-audio-flash"
category: "a2a"
summary: "inclusionAI — 126B MoE native audio-language model (6.5B active) that hears, reasons about and speaks: speech recognition, audio understanding and spoken answers through an optional Talker."
slug: "ming-3-0-audio-flash"
---

# Ming-3.0-audio-flash

Ming-3.0-audio-flash is inclusionAI's native audio-language Mixture-of-Experts model: **126B total parameters with 6.5B activated per inference step** (128,181,010,400 measured across 25 BF16 shards). It accepts audio together with a text instruction and returns text, optionally with synthesized speech from a separate Talker, so a single model covers the whole loop from hearing to understanding to answering out loud. The backbone is a `BailingMoeV3Audio` MoE paired with a 32-layer, 1280-wide audio encoder over 128 mel bins with a 3000-token audio context; the Talker speaks with built-in IP voices (灵小柔, 灵楷, US_James, US_Stella) or clones a voice from a reference clip plus its transcript. Recognition is the headline: Chinese CER **3.45%** averaged over AISHELL-1/2, Common Voice 15zh, FLEURS and WenetSpeech, English WER **3.69%** averaged over LibriSpeech, Common Voice 15 en, FLEURS and VoxPopuli, and **9.40%** CER across fifteen Mandarin dialects — with long-form meeting transcription (AA-Earnings22, AISHELL-4, AliMeeting, AMI) handled by the same model. On audio understanding it leads the compared open models on BigBenchAudio (99.40), MMAU (82.00), MMSU (78.82) and MMAU-Pro (66.41). It is served through vLLM-Omni, SGLang and SGLang-Omni — the last exposing OpenAI-compatible transcription, speech and chat endpoints from one server — and is released under MIT.

## Links

- HuggingFace: https://huggingface.co/inclusionAI/Ming-3.0-audio-flash
- GitHub: https://github.com/inclusionAI/Ming-3.0-audio-flash
- ModelScope: https://modelscope.cn/models/inclusionAI/Ming-3.0-audio-flash
- Website: https://sgl-project.github.io/sglang-omni/cookbook/ming3_audio.html

## Features

- parameters: 126B total / 6.5B active per step (128,181,010,400 safetensors-measured, 25 BF16 shards)
- license: MIT
- text: yes (text instruction in; text or text-plus-speech out)
- video: no
- audio: yes (audio in, optional synthesized speech out via the Talker)
- voice_cloning: yes (reference-audio prompting with `ref_audio` + `prompt_text`)
- asr: yes (same model transcribes; validated prompt returns a language label + tab + text)
- languages: Chinese and English (varied accents, dialects, noisy and multi-speaker conditions)
- streaming: yes (vLLM-Omni streaming client, raw PCM audio output)
- architecture: audio encoder (32 layers, hidden 1280, 20 heads, 128 mel bins, 3000 audio-context tokens) + projector + BailingMoeV3Audio MoE text backbone + optional Talker for speech output
- chinese_asr_avg: CER 3.45 (AISHELL-1 1.11, AISHELL-2 Android 2.48 / iOS 2.49, Common Voice 15zh 4.61, FLEURS zh 2.92, WenetSpeech meeting 5.54 / net 5.01)
- english_asr_avg: WER 3.69 (LibriSpeech clean 1.20 / other 2.40, Multilingual LibriSpeech 3.80, Common Voice 15 en 6.51, FLEURS en 2.86, VoxPopuli 5.37)
- dialect_asr_avg: CER 9.40 across 15 Mandarin dialects (incl. Cantonese 4.09, Sichuanese/Chongqing 4.07, Anhui 5.76, Hokkien 12.84)
- long_form_asr: AA-Earnings22-clean WER 5.78, Earnings22 WER 11.60, AISHELL-4 CER 14.76 / DER 8.58, AliMeeting DER 8.66, AMI WER 19.06
- context_asr: ContextLASR WER 1.52 / NE-WER 5.21 / NE-FNR 1.06
- audio_intelligence: BigBenchAudio 99.40, MMAU 82.00, MMAR 74.40, MMSU 78.82, MMAU-Pro 66.41, AudioMarathon 68.41, LongAudioSpan rubric 41.12, MuchoMusic 65.65
- spoken_interaction: URO-Bench-Pro 81.92, VoiceBench 86.74
- tool_calling: BFCL-V3 Audio 81.40, SpeechTCEval 82.60
- voices: built-in IP voices 灵小柔 (default), 灵楷, US_James, US_Stella; reference-audio cloning with prompt text
- serving: vLLM-Omni (OpenAI-compatible, 128K profile on 8x 80 GB H800, TP8), SGLang (text output, 4 GPUs), SGLang-Omni (2 GPUs; /v1/audio/transcriptions, /v1/audio/speech, /v1/chat/completions), Transformers with custom code (trust_remote_code)
- sibling_model: Ming-3.0-audio-tiny (9.3B total / 2.7B active, single-GPU profile)

## Comparison

- text: ✅
- video: ❌
- audio: ✅
- max_duration: —
- sample_rate: —
- license: MIT

## Innovation

The design bet is that **one audio-language model should absorb the whole assistant stack** — recognition, understanding, reasoning and spoken output — instead of chaining an ASR model into an LLM into a TTS model, each hop adding latency and losing acoustic context. Ming-3.0-audio-flash implements that as a MoE thinker (6.5B active out of 126B) behind a 32-layer audio encoder, with a Talker that can speak the answer in a built-in IP voice or a voice cloned from a reference clip. The evidence that the bet is paying off is in the numbers rather than the slogan: 3.45% Chinese CER and 3.69% English WER *including* fifteen Mandarin dialects and long-form multi-speaker meeting audio, 9.40% dialect-average CER, and best-in-class BigBenchAudio (99.40) and MMSU (78.82) against Qwen3-Omni, MiMo-V2.6 and Gemini 3.8 Flash. It also keeps the agent shape: tool calling (BFCL-V3 Audio 81.40) and spoken interaction (VoiceBench 86.74) come from the same weights, with an OpenAI-compatible server that serves transcription, chat and speech from one port.
