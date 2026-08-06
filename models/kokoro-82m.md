---
release_date: "January 27, 2025 (v1.0)"
model_name: "Kokoro-82M"
category: "tts"
summary: "Kokoro is an open-weight Text-to-Speech model with 82 million parameters."
slug: "kokoro-82m"
---

# Kokoro-82M

Kokoro is an open-weight Text-to-Speech model with 82 million parameters. Despite its lightweight architecture, it delivers comparable quality to larger models while being significantly faster and more cost-efficient. With Apache-licensed weights, Kokoro can be deployed anywhere from production environments to personal projects.

## Links

- GitHub: https://github.com/hexgrad/kokoro
- HuggingFace: https://huggingface.co/hexgrad/Kokoro-82M
- Demo: https://hf.co/spaces/hexgrad/Kokoro-TTS

## Features

- parameters: 82M
- architecture: StyleTTS 2, ISTFTNet
- voice_cloning: yes
- asr: no
- pronunciation: yes (via misaki G2P)
- emotion_control: yes
- languages: 8 (54 voices)
- streaming: yes (generator pattern)
- cost: <$0.06 per hour of audio
- license: Apache-2.0
## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 8
- streaming: ✅
- license: Apache-2.0
