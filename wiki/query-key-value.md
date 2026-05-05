# Query-Key-Value (QKV)

## Summary
The Query-Key-Value mechanism is the fundamental computation pattern underlying the [[attention-mechanism]] in [[Transformer]] models, where each token is represented in three roles to compute attention weights and output values.

## Explanation
The QKV mechanism is central to understanding how [[self-attention]] works. Each input token is transformed into three different representations, each serving a specific purpose in the attention computation.

### Three Roles of Each Token

Every input element x_i is projected into three vectors:

1. **Query (Q)**: Represents what the current token is "looking for"
   - Computed as: q_i = x_i × W_Q
   - Used to compare against keys of other tokens

2. **Key (K)**: Represents what the token "offers" or "advertises"
   - Computed as: k_j = x_j × W_K
   - Used to be compared against queries from other tokens

3. **Value (V)**: The actual information to be propagated
   - Computed as: v_j = x_j × W_V
   - Weighted and summed based on attention scores

### Attention Computation Steps

1. **Compute queries, keys, and values** for all tokens
2. **Score**: Compare each query with all keys
   - score(x_i, x_j) = q_i · k_j
   - Measures relevance/similarity
3. **Normalize**: Apply softmax to get attention weights
   - a_ij = softmax(score(x_i, x_j))
4. **Aggregate**: Weighted sum of values
   - output_i = Σ a_ij × v_j

### Intuitive Analogy
Think of a library:
- **Query**: "I'm looking for books about machine learning"
- **Key**: Each book's index card describing its content
- **Value**: The actual book content
- Attention matches your query to relevant keys, then retrieves corresponding values

## Relationship to Multi-Head Attention

In [[multi-head-attention]], separate Q, K, V projections are learned for each head:
- q^c_i = x_i × W^c_Q (query for head c)
- k^c_j = x_j × W^c_K (key for head c)
- v^c_j = x_j × W^c_V (value for head c)

Each head learns different query/key/value transformations, capturing different types of relationships.

## Why Separate Q, K, V?

The separation allows:
- **Asymmetric comparisons**: What you're looking for (Q) vs. what you offer (K)
- **Learned transformations**: Different aspects emphasized in scoring vs. output
- **Flexibility**: Query-key similarity can differ from value content

## Used Across All Transformer Models

- **[[Transformer]]**: Original implementation with scaled dot-product attention
- **[[BERT]]**: Bidirectional attention using QKV
- **[[GPT-3]]**: Autoregressive attention with masked QKV
- **All modern LLMs**: Fundamental building block

## Related Concepts
- [[attention-mechanism]]
- [[self-attention]]
- [[multi-head-attention]]
- [[Transformer]]
- [[scaled dot-product attention]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
- Educational materials on Transformer architecture
