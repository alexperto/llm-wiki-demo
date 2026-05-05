# Transformer

## Summary
The Transformer is a neural network architecture introduced in the paper "Attention Is All You Need" (2017) that relies entirely on [[attention mechanism]]s, dispensing with recurrence and convolutions.

## Explanation
The Transformer architecture consists of an [[encoder-decoder architecture]] using stacked [[self-attention]] and [[feed-forward networks]]. Key innovations include:

- **Multi-Head Attention**: Uses multiple attention heads to allow the model to jointly attend to information from different representation subspaces
- **Positional Encoding**: Since the model contains no recurrence or convolution, [[positional encoding]] is added to give the model information about position
- **Parallelization**: Unlike RNNs, the Transformer allows for significantly more parallelization during training

The architecture achieved state-of-the-art results on machine translation tasks (28.4 BLEU on WMT 2014 English-to-German) while requiring less time to train.

## Architecture Components
- Encoder: Stack of N=6 identical layers, each with [[multi-head attention]] and [[feed-forward networks]]
- Decoder: Stack of N=6 identical layers with an additional cross-attention layer

## Related Concepts
- [[attention mechanism]]
- [[self-attention]]
- [[multi-head attention]]
- [[encoder-decoder architecture]]
- [[positional encoding]]
- [[BERT]]
- [[GPT-3]]

## References
- Paper: "Attention Is All You Need" (Vaswani et al., 2017)
- ArXiv: 1706.03762v7
