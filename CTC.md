# End-to-End ASR theories

## Connectionist Temporal Classification (CTC) <br />
  Connectionist Temporal Classification (CTC) is a method for aligning output sequence with input sequence with different lengths; proposed by Graves in 2006, [CTC](http://www.cs.toronto.edu/~graves/icml_2006.pdf) has been a standard method for training end-to-end ASR models.

## CTC decoding techniques
  - principles
  - beam-search decoding
  - best-path decoding
  - others

## CTC-alternatives
  - [Auto Segmentation Criterion (ASG)](https://arxiv.org/pdf/1902.06022.pdf) is proposed as an alternative for aligning output sequence with input sequence
  - no special blank label; use '2' for repetitions instead
    - a more concise decode graph; (Souis implemented this and saved roughly 50% computation for dp-based best-path search)
    - decoder may perform better for language modeling
  - Unnormalized scores on nodes
    - making things easier for language models ('label bias' when calculation transitions)
  - Global normalization instead of per-frame normalization
    - make it easier for confidence calculation (otherwise score gets lower for longer sentences)

## attention based / self-attention based models
  utilizing an Encoder-Decoder structure; the attention vector by its nature forms an alignment between Encoder and Decoder 

## a hybrid approach

[back](index.md)
