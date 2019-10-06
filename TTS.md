# Text To Speech (TTS)

## overview:
- common approaches
- metrics and evaluation
- best practice today
- how well does Souis do in TTS tasks?

## Souis's work
- Souis utilizes a [Tacotron2](https://arxiv.org/abs/1712.05884)-based structure for Japanese TTS tasks, much credits to [EspNet](https://github.com/espnet/espnet/tree/master/egs/jsut/tts1), and pipes its output into a [WaveGlow structure](https://arxiv.org/abs/1811.00002) neural vocoder, and obtains [audio clips](AudioSamples.md) with really nice quality.
- Souis is still struggling to make sense of multiple speaker TTS systems, in the mean time, he uses a [voice conversion system](VoiceConversion.md) as a temporary substitute.

## features
- nothing special yet; Souis is still trying to convince his supervisor why TTS system is a critical part of the whole system; and how TTS improves Automatic Speech Recognition (ASR) performance drastically;

## future works
- Implement Multi-speaker TTS systems with Global Style Tokens
- Build an ASR-TTS chain to improve performance of both tasks

## further reading

[back](index.md)
