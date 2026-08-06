---
release_date: "July 9, 2026"
model_name: "MOSS-Transcribe-Diarize"
category: "asr"
summary: "OpenMOSS / MOSI.AI — end-to-end 0.9B long-form multi-speaker ASR with built-in speaker diarization, timestamps, and optional acoustic event tags from a single checkpoint (Qwen3-0.6B text backbone + Whisper-Medium audio encoder)."
slug: "moss-transcribe-diarize"
---

# MOSS-Transcribe-Diarize

**MOSS-Transcribe-Diarize 0.9B** is OpenMOSS's open-source SOTA
end-to-end audio-understanding model for long-form multi-speaker
transcription. Instead of stitching a separate ASR and diarization
system, the model **jointly** transcribes speech and assigns speaker
labels, producing time-aligned text with precise timestamps and
consistent speaker tags such as `[S01]`, `[S02]` in a single pass.
Built for meetings, calls, podcasts, interviews, lectures, and video
content. Optional acoustic-event annotations extend the output to
"[start][Sxx]text[end]" segments plus `[event]` tags for non-speech
sounds. Architecture: Qwen3-style 0.6B text backbone + Whisper-Medium
audio encoder (16 kHz, 80 mel bins, 30 s chunks) joined by a 4× temporal
merge + MLP audio-text adaptor.

## Links

- GitHub: https://github.com/OpenMOSS/MOSS-Transcribe-Diarize
- HuggingFace: https://huggingface.co/OpenMOSS-Team/MOSS-Transcribe-Diarize
- Paper: https://arxiv.org/abs/2601.01554

## Features

- parameters: 0.9B total
- voice_cloning: no
- asr: yes (joint ASR + diarization)
- pronunciation: yes (Whisper-Medium encoder captures phonetic content)
- emotion_control: no
- languages: Multilingual (model card: long-form speech unspecified languages; English demo)
- streaming: yes (chunked inference)
- license: Apache-2.0
- output_format: "[start_seconds][Sxx]text[end_seconds]" segments
- diarization: built-in ([S01], [S02], ...)
- acoustic_event_tags: yes (optional)
- text_backbone: Qwen3-0.6B causal decoder
- audio_encoder: Whisper-Medium, 16 kHz, 80 mel bins, 30 s chunks
- audio_text_bridge: 4× temporal merge + MLP adaptor
- inference: vLLM, SGLang Omni, transformers, HF inference API

## Comparison

- languages: Multilingual
- streaming: ✅
- license: Apache-2.0

## Innovation

**Joint** speech transcription + speaker diarization in a **single
end-to-end checkpoint** with the canonical `[Sxx]` output format
embedded in the transcript. Most production pipelines stitch a
separate ASR model to a separate diarization model (and reconcile
speaker turns post-hoc) — MOSS-Transcribe-Diarize folds them into
one model so the timestamps, speaker labels, and event tags come out
of the same forward pass. Adding a Qwen3-style text decoder on top
of Whisper-Medium audio features lets the model explicitly reason
about speaker continuity in the textual stream rather than as a
postprocess.
