# Self-Attention

## Summary
Self-attention (also called intra-attention) is an [[attention-mechanism]] that relates different positions of a single sequence to compute a representation of that sequence.

## Explanation
Self-attention allows each position in a sequence to attend to all positions in the same sequence. This enables the model to capture dependencies regardless of their distance in the sequence.

### Key Properties
- **No Sequential Dependency**: Unlike RNNs, all positions can be processed in parallel
- **Long-Range Dependencies**: Can directly model relationships between distant tokens
- **Representation Learning**: Computes context-aware representations for each position

### Implementation
Self-attention computes three vectors for each position:
- Query (Q): What this position is looking for
- Key (K): What this position offers
- Value (V): The actual information to be passed

## Usage Across Models
- **[[Transformer]]**: Foundation of the entire architecture, replacing RNNs
- **[[BERT]]**: Bidirectional self-attention enables looking at context from both directions
- **[[GPT-3]]**: Unidirectional (masked) self-attention for autoregressive generation

## Related Concepts
- [[attention-mechanism]]
- [[multi-head-attention]]
- [[Transformer]]
- [[BERT]]
- [[bidirectional-vs-unidirectional-models]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
