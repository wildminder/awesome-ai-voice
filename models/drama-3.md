---
release_date: "October 13, 2026"
model_name: "Fish Audio Drama 3"
category: "tts"
summary: "Fish Audio Drama 3 is a 35B-parameter mixture-of-experts speech model with only 3B active per token, built on a hybrid full-plus-linear attention stack with a codebook-MTP audio decoder, aimed at multi-character dramatic speech — 16 tagged speakers, free-form director's notes, revision rounds and infill editing rather than single-voice narration."
slug: "drama-3"
---

# Fish Audio Drama 3

**Fish Audio Drama 3** is a **35-billion-parameter mixture-of-experts**
text-to-speech model with roughly **3B parameters active per token**. Its
explicit target is not narration but *dramatic performance*: multi-character
scenes with up to **16 tagged speakers**, free-form director's notes,
performative tags, multi-round revision and infill editing. The backbone is a
**hybrid attention stack** — 40 layers mixing full attention with linear
attention — over a **256-expert / 8-active MoE** whose experts are stored as
**FP8 E4M3** blocks while the remainder stays in BF16, giving a measured
**35.9B parameters** across 8 safetensors shards. The audio side uses a
**codebook-MTP decoder**: a 4-layer shared multi-token-prediction tower over
**10 codebooks** decoded causally across the whole sequence, feeding the same
**ModifiedDAC** codec as Fish Audio S2 (10 codebooks at ~21.5 Hz, 44.1 kHz
output). It was initialised from **Qwen3.5**, and post-training used **GRPO**
with a single learned human-preference reward model and no KL penalty.

## Links

- HuggingFace: https://huggingface.co/fishaudio/drama-3
- GitHub: https://github.com/fishaudio/fish-speech
- arXiv: https://arxiv.org/abs/2610.18010
- Website: https://fish.audio
- Demo: https://speech.fish.audio/
- Predecessor: https://huggingface.co/fishaudio/s2-pro

## Features

- parameters: 35.9B total with ~3B active per token (35,901,609,088 safetensors-measured across 8 shards; 62,245 tensors)
- weight_layout: 32,212,254,720 FP8 E4M3 expert params, 3,687,388,288 BF16, 1,966,080 F32; index total 39,594,895,616 bytes
- voice_cloning: yes (speaker tags and reference audio)
- asr: no
- emotion_control: yes (point tags, scoped tags, style descriptions, director's notes)
- languages: 83 (language codes in the model card; the card describes roughly 80 languages and dialects)
- streaming: yes (long text is auto-chunked and streamed per chunk)
- license: Fish Audio Community License
- architecture: FishOmniModel, model_type fish_omni, bfloat16 dtype
- attention: hybrid — full attention plus linear attention over 40 layers, hidden 2048, 16 heads, 2 KV heads, head_dim 256, attn_output_gate enabled
- moe: 256 experts with 8 active per token, moe_intermediate_size 512, shared-expert gate, bsgemm-moe quantization with 128x128 weight blocks and dynamic activation scheme
- audio_decoder: codebook_mtp_shared — 4 layers, 4 shared enrichment layers, dim 2048, audio_hidden_dim 4096, intermediate_size 6144, 10 codebooks, vocab 4096, rope_base 10000000
- context_length: 262,144 max position embeddings, vocab 252,288
- base_model: initialised from Qwen3.5
- codec: ModifiedDAC, 10 codebooks at approximately 21.5 Hz, 44.1 kHz output
- speakers: up to 16 tagged characters via `<|speaker:0|>` through `<|speaker:15|>` tags
- chunking: long text auto-chunked at roughly 300 UTF-8 bytes with up to 3 speakers per chunk, streamed per chunk
- speech_template: reference-bracket-v1
- training_data: several hundred billion tokens spanning roughly 80 languages and dialects
- post_training: GRPO reinforcement learning with a single learned human-preference reward model, no rule-based rewards and no KL penalty
- editing: editing-as-continuation via previous_takes, plus infill editing with lower WER than the Cartesia Sonic-3 infill API on Ming-Freeform-Audio-Edit in English and Chinese
- revision: multi-turn revision raises emotion accuracy from 55.5% to 58.2% and style accuracy from 76.5% to 81.8% over 3 rounds on Step-Audio-Edit
- throughput: 271 frames per second versus 177 for Fish Audio S2 on one H200 despite more than 7x the parameters
- serving: on one H200, concurrency 1 gives 166.7 frames per second with 88.9 ms median TTFA and RTF 0.131; concurrency 16 gives 927.6 frames per second with 210.1 ms median TTFA; concurrency 64 gives 1,687.3 frames per second with 450.9 ms median TTFA
- vocoder_placement: moving the vocoder to a second GPU raises concurrency-256 throughput from 2,422 to 4,160 frames per second, about 72% more, and cuts median TTFA from 3,403 ms to 2,146 ms
- vram: NVIDIA GPU with at least 48 GB for the FP8 checkpoint
- deployment: vLLM-Omni, SGLang-Omni, mlx-audio, llama.cpp, audio.cpp, CTranslate2 and ComfyUI nodes
- release: v3.0.0-beta pre-release on GitHub on October 13, 2026, with the technical report on arXiv as 2610.18010
- license_terms: research and non-commercial use free of charge; commercial use permitted while annual revenue is below the USD 500,000 revenue threshold; hosted services require a separate written license; attribution notice and a "Built with Fish Audio" display are required; voice impersonation without consent and removal of watermarks or provenance are prohibited; outputs may not be used to train other speech or audio models

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 83
- streaming: ✅
- license: Fish Audio Community License

## Additional Tools

| Tool | Type | Link |
|------|------|------|
| darioooooo0o/drama-3-w4a16-32gb | NVIDIA CUDA W4A16 int4 experts with int8 backbone, 30.7 GiB peak for 32 GB GPUs | https://huggingface.co/darioooooo0o/drama-3-w4a16-32gb |
| darioooooo0o/drama-3-w4a16 | NVIDIA CUDA W4A16 int4 experts, 41.5 GB down to 25.9 GB, about 38% smaller | https://huggingface.co/darioooooo0o/drama-3-w4a16 |
| akhaliq/drama-3-int4 | NVIDIA CUDA hybrid W4A16 GPTQ-Marlin int4, 22.1 GB, runs on Ampere A100 sm80, published WER and speaker-similarity evals | https://huggingface.co/akhaliq/drama-3-int4 |
| WaveCut/Drama-3-OrbitQuant-W4A4 | NVIDIA CUDA OrbitQuant W4A4, RPBH rotation with Lloyd-Max codebooks, 25.44 GB bundle | https://huggingface.co/WaveCut/Drama-3-OrbitQuant-W4A4 |
| WaveCut/Drama-3-OrbitQuant-W2A2 | NVIDIA CUDA OrbitQuant W2A2, 11.8 GB, smallest CUDA quant in this set | https://huggingface.co/WaveCut/Drama-3-OrbitQuant-W2A2 |
| Reza2kn/drama-3-nvfp4 | NVIDIA Blackwell NVFP4 E2M1 with E4M3 scales per 16 input channels, CUTLASS kernels, 27.42 GB total | https://huggingface.co/Reza2kn/drama-3-nvfp4 |
| asfberlin/drama-3-128e-w4a16 | NVIDIA CUDA W4A16 pruned to 128 of 256 experts by measured router usage, 12.7 GiB on disk, 15.4 GiB peak for 2 concurrent requests on RTX 5080 | https://huggingface.co/asfberlin/drama-3-128e-w4a16 |
| skysay/drama3-emo-w4 | NVIDIA CUDA mixed W4A8 with W6A8 on layer 0, emotion-calibrated over 630 seed-matched takes, for ComfyUI-Drama3 | https://huggingface.co/skysay/drama3-emo-w4 |
| mlx-community/fish-audio-drama-3-bf16 | Apple Silicon MLX BF16, 67 GB | https://huggingface.co/mlx-community/fish-audio-drama-3-bf16 |
| mlx-community/fish-audio-drama-3-8bit | Apple Silicon MLX 8-bit, 42 GB, needs a 64 GB Mac | https://huggingface.co/mlx-community/fish-audio-drama-3-8bit |
| mlx-community/fish-audio-drama-3-4bit | Apple Silicon MLX 4-bit, 22 GB | https://huggingface.co/mlx-community/fish-audio-drama-3-4bit |
| mlx-community/fish-audio-drama-3-3bit | Apple Silicon MLX 3-bit, 16.9 GB, fits a 32 GB Mac, WER 1.4% and UTMOS 4.04 | https://huggingface.co/mlx-community/fish-audio-drama-3-3bit |
| vanch007/Drama-3-MLX-BF16 | Apple Silicon MLX BF16, 69.0 GB and RTF 5.238 on M3 Max 128 GB | https://huggingface.co/vanch007/Drama-3-MLX-BF16 |
| vanch007/Drama-3-MLX-8bit | Apple Silicon MLX 8-bit affine quantization with group size 64, 32.6 GB and RTF 4.827 on M3 Max 128 GB | https://huggingface.co/vanch007/Drama-3-MLX-8bit |
| vanch007/Drama-3-MLX-4bit | Apple Silicon MLX 4-bit affine quantization with group size 64, 23.2 GB and RTF 3.453 on M3 Max 128 GB | https://huggingface.co/vanch007/Drama-3-MLX-4bit |
| fcmeyer/drama-3-MLX-3bit-HQ | Apple Silicon MLX 3-bit experts except 15 sensitivity-swept layers at 4-bit, 19.7 GB plus 1.6 GB codec, 34 GB peak on M5 Max at 2.7x real time | https://huggingface.co/fcmeyer/drama-3-MLX-3bit-HQ |
| fcmeyer/drama-3-MLX-4bit-HQ | Apple Silicon MLX 4-bit quality-weighted, 24.5 GB, 39 GB peak on M5 Max at 2.3x real time | https://huggingface.co/fcmeyer/drama-3-MLX-4bit-HQ |
| fcmeyer/drama-3-MLX-5bit | Apple Silicon MLX 5-bit, 26.3 GB, 40 GB peak on M5 Max at 2.8x real time | https://huggingface.co/fcmeyer/drama-3-MLX-5bit |
| pentacoxian-dev/drama3-small-GGUF | GGUF pruned to 45% of expert slots and distilled back to Japanese and English, IQ3_XXS at 9.74 GiB, 10.26 GiB measured peak on RTX 4090, requires an audio.cpp patch | https://huggingface.co/pentacoxian-dev/drama3-small-GGUF |
| Jmica/Drama-3-GGUF | GGUF audio.cpp-native, Q2_K, Q3_K_S and Q4_K_S expert banks with explicit backbone precision overrides | https://huggingface.co/Jmica/Drama-3-GGUF |
| EryriLabs/drama-3-llamacpp-GGUF | GGUF llama.cpp build, Q4_K experts with Q8 backbone at 20.8 GB plus a 1.7 GB mmproj, run via mara-drama3 | https://huggingface.co/EryriLabs/drama-3-llamacpp-GGUF |
| jordimas/drama-3-ct2 | CTranslate2 conversion preserving FP8 E4M3 experts and block scales, needs a custom CTranslate2 build with Drama3 support | https://huggingface.co/jordimas/drama-3-ct2 |
| PedroMarinhoDev/Drama-3-ComfyUI | ComfyUI weights for ComfyUI-Drama3, FP8 and int8 expert variants plus W4A8 and W6A8, ComfyUI v0.40+ with 8 GB VRAM and 32 to 48 GB RAM | https://huggingface.co/PedroMarinhoDev/Drama-3-ComfyUI |
| UltimateIntent/Fish-Audio-Drama-3-Q2-Q3 | ComfyUI Q2_K and Q3_K expert quants with bundled workflow JSON, ASR and synthetic-voice auxiliaries | https://huggingface.co/UltimateIntent/Fish-Audio-Drama-3-Q2-Q3 |

## Innovation

Drama 3 treats speech generation as a **directing problem** rather than a
speaking problem, and the architecture is designed around that bet. A 16-way
speaker-tag system, performative point tags such as `[sighs]` and `[laughs]`,
scoped tags like `<whisper>...</whisper>`, free-form style descriptions and
unstructured director's notes all push the user toward *staging a scene*
rather than writing a prompt and accepting one take. The second bet is
**editing as a first-class verb**: `previous_takes` turns a revision into a
continuation of the model's own output, multi-round revision measurably lifts
emotion accuracy from 55.5% to 58.2% and style accuracy from 76.5% to 81.8%,
and infill editing beats Cartesia Sonic-3's infill API on WER in both English
and Chinese. The third bet is that **sparsity plus FP8 is enough to make a
35B speech model serveable**: 256 experts at 8 active keep per-token cost
near 3B while FP8 E4M3 expert storage keeps the footprint down, and the
reported 271 frames per second on one H200 against Fish Audio S2's 177 —
despite more than 7x the parameters — is the number that makes the case.
Two design details are worth flagging for anyone building on top: the
**codebook-MTP decoder** decodes all 10 codebooks causally over the entire
sequence rather than per-frame, which is what makes long multi-speaker
scenes coherent; and the **hybrid full-plus-linear attention** stack is the
price of a 262,144-token context at this scale. The post-training recipe is
notable for what it omits — GRPO with a single learned human-preference
reward model, no rule-based rewards and no KL penalty, a deliberately small
number of moving parts for a model of this size. The community license is
also unusually concrete for a 35B speech model: commercial use is allowed
below USD 500,000 annual revenue, outputs may not be used to train other
speech or audio models, and the attribution notice is mandatory.
