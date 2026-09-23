---
release_date: "August 3, 2026"
model_name: "NVIDIA NemotronLabs VoiceChat 11B"
category: "a2a"
summary: "NVIDIA — an 11B end-to-end full-duplex speech-to-speech model that unifies streaming speech understanding and generation in one architecture instead of an ASR → LLM → TTS cascade; ~450 ms turn-taking, instant barge-in, and the first open full-duplex model with tool calling, using per-tool 'on-hold' speech to cover tool latency."
slug: "nemotronlabs-voicechat-11b"
---

# NVIDIA NemotronLabs VoiceChat 11B

**NVIDIA NemotronLabs VoiceChat** is an **11B end-to-end, real-time speech
full-duplex (FD) model** for conversational AI that jointly performs
streaming speech understanding and speech generation in **one unified
architecture** — no ASR → LLM → TTS cascade, no API handoffs between models,
and therefore no stacked end-to-end latency. It listens and speaks
simultaneously, so it handles natural turn-taking (**~450 ms response**),
**barge-in** (the user cuts in and the model yields instantly) and mid-turn
pauses without a rigid request/response cycle. Architecturally it encodes
audio with a **Fast Conformer** streaming encoder, feeds the audio tokens
into a **Nemotron Nano V2 9B LLM backbone** to predict text tokens, and
decodes those to audio codes with an **NVIDIA TTS decoder and codec** — while
a **separate output channel** emits tool-calling scripts. That separate
channel is what makes VoiceChat **the first open full-duplex model to support
tool calling**: each tool can define an **"on-hold" message** spoken the
moment the LLM emits the triggering text, so the conversation keeps flowing
naturally while the tool executes. It ranks **#2 among all open full-duplex
models** on VoiceBench and **#2 among all open models** on Full-Duplex-Bench
1.0.

## Links

- HuggingFace: https://huggingface.co/nvidia/NVIDIA-NemotronLabs-VoiceChat-11B
- arXiv: https://arxiv.org/abs/2609.21967
- GitHub: https://github.com/NVIDIA-NeMo/Speech/tree/nemotron-labs-voicechat

## Features

- parameters: 11B (11,095,371,252 safetensors-measured)
- license: OpenMDW-1.1 (Open Model Development Weight License Agreement v1.1)
- text: yes (text prompt in; agent text plus user transcription out)
- video: no
- audio: yes (user speech in at 16 kHz; agent speech out at 22.05 kHz)
- max_duration: not stated
- sample_rate: 22.05 kHz output / 16 kHz input
- architecture: hybrid Mamba/Transformer — Fast Conformer streaming speech encoder + Nemotron Nano V2 9B LLM backbone + NVIDIA TTS decoder and codec + a separate tool-calling output channel
- encoder: Fast Conformer from nvidia/nemotron-speech-streaming-en-0.6b
- base_model: nvidia/NVIDIA-Nemotron-Nano-9B-v2
- duplex: full duplex (simultaneous listen and speak)
- turn_taking_latency: ~450 ms (448 ms measured, smooth turn-taking)
- barge_in: yes (user interruption TOR 1.0, 480 ms latency)
- tool_calling: yes — first open full-duplex model with tool calling; per-tool "on-hold" speech covers tool execution; `<TOOLCALL>[{...}]</TOOLCALL>` control format
- voicebench: #2 among all open full-duplex models
- full_duplex_bench_1: #2 among all open models
- pause_handling_tor: 0.153 (Synthetic) / 0.255 (Candor), lower is better
- smooth_turn_taking: TOR 0.82 / latency 448 ms
- user_interruption: TOR 1.0 / latency 480 ms / GPT-4o judge 4.33
- au_harness_bfcl_v3: simple 58.5% / multiple 62.5% / parallel 42.5% / parallel-multiple 27.5% / irrelevance 89.6% / average 56.1%
- full_duplex_bench_v3: tool selection 82.5% / argument accuracy 42.2% / pass@1 33%
- training_data: ~550k hours of audio plus text, real and synthetic
- training_sources: Nemotron 5.5 pre-training and SFT text, Brainy-mantis, Greteal AI v1/v2, UltraChat, Blackwell studio recordings, Fisher, LibriVox, LibriTTS, HiFi-TTS, Riva Speakers (internal), internet-scale public data, PromptTTS, VCTK, Voxmovies, JL-Corpus, Nemotron Nano v3 function-calling data, PersonaPlex training data
- runtime: vLLM
- hardware: NVIDIA A100, H100, H200, B100, B200, RTX-6000
- os: Linux only
- deployment: offline batch speech-to-speech from the HF checkpoint; interactive low-latency streaming via the NVIDIA inference container (bidirectional WebSocket with function calling)
- dependencies: NeMo Speech repo (`nemotron-labs-voicechat` branch), torch 2.10.0, transformers 4.56.0, mamba-ssm 2.3.2.post1, causal-conv1d 1.6.2.post1
- version: v1.0
- intended_use: ASR, TTS and voice-assistant development for researchers and developers

## Comparison

- text: ✅
- video: ❌
- audio: ✅
- max_duration: —
- sample_rate: 22.05 kHz
- license: OpenMDW-1.1

## Innovation

The cascade being replaced here is the whole point: **ASR → LLM → TTS** stacks
serialize three models' latencies and hand audio off as text, which makes
natural back-and-forth structurally impossible. VoiceChat collapses that into
a single model that **listens and speaks at once**, and the measured
consequences are the interesting part — 448 ms smooth turn-taking, and on
user interruption a TOR of 1.0 with a 480 ms yield, meaning the model does
not finish its sentence over the top of the user. The genuinely novel piece
is **tool calling in a duplex setting**. A tool call is a latency spike in a
conversation: the user hears silence while an API resolves. VoiceChat's fix
is architectural rather than a prompt trick — a **dedicated output channel**
predicts the tool-call script separately from the spoken channel, and each
tool can declare an **"on-hold" message** that is spoken as soon as the
triggering text is generated, so the agent *talks over its own tool
latency* instead of stalling. That is what makes it the first open
full-duplex model to do this. The benchmark table also deserves an honest
read rather than a headline: tool **selection** is strong (82.5% on
Full-Duplex-Bench v3, 89.6% irrelevance rejection on AU-Harness), but
**argument accuracy is 42.2% and pass@1 is 33%** — spoken tool arguments are
a genuinely hard problem (names, numbers and IDs must survive the audio
round-trip), so the capability is real and the remaining gap is visible.
The hybrid Mamba/Transformer backbone and reuse of NVIDIA's own streaming
Conformer encoder and Nemotron Nano V2 LLM show the design is assembled from
components the lab had already validated, which is why the release reads as
an integration milestone for open voice agents rather than a single-model
result.
