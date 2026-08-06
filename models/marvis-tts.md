---
release_date: "November 6, 2025"
model_name: "Marvis-TTS"
category: "tts"
summary: "Marvis-Labs — Marvis: a real-time streaming conversational TTS built on the Sesame CSM-1B architecture with a 250M multimodal-backbone + 60M audio-decoder (Kyutai mimi codec); supports zero-shot voice cloning, processes full text contextually (no regex chunking), ships MLX 4/6/8-bit variants for on-device Apple-Silicon inference; English / French / German."
slug: "marvis-tts"
---

# Marvis-TTS

**Marvis** is a conversational real-time streaming TTS from
Marvis-Labs. The architecture inherits Sesame's **CSM-1B**
(Conversational Speech Model): a 250M-parameter **multimodal
backbone** that processes interleaved text + audio tokens and
a smaller 60M-parameter **audio decoder** that models the remaining
31 RVQ codebook levels to reconstruct high-quality speech from the
backbone's representations. Audio tokens come from **Kyutai's mimi
codec** (RVQ tokens). The dual-transformer split — semantic backbone
+ small decoder — yields sub-second latency, and the model is built
for **on-edge / on-device** deployment (Apple Silicon / iPad /
iPhone / Mac). Two operational choices distinguish Marvis:

* **No regex chunking** — Marvis processes entire text sequences
  contextually, producing more natural speech flow / intonation
  than systems that pre-split text by regex patterns.
* **Zero-shot voice cloning** — pass any reference audio via
  `--ref_audio` (or pick from the bundled prompts) and the cloned
  voice is rendered in-context with the streaming output.

A family of variants ships in the official HF collection
"Marvis-TTS-250m-v0.2": the canonical 250M, MLX 4-bit / 6-bit /
8-bit quantizations, a 100M mini variant, and a transformers-ready
format. Optimized for English, French, and German.

## Links

- HuggingFace: https://huggingface.co/Marvis-AI/marvis-tts-250m-v0.2
- GitHub: https://github.com/Marvis-Labs/marvis-tts

## Features

- parameters: 250M (multimodal backbone) + 60M (audio decoder) = 310M total
- voice_cloning: yes (zero-shot; --ref_audio input + bundled sample prompts)
- asr: no
- languages: English, French, German
- streaming: yes (real-time streaming audio chunks as text is processed)
- license: Apache-2.0
- architecture: dual-transformer CSM-1B (Conversational Speech Model) — multimodal backbone + audio decoder
- audio_codec: Kyutai mimi codec (RVQ tokens; backbone models codebook 0, decoder models codebook 1–31)
- quantized_size: ~500 MB (4-bit MLX)
- training_dataset: amphion/Emilia-Dataset
- library_name: transformers, mlx, mlx-audio
- inference_cli: `mlx_audio.tts.generate --model Marvis-AI/marvis-tts-250m-v0.2 --stream --text "..." [--ref_audio ./x.wav]`
- variants_in_collection: 250m-v0.2, 250m-v0.2-MLX-{4bit,6bit,8bit}, 100m-v0.2 (+ MLX variants), 250m-v0.2-transformers
- emits_text_chunking: no (full-sequence contextual processing)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English, French, German
- streaming: ✅
- license: Apache-2.0

## Innovation

Two operational choices make Marvis stand out among conversational
TTS. First, **no regex chunking**: most streaming TTS engines
pre-split sentences by regex patterns before feeding them to the
generator, which can disrupt flow / intonation; Marvis processes
the entire text contextually, treating the text as a single
interleaved multimodal sequence. Second, the **dual-transformer
CSM-1B design** — a 250M backbone for codebook 0 (semantic) and a
smaller 60M audio decoder for codebooks 1-31 (acoustic) — produces
a quantized footprint of ~500 MB, enabling **on-device Apple-Silicon
inference** (iPad / iPhone / Mac) with real-time streaming. The
architecture makes a high-quality CSM-style TTS with zero-shot
cloning actually deployable at the edge, while the official
collection's 4 / 6 / 8-bit MLX variants let users trade footprint
for fidelity on a per-device basis.
