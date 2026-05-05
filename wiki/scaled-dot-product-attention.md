# Scaled Dot-Product Attention

## Summary
Scaled dot-product attention is the specific [[attention-mechanism]] formula used in the [[transformer]], which computes attention by taking the dot product of queries and keys, scaling by the square root of the dimension, and applying softmax.

## Explanation
This is the concrete implementation of attention introduced in "Attention Is All You Need". The scaling factor is crucial for maintaining stable gradients.

### Formula

**Attention(Q, K, V) = softmax(QK^T / √d_k) V**

Where:
- Q: Query matrix
- K: Key matrix
- V: Value matrix
- d_k: Dimension of the key vectors
- √d_k: Scaling factor

### Step-by-Step Computation

1. **Compute scores**: QK^T (matrix multiplication of queries and keys)
   - Each element is dot product of a query with a key
   - Measures similarity/relevance

2. **Scale**: Divide by √d_k
   - Prevents dot products from growing too large in high dimensions
   - Maintains reasonable gradient magnitudes

3. **Normalize**: Apply softmax
   - Converts scores to probability distribution
   - Ensures attention weights sum to 1

4. **Aggregate**: Multiply by V
   - Weighted sum of value vectors
   - Produces output representation

### Why Scaling is Important

**Without scaling** (d_k large):
- Dot products grow very large in magnitude
- Softmax pushed into regions with small gradients
- Gradients vanish, training becomes difficult

**With scaling** (divide by √d_k):
- Keeps dot products in reasonable range
- Softmax operates in region with better gradients
- Stable training even for large dimensions

### Implementation Details

**Used in:**
- Every [[multi-head-attention]] computation
- Both [[self-attention]] and cross-attention
- All [[transformer]]-based models ([[BERT]], [[GPT-3]], [[InstructGPT]])

**Dimensions:**
- [[Transformer]] original: d_k = 64 (within each head)
- [[BERT]]-base: d_k = 64 (per head out of 12 heads)
- [[GPT-3]]: d_k = 128 (per head out of 96 heads)

### Relation to Query-Key-Value

Scaled dot-product attention is the mathematical operation that uses the [[query-key-value]] mechanism:
- Queries and keys determine **where** to attend (via dot product)
- Scaling ensures **numerical stability**
- Values provide the **content** to aggregate

## Alternative Attention Mechanisms

While scaled dot-product is standard, alternatives exist:
- **Additive attention**: Uses feed-forward network instead of dot product
- **Multiplicative attention**: Dot product without scaling (problematic)
- **Linear attention**: Approximations for efficiency

The [[transformer]] paper compared these and showed scaled dot-product performs best.

## Related Concepts
- [[attention-mechanism]] - General concept
- [[query-key-value]] - The QKV mechanism
- [[multi-head-attention]] - Uses scaled dot-product in parallel
- [[self-attention]] - Applies scaled dot-product within sequence
- [[transformer]] - Architecture using this mechanism
- [[BERT]] - Model using scaled dot-product attention
- [[GPT-3]] - Model using scaled dot-product attention

## References
- "Attention Is All You Need" (Vaswani et al., 2017) - Section 3.2.1
