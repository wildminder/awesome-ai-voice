---
release_date: "August 22, 2026"
model_name: "kodama-ja-streaming-small"
category: "asr"
summary: "ayousanz — Japanese streaming ASR fully fine-tuned from Moonshine Streaming (small) on all 35,000 hours of ReazonSpeech v2; low-latency on-device CPU inference with bundled ONNX/ORT assets."
slug: "kodama-ja-streaming-small"
---

# kodama-ja-streaming-small

kodama-ja-streaming-small is a Japanese streaming speech-recognition model, fully fine-tuned from `moonshine-ai/moonshine-streaming-small` (MIT, English) on the full 35,000 hours of ReazonSpeech v2. It targets offline CPU operation and low-latency streaming, shipping a 3-graph ONNX/ORT deployment set (324 MB): a float acoustic encoder (207.9 MB; int8 quantization degrades accuracy so it is kept in float), a cross-attention KV prefill graph, and an int8 dynamic-quantized single-step decoder (83.1 MB, no CER regression). Streaming uses **bounded-tail revision (local-agreement)** with a 500 ms block; the adopted setting trades +0.0538 CER vs offline for ~883–957 ms finalization latency. It is ~5.3× faster to first partial than Vosk small. The card notes the checkpoint measures 140,135,225 parameters from the safetensors header (the base model's card says 123M).

## Links

- HuggingFace: https://huggingface.co/ayousanz/kodama-ja-streaming-small
- Demo: https://huggingface.co/spaces/hugging-apps/kodama-ja-streaming-asr

## Features

- languages: Japanese only (ja)
- streaming: yes (bounded-tail revision / local-agreement, 500 ms blocks)
- license: Apache-2.0
- parameters: 140.1M (safetensors measured; base card claims 123M)
- architecture: Moonshine Streaming encoder-decoder (10+10 layers, vocab 32,768, 16 kHz)
- base_model: moonshine-ai/moonshine-streaming-small (full fine-tune, not LoRA)
- training_data: ReazonSpeech v2 (35,000 hours, CDLA-Sharing-1.0)
- deployment: ONNX/ORT assets bundled (encoder float + int8 decoder step), CPU offline

## Comparison

- languages: Japanese
- streaming: ✅
- license: Apache-2.0

## Innovation

Brings native streaming Japanese ASR to CPU-class devices by porting Moonshine's bounded-tail revision scheme through a full-language fine-tune and quantizing only where it is safe (the per-step decoder, keeping the acoustic encoder in float). The card is unusually transparent about the streaming/offline trade-off (+0.0538 CER at the adopted latency setting vs +0.0230 for a slower frozen-free variant) and about the parameter-count discrepancy versus the upstream card.
