# Text To Speech (TTS)

## overview:
- metrics and evaluation
- best practice today
  - a mel-spectrogram or STFT-spectrogram is first generated;
  - a vocoder is used to generate audio from spectrograms;
  while earlier works add emotion and speaker-related information in the vocoder-step; recent advances tend to add all these variations in the spectrogram.
- how well does Souis do in TTS tasks?  
  nothing much yet; Souis is still trying to convince his supervisor why TTS system is a critical part of the whole system; and how TTS improves Automatic Speech Recognition (ASR) performance drastically;

## Souis's work
- Souis utilizes a [Tacotron2](https://arxiv.org/abs/1712.05884)-based structure for Japanese TTS tasks, much credits to [EspNet](https://github.com/espnet/espnet/tree/master/egs/jsut/tts1), and pipes its output into a [WaveGlow structure](https://arxiv.org/abs/1811.00002) neural vocoder, and obtains [audio clips](AudioSamples.md) with really nice quality.
- Souis is still struggling to make sense of multiple speaker TTS systems, in the mean time, he uses a [voice conversion system](VoiceConversion.md) as a temporary substitute.

## features
- tacotron2-based structure/ transformer-based structure
- global style token for capturing multi-speaker features
- extracting [x-vector](http://www.danielpovey.com/files/2018_icassp_xvectors.pdf) [(recipe by kaldi)](https://github.com/kaldi-asr/kaldi/tree/master/egs/sre08) as speaker token

## future works
- Implement Multi-speaker TTS systems with Global Style Tokens or speaker token
- Build an ASR-TTS chain to improve performance of both tasks

[back](index.md)
