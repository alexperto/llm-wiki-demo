# Transfer Learning

## Summary
A machine learning technique where knowledge gained from training on one task is applied to a different but related task, enabling better performance with less data.

## Explanation
Transfer learning is the foundational principle behind modern NLP models. Instead of training task-specific models from scratch, models learn general representations that transfer to many tasks.

### In NLP Context
Modern transfer learning typically involves:
1. **Pre-training**: Learn general representations from large unlabeled corpus
2. **Transfer**: Apply learned representations to downstream tasks
3. **Adaptation**: Fine-tune or prompt for specific tasks

## Evolution Across Papers

### BERT's Approach
[[BERT]] demonstrates transfer learning through:
- [[Pre-training]] on large corpus with [[masked language model]]
- [[Fine-tuning]] with single additional layer for downstream tasks
- Same pre-trained model works for diverse tasks

### GPT-3's Approach
[[GPT-3]] shows an extreme form:
- Pre-train massive model on diverse text
- Transfer to new tasks via [[few-shot learning]]
- No parameter updates needed (true zero-shot transfer)

### Foundation Models Framing
[[Foundation models]] report positions transfer learning as:
- Core principle of foundation models
- Scale changes the nature of transfer
- "Based on standard deep learning and transfer learning"

## Key Insight
All papers build on transfer learning but differ in transfer mechanism:
- **[[BERT]]**: Transfer via fine-tuning
- **[[GPT-3]]**: Transfer via in-context learning
- **[[InstructGPT]]**: Transfer via RLHF + few-shot

## Benefits
- Reduced need for labeled data
- Better performance through pre-training
- Shared knowledge across tasks
- More efficient than training from scratch

## Scale Effects
[[Foundation models]] and [[GPT-3]] show:
- Scale amplifies transfer learning benefits
- [[Emergent abilities]] arise from transfer at scale
- Single model can transfer to unprecedented range of tasks

## Related Concepts
- [[pre-training and fine-tuning]]
- [[few-shot learning]]
- [[BERT]]
- [[GPT-3]]
- [[foundation models]]
- [[in-context learning]]

## References
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
- "On the Opportunities and Risks of Foundation Models" (Bommasani et al., 2021)
