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

### Encoder
Stack of N=6 identical layers, each containing:
1. **[[Multi-head attention]]** sublayer
2. **[[Feed-forward networks]]** sublayer
3. **[[Residual connections]]** around each sublayer
4. **[[Layer normalization]]** applied twice per layer

### Decoder
Stack of N=6 identical layers with:
1. **Masked [[multi-head attention]]** (self-attention on output)
2. **Cross-attention** to encoder output
3. **[[Feed-forward networks]]** sublayer
4. **[[Residual connections]]** around all three sublayers
5. **[[Layer normalization]]** applied three times per layer

### Transformer Block Structure
Each layer follows this pattern:
```
x = LayerNorm(x + MultiHeadAttention(x))
x = LayerNorm(x + FeedForward(x))
```

The combination of [[residual connections]] and [[layer normalization]] enables:
- Training of deep networks (12-96+ layers in modern LLMs)
- Stable gradient flow
- Preservation of information through layers

## Related Concepts
- [[attention mechanism]]
- [[query-key-value]]
- [[self-attention]]
- [[multi-head attention]]
- [[encoder-decoder architecture]]
- [[positional encoding]]
- [[layer normalization]]
- [[residual connections]]
- [[feed-forward networks]]
- [[contextual embeddings]]
- [[tokenization]]
- [[BERT]]
- [[GPT-3]]

## References
- Paper: "Attention Is All You Need" (Vaswani et al., 2017)
- ArXiv: 1706.03762v7
