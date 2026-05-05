# Positional Encoding

## Summary
A mechanism to inject information about token positions into the [[Transformer]] model, compensating for the lack of sequential structure in the attention mechanism.

## Explanation
Since the [[Transformer]] architecture contains no recurrence or convolution, it has no inherent notion of token order. Positional encoding solves this by adding position-dependent signals to the input embeddings.

### Why It's Needed
[[Attention mechanism]]s are permutation-invariant:
- Self-attention treats input as a set, not a sequence
- Without positional information, "cat ate mouse" = "mouse ate cat"
- Position encoding restores sequential structure

### Implementation in Transformer
The [[Transformer]] paper proposed using sinusoidal functions:
- Different frequencies for different dimensions
- Allows model to attend to relative positions
- Parameter-free (no learned parameters)

### Formula
Uses sine and cosine functions of different frequencies:
- PE(pos, 2i) = sin(pos / 10000^(2i/d_model))
- PE(pos, 2i+1) = cos(pos / 10000^(2i/d_model))

Where:
- pos = position in sequence
- i = dimension
- d_model = model dimension

## Alternatives
While Transformer used sinusoidal encoding, later models (including [[BERT]], [[GPT-3]]) often use:
- **Learned positional embeddings**: Trainable position vectors
- Trade-off: More flexible but fixed maximum sequence length

## Importance
Critical for:
- Maintaining sequence order information
- Enabling position-aware [[self-attention]]
- Allowing [[Transformer]] to process sequential data

## Related Concepts
- [[Transformer]]
- [[attention mechanism]]
- [[self-attention]]
- [[BERT]]
- [[GPT-3]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
