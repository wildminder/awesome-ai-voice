---
release_date: "July 7, 2026"
model_name: "FreyaTTS"
category: "tts"
summary: "FreyaVoice — 183M-parameter Turkish speech-synthesis foundation model; tokenizer-free at the character level (92 symbols, no phonemizer, no G2P), non-autoregressive conditional flow-matching DiT in the frozen AudioVAE2 latent space (25 Hz, 64-dim, 16 kHz encode / 48 kHz decode). Trained from scratch on Turkish speech; single target speaker, no cloning."
slug: "freyatts"
---

# FreyaTTS

**FreyaTTS** is a 183M-parameter Turkish text-to-speech model. It is
**tokenizer-free at the character level** — 92 symbols in its Turkish
vocabulary — so there is no phonemizer or G2P step in either training
or inference. Speech is generated with a **non-autoregressive
conditional flow-matching DiT** in the frozen
[AudioVAE2](https://huggingface.co/openbmb/VoxCPM2) latent space
(25 Hz, 64-dim latents, 16 kHz encode / 48 kHz decode). Training
runs from scratch on Turkish speech: a pretraining stage followed
by SFT stage 1/2 for voice lock and short-utterance coverage.
Output is 48 kHz mono. On the project's Freya-TR-Eval benchmark
the model reports **WER 8.0% / CER 3.0%**, ranking 3rd of 7 among
open sub-1B Turkish TTS systems — a deliberate **single-target-speaker,
no-cloning** design choice for a focused foundation release.
The evaluation dataset is
[freya-tr-eval](https://huggingface.co/datasets/freyavoice/freya-tr-eval).

## Links

- HuggingFace: https://huggingface.co/freyavoice/Freya-TTS
- GitHub: https://github.com/freyavoiceai/FreyaTTS
- Paper: https://arxiv.org/abs/2607.09530

## Features

- parameters: 183.2M
- voice_cloning: no (single target speaker, no zero-shot cloning)
- asr: no
- languages: Turkish (tr)
- streaming: no (non-autoregressive; 32-step Euler ODE renders utterance offline)
- license: Apache-2.0
- architecture: conditional flow-matching diffusion transformer (DiT), non-autoregressive, 32-step Euler ODE, no CFG
- tokenizer: character-level (92 Turkish symbols; no phonemizer, no G2P)
- latent_space: frozen AudioVAE2 (Apache-2.0, openbmb/VoxCPM2), 64-dim at 25 Hz
- codec_io: 16 kHz encode / 48 kHz decode
- sample_rate: 48,000 Hz
- training: from scratch on Turkish speech; pretraining + SFT stage 1/2 (voice lock + short-utterance coverage)
- evaluation: Freya-TR-Eval — WER 8.0% / CER 3.0%, 3rd of 7 open sub-1B Turkish TTS
- library_name: freyatts

## Comparison

- voice_cloning: ❌
- asr: ❌
- languages: Turkish
- streaming: ❌
- license: Apache-2.0

## Innovation

Two design choices are worth flagging. First, **tokenizer-free
character-level Turkish**: by training directly on the 92-symbol
Turkish alphabet with no phonemizer or G2P grapheme-to-phoneme step,
the model removes a dependency that is fragile for agglutinative
Turkish morphology and that often degrades quality when ported to
low-resource Turkic relatives. Second, **non-autoregressive
conditional flow-matching in a frozen AudioVAE2 latent space**:
the 25 Hz / 64-dim bottleneck keeps the DiT small (183M) while
inheriting a separately-trained audio codec's representation,
letting a focused single-language-non-multilingual release ship at
a fraction of the parameter budget of multilingual foundation TTS
systems. The deliberate "no cloning, single target speaker" choice
is a scope-lowering move that lets the foundation release put all
its capacity into Turkish speech quality rather than spread it
across zero-shot speaker adaptation.
