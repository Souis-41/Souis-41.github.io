# Automatic Speech Recognition (ASR)

# Overview:
- How to evaluate ASR systems?
  - by [Word Error Rate (WER)](en.wikipedia.org/wiki/Word_error_rate), the fewer, the better; for Chinese, Japanese or other language where charactors serve as basic unit of the language, Char Error Rate (CER) might be a better criteria
  - if the result is passed on into another system (say translation system); then the performance of the said system is a better criteria; (for example: the translation system may still have a better BLEU score even if the system has a high WER but gets all the key word right, [stated here](https://www.microsoft.com/en-us/research/publication/why-word-error-rate-is-not-a-good-metric-for-speech-recognizer-training-for-the-speech-translation-task/))
- what is the current State Of The Art (SOTA) on Japanese datasets?
  - on [CSJ](https://pj.ninjal.ac.jp/corpus_center/csj/document.html) dataset: a CER of ~5% by [Mitsubishi Electronic Research Lab](https://www.merl.com/)
  - on a publicly available dataset [jsut](https://sites.google.com/site/shinnosuketakamichi/publication/jsut) basic5k; [Google ASR API](https://cloud.google.com/speech-to-text/) achieves a CER of ~8.0%
- how well does Souis do in ASR related tasks?
  - CER ~4.7% on CSJ test set;
  - CER ~9.9% on Jsut Basic5k; Beats [IBM Watson API](https://www.ibm.com/watson/services/speech-to-text/) for a relative CER of ~41%
  - transcription time ~8 min per audio hour on 4 Nvidia GTX1080Ti using parallism

# Souis' Works
- Japanese ASR
  - a self-attention ASR network architecture; connected to a Language Model using [shallow fusion](https://arxiv.org/abs/1712.01996
)
  - a [bidirectional Language Model rescoring technique](https://arxiv.org/abs/1905.06655) finetuned from a pretrained Bert [here](http://nlp.ist.i.kyoto-u.ac.jp/index.php?BERT日本語Pretrainedモデル)
  - a Voice Activity Detection(VAD) system to segment raw audio and extract clips with utterances
  - an optional Speech Enhancement (denoise) system trained in a joint-learning manner  
  - an Auto-punctuating System for better human understanding and machine translation results

- Tibetan ASR
  - a hybrid CTC-Attention ASR network architecture; connected with Language Model using shallow fusion
  - a transfer learning technique enables the model to reach <7% Word Error Rate with only ~30h of training data beating [zhou et. al](http://tcci.ccf.org.cn/conference/2017/papers/106.pdf) (WER ~14.5%) with more convincing train-test split and no prior knowledge in Tibentan language 

# Future Works

# Read More
- where to get started on your own ASR systems
  - [EspNet](https://github.com/espnet/espnet) by JHU offers a great baseline for Pytorch Users
  - [Openseq2seq](https://github.com/NVIDIA/OpenSeq2Seq) by Nvidia offers a great baseline for Tensorflow Users
  - for Andriod applications [CMU sphinx](https://cmusphinx.github.io/) might be what you're looking for
  - [Fairseq](https://github.com/pytorch/fairseq) by Facebook AI Research Team and [RWTH ASR](https://www-i6.informatik.rwth-aachen.de/rwth-asr/) by Aachen University are great too; but might frighten beginnners because of their elaborate coding style
- augmentation methods and training tricks
  - speed perturbation
  - SpecAugment
  - compression methods
  - augment from noise
  - tuning learning rate
  - label smoothing
  - loss penalty
  - min WER training
  - training on sub-sentence units
  - training tricks for self-attention based (transformer) models
  - Spelling Correction models
- [if you are more interest in ASR theories](CTC.md)
- [ToolKits](tools.md)

\n[back](index.md)\n
