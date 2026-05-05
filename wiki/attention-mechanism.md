# Attention Mechanism

## Summary
An attention mechanism allows a model to focus on different parts of the input when producing each part of the output, enabling modeling of dependencies without regard to their distance in sequences.

## Explanation
Attention mechanisms have become integral to sequence modeling and transduction models. The [[Transformer]] paper introduced **scaled dot-product attention** as the core building block.

### Core Intuition
Attention allows computing a representation for a token by **selectively attending to and integrating information** from surrounding tokens. We say a token "attends to" some neighboring tokens more than others, building up [[contextual embeddings]].

### Types of Attention
- **Self-Attention**: Relates different positions of a single sequence to compute a representation (see [[self-attention]])
- **Cross-Attention**: Attends from one sequence to another (used in encoder-decoder models)
- **Multi-Head Attention**: Uses multiple attention mechanisms in parallel (see [[multi-head attention]])

### Query-Key-Value Mechanism
Attention is implemented through the [[query-key-value]] (QKV) mechanism:

1. **Project inputs** into queries (Q), keys (K), and values (V)
2. **Score**: Compare query with all keys - score(q_i, k_j) = q_i · k_j
3. **Normalize**: Apply softmax to get attention weights
4. **Aggregate**: Compute weighted sum of values

See [[query-key-value]] for detailed explanation.

### Scaled Dot-Product Attention
The attention function computes a weighted sum of values based on the similarity between queries and keys. The scaling factor (1/√d_k) prevents gradients from becoming too small in high dimensions.

Formula: Attention(Q, K, V) = softmax(QK^T / √d_k)V

## Evolution Across Papers
- **Transformer (2017)**: Introduced as the sole mechanism, replacing recurrence entirely
- **BERT (2018)**: Used bidirectional self-attention for [[pre-training]]
- **GPT-3 (2020)**: Employed in autoregressive (unidirectional) manner for [[language modeling]]

## Related Concepts
- [[query-key-value]]
- [[self-attention]]
- [[multi-head attention]]
- [[Transformer]]
- [[BERT]]
- [[contextual embeddings]]
- [[encoder-decoder architecture]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
