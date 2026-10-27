---
release_date: "March 17, 2026"
model_name: "VoXtream2"
category: "tts"
summary: "KTH Royal Institute of Technology — zero-shot full-stream TTS with dynamic speaking-rate control adjustable mid-utterance, 74 ms first-packet latency at 4x real time; English synthesis with any-language acoustic prompts."
slug: "voxtream2"
---

# VoXtream2

VoXtream2 is a zero-shot full-stream TTS model from the Department of Speech, Music and Hearing at KTH Royal Institute of Technology (Nikita Torgashov, Gustav Eje Henter, Gabriel Skantze). Its headline feature is **dynamic speaking-rate control**: distribution matching plus classifier-free guidance give fine-grained control of speech rate that can be changed *while the model is generating* — the paper demonstrates gradual speed-ups/slow-downs and sharp control-signal changes mid-utterance. It runs **4x faster than real time** with a **74 ms first-packet latency** in full-stream mode on a consumer GPU ("full-stream" meaning it begins speaking from the first word rather than waiting for a text chunk). A **translingual** capability comes from prompt text masking, so the 3–10 s reference clip can be in any language even though text input is English. The backbone follows the phone/temp/dep former stack of its predecessor VoXtream (arXiv 2509.15969, ICASSP 2026), keeping sink attention for streaming, and was trained on Emilia and HiFiTTS2. Code is Apache-2.0; weights are CC-BY-NC 4.0, and the card prohibits generating someone's speech without consent.

## Links

- HuggingFace: https://huggingface.co/herimor/voxtream2
- GitHub: https://github.com/herimor/voxtream
- arXiv: https://arxiv.org/abs/2603.13518
- Website: https://herimor.github.io/voxtream2
- Demo: https://huggingface.co/spaces/herimor/voxtream2
- Dataset: https://huggingface.co/datasets/herimor/voxtream2-train
- Predecessor: https://arxiv.org/abs/2509.15969

## Features

- parameters: 639,104,000 (462,870,528 model + 176,233,472 depth former, FP32)
- voice_cloning: yes (zero-shot from 3-10 s prompt audio; max 20 s, longer is trimmed)
- asr: no
- languages: English (acoustic prompts in any language via prompt text masking)
- streaming: yes (full-stream; 74 ms first packet, 4x real-time on consumer GPU)
- license: CC BY-NC 4.0 (weights; code Apache-2.0)
- architecture: phone_former + temp_former + dep_former_csm (depth former, CSM-style), 16 codebooks, audio vocab 2050, embedding dim 1024, speaker embedding dim 192, sink attention
- speaking_rate: dynamic, adjustable mid-utterance in syllables per second (distribution matching + classifier-free guidance)
- training_data: Emilia + HiFiTTS2 (preprocessed: herimor/voxtream2-train)
- constraints: text max 1000 chars; prompt audio 3-10 s; out-of-scope use forbids generating anyone's speech without consent
- usage: pip install "voxtream>=0.2" (espeak-ng phonemizer required)

## Comparison

- voice_cloning: ✅
- asr: ❌
- languages: English
- streaming: ✅
- license: CC BY-NC 4.0

## Innovation

Dynamic speaking-rate control is the novelty: instead of a fixed speed set at inference, the target rate (in syllables per second) acts as a continuous control signal handled with distribution matching and classifier-free guidance, and can be updated between generated frames. Combined with full-stream generation — first audio packet in 74 ms at 4x real time on a consumer GPU — and prompt text masking that makes any-language reference audio usable for English synthesis, VoXtream2 extends the low-latency streaming TTS line started by VoXtream into flexibly paced, voice-controllable territory.
