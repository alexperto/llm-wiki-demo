# Attention Mechanism

## Summary
An attention mechanism allows a model to focus on different parts of the input when producing each part of the output, enabling modeling of dependencies without regard to their distance in sequences.

## Explanation
Attention mechanisms have become integral to sequence modeling and transduction models. The [[Transformer]] paper introduced **scaled dot-product attention** as the core building block.

### Types of Attention
- **Self-Attention**: Relates different positions of a single sequence to compute a representation (see [[self-attention]])
- **Cross-Attention**: Attends from one sequence to another (used in encoder-decoder models)
- **Multi-Head Attention**: Uses multiple attention mechanisms in parallel (see [[multi-head attention]])

### Scaled Dot-Product Attention
The attention function computes a weighted sum of values based on the similarity between queries and keys. The scaling factor prevents gradients from becoming too small in high dimensions.

## Evolution Across Papers
- **Transformer (2017)**: Introduced as the sole mechanism, replacing recurrence entirely
- **BERT (2018)**: Used bidirectional self-attention for [[pre-training]]
- **GPT-3 (2020)**: Employed in autoregressive (unidirectional) manner for [[language modeling]]

## Related Concepts
- [[self-attention]]
- [[multi-head attention]]
- [[Transformer]]
- [[BERT]]
- [[encoder-decoder architecture]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
