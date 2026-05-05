# Encoder-Decoder Architecture

## Summary
A neural network architecture consisting of two components: an encoder that processes the input sequence into representations, and a decoder that generates the output sequence from those representations.

## Explanation
The encoder-decoder structure has been a dominant architecture for sequence transduction tasks like machine translation.

### Components

#### Encoder
- Processes input sequence (x₁, ..., xₙ)
- Produces continuous representations z = (z₁, ..., zₙ)
- In [[Transformer]]: Stack of 6 identical layers with [[multi-head-attention]] and [[feed-forward-networks]]

#### Decoder
- Takes encoder representations z
- Generates output sequence autoregressively
- In [[Transformer]]: Stack of 6 layers with additional cross-attention to encoder

### Transformer Implementation
The [[Transformer]] uses:
- **Encoder**: [[multi-head-attention]] + feed-forward network per layer
- **Decoder**: Self-attention + cross-attention + feed-forward network per layer
- **Attention Bridge**: Decoder attends to encoder output through cross-attention

## Variations Across Papers

### Full Encoder-Decoder
- **[[Transformer]]**: Original architecture with both encoder and decoder
- Use case: Machine translation, sequence-to-sequence tasks

### Encoder-Only
- **[[BERT]]**: Uses only the Transformer encoder
- Bidirectional [[self-attention]]
- Better for understanding tasks

### Decoder-Only
- **[[GPT-3]]**: Uses only decoder-style architecture
- Autoregressive, unidirectional
- Better for generation and [[few-shot-learning]]

## Evolution
1. **RNN-based** encoder-decoders with attention (pre-2017)
2. **[[Transformer]]** (2017): Full encoder-decoder with self-attention
3. **[[BERT]]** (2018): Encoder-only for bidirectional representations
4. **[[GPT-3]]** (2020): Decoder-only for few-shot learning

## Related Concepts
- [[Transformer]]
- [[BERT]]
- [[GPT-3]]
- [[attention-mechanism]]
- [[multi-head-attention]]
- [[self-attention]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
