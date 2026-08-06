---
release_date: "May 6, 2026"
model_name: "Supertonic 3"
category: "tts"
summary: "Supertone — lightweight, on-device, lightning-fast TTS via ONNX Runtime; 31 languages, expression tags (laugh/breath/sigh), higher speaker similarity than v2."
slug: "supertonic-3"
---

# Supertonic 3

Supertonic 3 is the third-generation open-weight release from Supertone. It is a lightweight, on-device text-to-speech system that runs with ONNX Runtime entirely on the user's machine (no network, no API call) and ships as a Python SDK (`pip install supertonic`). Compared with the Supertonic 2 base (5 languages, 66 M params), v3 expands to **31 languages** and adds expression tags (`<laugh>`, `<breath>`, `<sigh>`), more stable reading on long utterances, and higher speaker similarity across the core language set.

## Links

- HuggingFace: https://huggingface.co/Supertone/supertonic-3
- GitHub: https://github.com/supertone-inc/supertonic
- Demo: https://huggingface.co/spaces/Supertone/supertonic-3
- PyPI: https://pypi.org/project/supertonic/

## Features

- parameters: (not stated on card; Supertonic 2 baseline 66 M — likely similar or smaller weight class)
- voice_cloning: yes (zero-shot custom voice styles via Supertonic Voice Builder)
- asr: no
- emotion_control: yes (expression tags: `<laugh>`, `<breath>`, `<sigh>`)
- languages: 31 (expanded from Supertonic 2's 5)
- streaming: yes (on-device, low-latency ONNX Runtime inference)
- license: OpenRAIL-M
- on_device: yes (ONNX Runtime, no cloud call)
- expression_tags: yes (`<laugh>`, `<breath>`, `<sigh>`)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: 31
- streaming: ✅
- license: OpenRAIL-M

## Innovation

A more compact on-device multilingual TTS: ONNX-Runtime inference everywhere, 31 languages from a single small open-weight encoder, and discrete expression tags that the decoder interprets inline — without a separate speaker-emotion control path or a cloud-rendered audio round-trip.
