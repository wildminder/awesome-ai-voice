---
release_date: "April 17, 2026"
model_name: "Dramabox"
category: "tts"
summary: "Resemble AI — expressive TTS with zero-shot voice cloning built as an IC-LoRA fine-tune of LTX-2.3 3.3B (DiT + flow matching), conditioned on Gemma 3 12B text embeddings and driven by prompt-scene descriptions."
slug: "dramabox"
---

# Dramabox

Dramabox is Resemble AI's expressive TTS, distributed under the LTX-2 Community License. It is an IC-LoRA fine-tune of the LTX-2.3 3.3B audio-only branch (Diffusion Transformer + flow matching), conditioned on Gemma 3 12B text embeddings. Generation is **prompt-driven**: speaker identity, emotion, delivery, laughs, sighs, breaths, pauses, and transitions are all expressed inside a natural-language description, with an optional 10-second voice reference that clones the target timbre.

## Links

- HuggingFace: https://huggingface.co/ResembleAI/Dramabox
- GitHub: https://github.com/resemble-ai/DramaBox
- Demo: https://huggingface.co/spaces/ResembleAI/Dramabox
- Website: https://www.resemble.ai/learn/models/dramabox

## Features

- parameters: 3.3B (LTX-2.3 audio backbone, IC-LoRA fine-tune) + 12B Gemma 3 text encoder (conditioning only)
- voice_cloning: yes (10+ s voice reference, prompt-driven timbre)
- asr: no
- emotion_control: yes (prompt-driven scene descriptions: laughs, sighs, breaths, pauses, transitions)
- languages: English
- streaming: no
- license: Other (LTX-2 Community License)
- base_model: Lightricks/LTX-2.3 (audio branch)
- architecture: DiT + flow matching, IC-LoRA fine-tune, Gemma 3 12B text embeddings
- inference_time: ~2.5 s / generation (warm server)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English
- streaming: ❌
- license: Other

## Innovation

IC-LoRA fine-tune of LTX-2.3's audio branch leaves the heavy text-understanding work to Gemma 3 12B and lets the DiT do the expressive rendering — so what's normally multimodal-stage orchestration collapses into a single prompt-driven TTS where speaker identity, emotion, and delivery are encoded in the prompt itself, and the timbre comes from a 10-second voice reference when present.
