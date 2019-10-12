# Language Modeling

1. why language modeling?  
language model, together with acoustic model and pronunciation model, has been a key component in a traditional ASR pipeline; but recent advances in end-to-end ASR systems do not necessarily require a language model; yet we still need them for:
  - capturing relationships amongst charactors, word-pieces, words, or sentence-pieces; essential in CTC-based methods (as an abundance of <blank> and repeated parts breaks the connections of different parts)
  - making use of massive unpaired text data

2. how to utilize language models in ASR systems?
  - rescoring:  
  ASR models propose several sequences with scores; language models rescore them; pick best.
    - beam search + second pass rescoring  
    after the whole sequence is proposed; both uni-directional language models and bi-directional language models can be used for rescoring.  
    bi-directional lms sounds better than uni-directional lms; but only marginal gain can be observed before you have both strong ASR models and language models, [this work](https://arxiv.org/abs/1905.06655) was the first to achieve a significant improvement;
    **TODO: add explanation here** 
    - lattice rescoring  
    save resources significantly; fit for n-gram language models;  
    [this work](http://mi.eng.cam.ac.uk/~xc257/papers/RNNLM_latrescore.pdf) and [this work in Kaldi](http://danielpovey.com/files/2018_icassp_lattice_pruning.pdf) proposes novel methods to cluster RNNLM states to fit into lattice rescoring techniques  
    **TODO: add explanation here** 
  - augmented ASR scorings:  
  ASR models and Language models give weighted scores together; propose sequences accodingly.
    - shallow fusion  
    best practice; easiest to implement;  
    **TODO: add explanation here** 
    - deep fusion  
    **TODO: add explanation here** 
    - cold fusion  
    **TODO: add explanation here** 

3. training and decoding theories
  - count-based models (n-grams):
  - lstm-based models:
  - self-attention based models

4. toolkits
  - KenLM
  - gensim
  - fairseq (lstm or transformer)
  - pytorch-transformer (transformer, bert)

[back](index.md)
