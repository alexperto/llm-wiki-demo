# Layer Normalization

## Summary
Layer Normalization (LayerNorm) is a normalization technique applied to each token's vector representation independently, used extensively in [[Transformer]] architectures to stabilize training and improve performance.

## Explanation
Layer normalization normalizes the activations across the feature dimension for each example independently, unlike batch normalization which normalizes across the batch dimension.

### How It Works

For a vector x with dimension d:

1. **Compute mean**: μ = (1/d) Σ x_i
2. **Compute variance**: σ² = (1/d) Σ (x_i - μ)²
3. **Normalize**: x_norm = (x - μ) / √(σ² + ε)
4. **Scale and shift**: output = γ × x_norm + β

Where:
- ε: small constant for numerical stability
- γ, β: learnable parameters (scale and bias)

### In Transformer Architecture

Layer normalization is applied **twice** in each [[Transformer]] block:

1. **After attention sublayer**: Normalizes the output of [[multi-head attention]]
2. **After feed-forward sublayer**: Normalizes the output of [[feed-forward networks]]

Each normalization typically occurs:
- **Post-norm** (original Transformer): After the residual connection
  - x = LayerNorm(x + Sublayer(x))
- **Pre-norm** (modern variants): Before the sublayer
  - x = x + Sublayer(LayerNorm(x))

### Why Layer Normalization?

**Benefits:**
- **Stabilizes training**: Prevents activation values from growing too large or small
- **Enables deeper networks**: Facilitates gradient flow
- **Faster convergence**: Helps optimization
- **Independence from batch size**: Works with any batch size, unlike batch normalization

**Why not Batch Normalization?**
- Sequence lengths vary in NLP tasks
- Batch normalization would couple statistics across different sequences
- Layer norm operates on each token independently

## Usage Across Models

- **[[Transformer]]**: Two layer norms per encoder/decoder layer
- **[[BERT]]**: Layer norm after each sublayer
- **[[GPT-3]]**: Layer norm in every transformer block
- **Modern LLMs**: Universal component

## Variants

- **RMSNorm**: Simplified version without mean centering (used in some modern LLMs)
- **Pre-norm vs Post-norm**: Placement relative to residual connections

## Related Concepts
- [[Transformer]]
- [[residual connections]]
- [[multi-head attention]]
- [[feed-forward networks]]
- [[BERT]]
- [[GPT-3]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
- Ba et al., "Layer Normalization" (2016)
