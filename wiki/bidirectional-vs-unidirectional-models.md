# Bidirectional vs Unidirectional Models

## Summary
Bidirectional models can attend to context from both directions when processing each token, while unidirectional models can only attend to previous tokens.

## Explanation
This distinction represents a fundamental architectural choice in language models with significant implications for their capabilities and training.

### Unidirectional (Autoregressive) Models
- Process sequence left-to-right
- Each token can only attend to previous tokens
- Examples: [[GPT-3]], standard language models
- Used for: Text generation, [[language modeling]]

**Advantages:**
- Natural for generation tasks
- Enables [[few-shot learning]] and [[in-context learning]]
- Can generate coherent long-form text

**Limitations:**
- Cannot use future context
- [[BERT]] paper argues this is "sub-optimal for sentence-level tasks"

### Bidirectional Models
- Can attend to both past and future context
- Example: [[BERT]]
- Enabled by [[masked language model]] objective

**Advantages:**
- Better for understanding tasks (classification, QA)
- Can incorporate full context for each token
- [[BERT]] shows superior performance on many NLP benchmarks

**Limitations:**
- Cannot directly generate text (no natural left-to-right generation)
- Requires special training objective (MLM)

## Key Contradiction Between Papers

### BERT's Position
[[BERT]] argues:
- "Standard language models are unidirectional, and this limits the choice of architectures"
- Unidirectionality is "sub-optimal for sentence-level tasks"
- "Could be very harmful when applying fine-tuning based approaches to token-level tasks such as question answering"

### GPT-3's Position
[[GPT-3]] demonstrates:
- Unidirectional models can achieve competitive performance through scale
- [[Few-shot learning]] with autoregressive models rivals fine-tuned bidirectional models
- Single unidirectional model handles diverse tasks without architectural modifications

### Resolution
Different strengths for different use cases:
- **Bidirectional**: Better for tasks requiring full context understanding when [[fine-tuning]]
- **Unidirectional**: Better for generation and [[few-shot learning]]
- **Scale**: [[GPT-3]] shows that sufficient scale can compensate for architectural limitations

## Related Concepts
- [[BERT]]
- [[GPT-3]]
- [[masked language model]]
- [[language modeling]]
- [[self-attention]]
- [[pre-training and fine-tuning]]

## References
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
