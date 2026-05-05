# Fine-tuning

## Summary
Fine-tuning is the process of taking a [[pre-training|pre-trained]] model and further training it on a specific task using a (typically smaller) labeled dataset to adapt it for that task.

## Explanation
Fine-tuning is the second stage of the [[pre-training-and-fine-tuning]] paradigm that has dominated modern NLP. After a model learns general representations during [[pre-training]], fine-tuning specializes it for specific applications.

### How It Works
1. **Start with pre-trained model**: Use weights from [[pre-training]] phase
2. **Add task-specific layers**: Often just a single output layer
3. **Train on labeled data**: Use supervised learning on task dataset
4. **Update parameters**: Fine-tune all or some model weights

### Approaches Across Models

**[[BERT]] Approach:**
- Add one task-specific output layer
- Fine-tune on downstream task (QA, classification, NER, etc.)
- Typically needs thousands of labeled examples
- Achieves state-of-the-art on many benchmarks

**[[GPT-3]] Alternative:**
- Challenges the need for fine-tuning entirely
- Uses [[few-shot-learning]] instead - no parameter updates
- Shows competitive performance without fine-tuning
- Demonstrates that sufficient scale can reduce need for fine-tuning

**[[InstructGPT]] Approach:**
- Combines supervised fine-tuning with [[RLHF]]
- First: supervised fine-tuning on demonstrations
- Then: further fine-tuning with reinforcement learning
- Optimizes for [[alignment]] rather than just task performance

## Fine-tuning vs Few-shot Learning

| Aspect | Fine-tuning ([[BERT]]) | Few-shot ([[GPT-3]]) |
|--------|----------------------|---------------------|
| Parameter updates | Yes | No |
| Training data needed | Thousands of examples | 10-100 examples in prompt |
| Adaptation time | Hours of training | Immediate |
| Task switching | Requires retraining | Instant via prompts |
| Performance | Often highest | Competitive at scale |

## Benefits
- Better task performance than zero-shot
- Adapts general knowledge to specific domain
- Can achieve state-of-the-art results
- Works with moderate amounts of labeled data

## Challenges
- Requires task-specific labeled datasets
- Computational cost of training
- Separate model needed for each task
- Risk of catastrophic forgetting

## See Also
- [[pre-training-and-fine-tuning]] - Full paradigm explanation
- [[pre-training]] - First stage before fine-tuning
- [[few-shot-learning]] - Alternative to fine-tuning
- [[transfer-learning]] - Broader concept
- [[BERT]] - Model designed for fine-tuning
- [[RLHF]] - Advanced fine-tuning with human feedback

## References
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
- "Training language models to follow instructions with human feedback" (Ouyang et al., 2022)
