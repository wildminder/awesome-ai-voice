---
release_date: "May 21, 2026"
model_name: "Miso TTS"
category: "tts"
summary: "Miso Labs — 8.3B Sesame-style Conversational Speech Model (CSM) with Llama 3.2 8B backbone + 300M AR audio decoder over Mimi codec; prompt-audio voice continuation."
slug: "misotts"
---

# Miso TTS

Miso TTS 8B is a text-to-speech model from Miso Labs built on the Sesame Conversational Speech Model (CSM) architecture. A large Llama-3.2-style backbone consumes text/audio-frame embeddings and predicts codebook 0 of the Mimi audio token stream, while a smaller 300M autoregressive audio decoder predicts codebooks 1–31 in codebook depth. The model is designed for high-quality conversational speech and voice continuation from a short prompt audio clip.

## Links

- HuggingFace: https://huggingface.co/MisoLabs/MisoTTS
- GitHub: https://github.com/MisoLabsAI/MisoTTS
- Website: https://misolabs.ai

## Features

- parameters: 8B (backbone llama-3.2-style) + 300M (audio decoder) = 8.3B
- voice_cloning: yes (prompt-audio continuation)
- asr: no
- languages: English
- streaming: no
- license: MIT (Modified MIT — © Kamino Learning, Inc., 2026)
- architecture: Sesame-style CSM (two transformer stack: backbone + audio decoder)
- audio_tokenizer: Mimi (32 codebooks, vocab 2051, max seq 2048)
- library: pytorch

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English
- streaming: ❌
- license: MIT

## Innovation

A two-transformer Sesame-style CSM (Llama 8B backbone consumes text + audio frames and produces backbone codebook-0 prediction; a 300M audio decoder autoregresses over codebook depth via Mimi's 32-codebook stack) — letting the larger backbone spend capacity on linguistic / speaker conditioning while a leaner decoder handles fine-grained codebook-by-codebook generation.
