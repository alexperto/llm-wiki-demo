# Pre-training

## Summary
Pre-training is the first stage of training where a model learns general language representations from large amounts of unlabeled text before being adapted to specific tasks through [[fine-tuning]] or [[few-shot-learning]].

## Explanation
Pre-training enables [[transfer-learning]] by creating models that capture broad linguistic knowledge, patterns, and world knowledge from massive text corpora. This learned knowledge then transfers to downstream tasks.

### Pre-training Objectives

Different models use different pre-training approaches:

**[[BERT]]:**
- **[[Masked-language-model]]** (MLM): Predict randomly masked tokens
- **[[Next-sentence-prediction]]** (NSP): Predict if sentences are consecutive
- Trained on unlabeled text (Wikipedia, BookCorpus)
- Bidirectional context

**[[GPT-3]]:**
- **Autoregressive [[language-modeling]]**: Predict next token
- Trained on massive web text (Common Crawl, WebText, Books, Wikipedia)
- Unidirectional (left-to-right) context
- 300 billion tokens of training data

**[[InstructGPT]]:**
- Starts with [[GPT-3]] pre-training
- Additional supervised pre-training on demonstrations
- Then [[RLHF]] (though some consider RLHF a form of fine-tuning)

### Why Pre-training Works

**Transfer of Knowledge:**
- Learns syntax, semantics, facts, reasoning patterns
- Captures statistical patterns in language
- Builds [[contextual-embeddings]] that adapt to context

**Data Efficiency:**
- Leverages unlimited unlabeled text
- Reduces need for labeled data in downstream tasks
- Amortizes learning across many tasks

**Scale Effects:**
- [[GPT-3]] showed larger pre-training enables [[emergent-abilities]]
- More compute, data, and parameters → better transfer
- [[Foundation-models]] report emphasizes scale's importance

## Pre-training vs Fine-tuning

| Aspect | Pre-training | [[Fine-tuning]] |
|--------|--------------|----------------|
| Data | Massive unlabeled text | Task-specific labeled data |
| Objective | Self-supervised (MLM, next token) | Supervised task objective |
| Scale | Billions of tokens | Thousands-millions of examples |
| Cost | Very expensive (months on many GPUs) | Much cheaper (hours-days) |
| Purpose | Learn general representations | Specialize for specific task |

## Evolution

1. **Pre-2018**: Task-specific models trained from scratch
2. **2018 ([[BERT]])**: Transformer pre-training + fine-tuning paradigm
3. **2020 ([[GPT-3]])**: Scale pre-training to enable [[few-shot-learning]]
4. **2022 ([[InstructGPT]])**: Pre-training + fine-tuning + [[RLHF]] for [[alignment]]

## See Also
- [[pre-training-and-fine-tuning]] - Full two-stage paradigm
- [[fine-tuning]] - Second stage after pre-training
- [[masked-language-model]] - BERT's pre-training objective
- [[language-modeling]] - GPT-3's pre-training objective
- [[transfer-learning]] - Broader concept
- [[foundation-models]] - Models defined by large-scale pre-training

## References
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
- "On the Opportunities and Risks of Foundation Models" (Bommasani et al., 2021)
