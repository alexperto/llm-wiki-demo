# Language Modeling

## Summary
The task of predicting the next token in a sequence given the previous tokens, serving as both a training objective and a fundamental capability of language models.

## Explanation
Language modeling has evolved from a specific NLP task to the primary pre-training objective for modern [[foundation models]].

### Autoregressive Language Modeling
Standard approach used in [[GPT-3]]:
- Predict next token given all previous tokens
- Unidirectional (left-to-right)
- Enables text generation
- Training objective: maximize P(token_t | token_1, ..., token_{t-1})

### Limitations
Papers identify key limitation:
- **Unidirectionality**: Cannot use future context (addressed by [[BERT]])
- **Alignment Gap**: Predicting likely next tokens ≠ following user intent (addressed by [[InstructGPT]])

## Alternatives and Extensions

### Masked Language Modeling
[[BERT]]'s approach (see [[masked language model]]):
- Bidirectional context
- Better for understanding tasks
- Not directly generative

### Language Modeling + RLHF
[[InstructGPT]]'s approach:
- Start with language model pre-training
- Add [[RLHF]] to align with human intent
- Addresses gap between likelihood and helpfulness

## Evolution Across Papers
1. **[[Transformer]]** (2017): Enables better language modeling through [[attention mechanism]]
2. **[[BERT]]** (2018): Challenges pure language modeling with [[masked language model]]
3. **[[GPT-3]]** (2020): Shows language modeling at scale enables [[few-shot learning]]
4. **[[InstructGPT]]** (2022): Shows language modeling alone insufficient for [[alignment]]

## Contradictions
- **[[BERT]] vs Language Modeling**: BERT argues unidirectional language models are "sub-optimal" and proposes MLM instead
- **[[InstructGPT]] vs Pure LM**: Shows language modeling objective is "different from the objective 'follow the user's instructions helpfully and safely'"

## Related Concepts
- [[GPT-3]]
- [[masked language model]]
- [[InstructGPT]]
- [[pre-training and fine-tuning]]
- [[bidirectional vs unidirectional models]]
- [[BERT]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
- "Training language models to follow instructions with human feedback" (Ouyang et al., 2022)
