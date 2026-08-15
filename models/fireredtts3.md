---
release_date: "August 5, 2026"
model_name: "FireRedTTS3"
category: "tts"
summary: "FireRedTeam — unified speech generation & editing (zero-shot voice cloning across 24 languages + 21 Chinese dialects; instruction-based voice design and semantic/acoustic speech editing) built on semantically enriched continuous speech representations."
slug: "fireredtts3"
---

# FireRedTTS3

FireRedTTS3 is a unified speech generation and editing system from the FireRed Team built on semantically enriched continuous speech representations. It ships in two variants: **FireRedTTS3-Base** (zero-shot voice cloning across 24 languages and 21 Chinese dialects) and **FireRedTTS3-Instruct** (natural-language voice design and combined semantic + acoustic speech editing in one model). Beyond cloning, it supports instruction-based voice design (no reference audio needed) and editing operations such as insertion / deletion / substitution (semantic) and speed / pitch / volume changes (acoustic).

## Links

- HuggingFace: https://huggingface.co/FireRedTeam/FireRedTTS3
- GitHub: https://github.com/FireRedTeam/FireRedTTS3

## Features

- voice_cloning: yes (zero-shot, 24 languages + 21 Chinese dialects)
- asr: no
- languages: 24 (plus 21 Chinese dialects)
- license: Apache-2.0
- architecture: Qwen3 backbone + patch-level diffusion autoregressive (DiTAR) + RedAE codec + CAM++ speaker encoder
- variants: Base (cloning), Instruct (cloning + voice design + editing)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 24
- license: Apache-2.0

## Innovation

Represents speech with semantically enriched *continuous* (non-quantized) representations, enabling a single system to do zero-shot cloning, text-driven voice design, and fine-grained semantic + acoustic editing. On Seed-TTS-eval it reaches an average WER/CER of 3.04% with 78.8% speaker similarity; MiniMax-MLS-Test average SIM 84.8%.

## Additional Tools

| Tool | Type | Link |
|------|------|------|
| FireRedTTS3-ComfyUI | ComfyUI node | https://github.com/Saganaki22/FireRedTTS3-ComfyUI |
