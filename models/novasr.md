---
release_date: "January 6, 2026"
model_name: "NovaSR"
category: "restoration"
summary: "Compact (52 kB) audio upsampler that bandlimits 16 kHz speech up to 48 kHz at extremely high realtime factors (~3500×)."
slug: "novasr"
---

# NovaSR

NovaSR is a tiny audio upsampler (~52 kB parameter count) that bandwidth-extends 16 kHz input up to 48 kHz. Public card on `YatharthS/NovaSR` advertises realtime factors around 3500× on A100, making it a candidate for real-time on-device super-resolution where model size dominates latency. Inference path is small enough to fit in CPU memory; the use case is speech-bandwidth extension without GPU.

## Links

- GitHub: https://github.com/ysharma3501/NovaSR
- HuggingFace: https://huggingface.co/YatharthS/NovaSR

## Features

- type: Audio Super-Resolution (16 kHz → 48 kHz)
- bandwidth_extension: yes (speech band BWE)
- inpainting: no
- channels: mono
- license: Apache-2.0
- parameters: 52 kB
- streamable: yes (low VRAM / runs without GPU)
- realtime_factor: ~3500× (A100)

## Comparison

- type: Audio Super-Resolution
- bandwidth_extension: ✅
- inpainting: ❌
- license: Apache-2.0

## Innovation

A 52 kB-parameter Upsampler that hits ~3500× realtime on GPU and runs on CPU — pushing bandwidth extension below the size / latency envelope where a typical neural upsampler is unacceptable (real-time on-device speech enhancement).
