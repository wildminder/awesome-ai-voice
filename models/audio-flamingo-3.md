---
release_date: "July 2025 (AF3), 2026 (AF-Next)"
model_name: "Audio Flamingo 3 (AF3) / Audio Flamingo Next"
category: "tts"
summary: "NVIDIA ADLR's fully open-source Large Audio Language Model with state-of-the-art audio understanding."
slug: "audio-flamingo-3"
---

# Audio Flamingo 3 (AF3) / Audio Flamingo Next

NVIDIA ADLR's fully open-source Large Audio Language Model with state-of-the-art audio understanding. Audio Flamingo Next (AF-Next) is the latest generation featuring stronger general audio understanding, longer context support, and timestamp-grounded reasoning.

## Links

- GitHub: https://github.com/NVIDIA/audio-flamingo
- HuggingFace: https://huggingface.co/nvidia/audio-flamingo-3
- Website: https://afnext-umd-nvidia.github.io/

## Features

- parameters: 7B
- voice_cloning: no
- asr: yes
- emotion_control: yes
- languages: Multi-lingual
- streaming: yes
- license: Apache-2.0
- context: Up to 30 minutes

## Comparison

- voice_cloning: ❌
- asr: ✅
- languages: Multi-lingual
- streaming: ✅
- license: Apache-2.0

## Innovation

**Key Innovation (AF-Next):** Staged curriculum training with GRPO-based RL post-training. Three specialized checkpoints: Instruct, Think (reasoning), and Captioner. Temporal Audio Chain-of-Thought grounding intermediate reasoning to timestamps.
