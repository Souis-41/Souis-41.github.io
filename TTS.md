# Text To Speech (TTS)

## overview:
- metrics and evaluation
- best practice today
  - a mel-spectrogram or STFT-spectrogram is first generated;
  - a vocoder is used to generate audio from spectrograms;
  while earlier works add emotion and speaker-related information in the vocoder-step; recent advances tend to add all these variations in the spectrogram.
- how well does Souis do in TTS tasks?  
  he has built a baseline system from [EspNet recipe](https://github.com/espnet/espnet)
- [Single Speaker Sample Audios](resources/AudioSamples.md)

## Souis's work
- Souis utilizes a [Tacotron2](https://arxiv.org/abs/1712.05884)-based structure for Japanese TTS tasks, much credits to [EspNet](https://github.com/espnet/espnet/tree/master/egs/jsut/tts1), and pipes its output into a [WaveGlow structure](https://arxiv.org/abs/1811.00002) neural vocoder, and obtains [audio clips](resources/AudioSamples.md) with really nice quality.
- Souis uses a [voice conversion system](VoiceConversion.md) as a backup-plan.
- According to a [recent work by Google](https://arxiv.org/abs/1909.11699), acoustic and lexical diversity as well as speaker diversity is required to enhance speech recognition performance.
  - Acoustic & lexical diversity could be achieved through perplexty calculated by language models (desirably trained on transcript of the original training set).
  - Speaker embedding randomly chose from seen clips generates audio more plausible than sampled on some distribution.
- on [Vocoders](Vocoders.md)

## features
- tacotron2-based structure/ transformer-based structure
- extracting [x-vector](http://www.danielpovey.com/files/2018_icassp_xvectors.pdf) with a plug-in-and-use [(recipe by kaldi)](https://github.com/kaldi-asr/kaldi/tree/master/egs/sre08) as speaker token; giving a somewhat plausible result for multi speakers

## future works
- Implement Multi-speaker TTS systems with Global Style Tokens
- Build an ASR-TTS chain to improve performance of both tasks
- Souis cannot improve ASR results using TTS generated audio yet; much may due to the fact that Japanses use pitch accent and tone, both systems failed to capture related features and galloped astray together. He is making use of addional linguistic features as inputs, hoping the TTS model could generate better audio.

[back](index.md)
