# Residual Connections

## Summary
Residual connections (also called skip connections) add the input of a sublayer directly to its output, enabling training of very deep networks by facilitating gradient flow and information propagation.

## Explanation
A residual connection creates a direct path for information to flow through the network by adding (summing) the input to a layer with its output, rather than just passing the transformed output forward.

### Basic Formula
Instead of: output = F(x)

Use: output = x + F(x)

Where:
- x: input to the sublayer
- F(x): transformation applied by the sublayer
- output: sum of input and transformation

### In Transformer Architecture

Each [[Transformer]] block contains **two residual connections**:

1. **Around multi-head attention**:
   - output = x + MultiHeadAttention(x)

2. **Around feed-forward network**:
   - output = x + FeedForward(x)

Combined with [[layer normalization]], the typical pattern is:
- **Post-norm**: x = LayerNorm(x + Sublayer(x))
- **Pre-norm**: x = x + Sublayer(LayerNorm(x))

### Why Residual Connections?

**Gradient Flow:**
- During backpropagation, gradients can flow directly through the skip connection
- Prevents vanishing gradients in deep networks
- Enables training of very deep models (12-24+ layers in [[BERT]], [[GPT-3]])

**Information Preservation:**
- Original information is always preserved
- Network only needs to learn the "residual" (difference/refinement)
- Makes it easier to learn identity mappings when needed

**Residual Stream Perspective:**
- Can view the network as maintaining a "residual stream" of information
- Each layer reads from and writes to this stream
- [[Attention mechanism]] and [[feed-forward networks]] add information to the stream

### Historical Context

Residual connections were introduced in ResNet (He et al., 2016) for computer vision and proved crucial for training very deep CNNs. The [[Transformer]] architecture adopted this technique for the same benefits.

## Usage Across All Transformer Models

- **[[Transformer]]** (2017): Two residual connections per layer
- **[[BERT]]** (2018): Residual connections in all 12/24 layers
- **[[GPT-3]]** (2020): Residual connections throughout 96 layers
- **All modern LLMs**: Essential architectural component

## Residual Stream Interpretation

Modern interpretability research views transformers as:
- Maintaining a **residual stream** for each token
- Attention and FFN layers **add** to this stream
- Each position's stream flows upward through the network
- [[Multi-head attention]] can move information between streams

## Related Concepts
- [[Transformer]]
- [[layer normalization]]
- [[multi-head attention]]
- [[feed-forward networks]]
- [[BERT]]
- [[GPT-3]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
- He et al., "Deep Residual Learning for Image Recognition" (2016)
- Transformer interpretability research
