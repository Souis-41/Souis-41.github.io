# Automatic Speech Recognition (ASR)

- Overview:
  - what is ASR?
  - where can you apply ASR techniques?
  - what is the current State Of The Art (SOTA) of ASR technique?
    - on [CSJ](https://pj.ninjal.ac.jp/corpus_center/csj/document.html) dataset: a [Char Error Rate(CER, the fewer, the better)](en.wikipedia.org/wiki/Word_error_rate) of ~5% by [Mitsubishi Electronic Research Lab](https://www.merl.com/)
    - on a publicly available dataset [jsut](https://sites.google.com/site/shinnosuketakamichi/publication/jsut) basic5k; [Google ASR API](https://cloud.google.com/speech-to-text/) achieves a CER of ~8.0%
  - how well does Souis do in ASR related tasks?
    - CER ~4.7% on CSJ test set;
    - CER ~10.1% on Jsut Basic5k; Beats [IBM Watson API](https://www.ibm.com/watson/services/speech-to-text/) for a relative CER of ~41%
    - transcription time ~8 min per audio hour on 4 Nvidia GTX1080Ti using parallism

- Souis' Works
  - Japanese ASR
    - a self-attention ASR network architecture; connected to a Language Model using shallow fusion
    - a [bidirectional Language Model rescoring technique](https://arxiv.org/abs/1905.06655) finetuned from a pretrained Bert [here](http://nlp.ist.i.kyoto-u.ac.jp/index.php?BERT日本語Pretrainedモデル)
    - a Voice Activity Detection(VAD) system to segment raw audio and extract clips with utterances
    - an Auto-punctuating System for better human understanding and translation results

  - Tibetan ASR
    - a hybrid CTC-Attention ASR network architecture; connected with Language Model using shallow fusion
    - a transfer learning technique enables the model to reach <12% Word Error Rate with only ~30h of training data beating [zhou et. al](http://tcci.ccf.org.cn/conference/2017/papers/106.pdf) with a relative WER of ~10%
    
  - MORE ...

- Key Features:

- Future Work

- Read More
  - where to get started on your own ASR systems:
  - augmentation methods and training tricks
  
