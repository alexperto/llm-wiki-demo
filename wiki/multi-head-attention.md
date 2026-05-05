# Multi-Head Attention

## Summary
An [[attention mechanism]] that uses multiple attention functions in parallel, allowing the model to jointly attend to information from different representation subspaces at different positions.

## Explanation
Multi-head attention is a key component of the [[Transformer]] architecture. Instead of performing a single attention function, it runs multiple attention mechanisms in parallel and concatenates their outputs.

### How It Works
1. Project queries, keys, and values into h different learned subspaces
2. Perform [[self-attention]] in parallel across all heads
3. Concatenate the outputs
4. Apply final linear projection

### Benefits
- **Multiple Representation Subspaces**: Different heads can learn different types of relationships
- **Richer Representations**: Captures diverse aspects of input simultaneously
- **Prevents Attention Collapse**: Counteracts effect of averaging attention-weighted positions

### Architecture Details
The [[Transformer]] paper uses:
- 8 attention heads in parallel
- Reduced dimensionality per head (d_model / h)
- Computational cost similar to single full-dimensional attention

## Usage Across Models
- **[[Transformer]]**: Core building block of encoder and decoder
- **[[BERT]]**: Used in every layer of the bidirectional encoder
- **[[GPT-3]]**: Used throughout the autoregressive model

## Related Concepts
- [[attention mechanism]]
- [[self-attention]]
- [[Transformer]]
- [[BERT]]
- [[GPT-3]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
