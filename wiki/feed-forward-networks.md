# Feed-Forward Networks

## Summary
Position-wise fully connected layers used in each [[Transformer]] layer, applied identically to each position separately.

## Explanation
In the [[Transformer]] architecture, each encoder and decoder layer contains a feed-forward network (FFN) in addition to the attention mechanism.

### Structure
The FFN consists of:
1. Linear transformation
2. Non-linear activation (ReLU in original Transformer)
3. Another linear transformation

### Formula
FFN(x) = max(0, xW₁ + b₁)W₂ + b₂

### Key Properties
- **Position-wise**: Applied to each position separately and identically
- **Same parameters**: Same FFN used at every position (but different across layers)
- **Dimensionality**: Input and output are d_model; inner layer often larger (e.g., 2048 vs 512)

## Role in Transformer
Each [[Transformer]] layer has:
1. [[Multi-head attention]] sublayer
2. Feed-forward network sublayer
3. Residual connections around both
4. Layer normalization

### Purpose
- Add non-linearity and transformation after attention
- Increase model capacity
- Each position processed independently (unlike attention which mixes positions)

## Usage Across Models
- **[[Transformer]]**: Core component with ReLU activation
- **[[BERT]]**: Same structure in every encoder layer
- **[[GPT-3]]**: Used in every decoder layer

## Related Concepts
- [[Transformer]]
- [[multi-head attention]]
- [[encoder-decoder architecture]]
- [[BERT]]
- [[GPT-3]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
