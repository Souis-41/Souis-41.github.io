# Language Modeling

1. why language modeling?  
language model, together with acoustic model and pronunciation model, has been a key component in a traditional ASR pipeline; but recent advances in end-to-end ASR systems do not necessarily require a language model
  - capture relationships amongst charactors, word-pieces, words, or sentence-pieces; essential in CTC-based methods (as an abundance of <blank> and repeated parts breaks the connections of different parts)
  - make use of massive unpaired text data

2. how to utilize language models in ASR systems?
  - rescoring:  
  ASR models propose several sequences with scores; language models rescore them; pick best.
    - beam search + second pass rescoring
    - lattice rescoring
  - augmented ASR scorings:  
  ASR models and Language models both give scores; propose sequences with augmented scores.
    - shallow fusion
    - deep fusion
    - cold fusion
    
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
