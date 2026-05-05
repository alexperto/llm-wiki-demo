# Pre-training and Fine-tuning

## Summary
A two-stage training paradigm where a model is first pre-trained on a large corpus using self-supervised objectives, then fine-tuned on specific downstream tasks.

## Explanation
Pre-training and fine-tuning has become a dominant approach in NLP, enabling models to learn general language representations before specializing for specific tasks.

### Pre-training Stage
- Train on large unlabeled corpora
- Use self-supervised objectives (e.g., [[masked language model]], next token prediction)
- Learn general representations and patterns
- Examples: [[BERT]] pre-training, GPT pre-training

### Fine-tuning Stage
- Adapt pre-trained model to specific tasks
- Use (typically smaller) labeled datasets
- Add task-specific layers if needed
- Update model parameters with supervised learning

## Approaches Across Papers

### BERT Approach
[[BERT]] uses:
- Pre-training: [[Masked language model]] + [[Next sentence prediction]]
- Fine-tuning: Add one output layer and train on downstream task
- Described as "fine-tuning based approach"

### GPT-3 Alternative
[[GPT-3]] challenges this paradigm:
- Uses [[few-shot learning]] instead of fine-tuning
- Tasks specified via text prompts, no parameter updates
- Shows that scale enables task-agnostic [[in-context learning]]

### InstructGPT Hybrid
[[InstructGPT]] combines both:
- Starts with pre-trained [[GPT-3]]
- Uses supervised fine-tuning on demonstrations
- Further fine-tunes with [[RLHF]]

## Contradictions/Tensions
- **BERT vs GPT-3**: BERT advocates fine-tuning for best performance; GPT-3 shows competitive performance without any fine-tuning through scale
- **Alignment Tax**: [[InstructGPT]] shows that fine-tuning for [[alignment]] can cause performance regressions on standard benchmarks

## Related Concepts
- [[BERT]]
- [[GPT-3]]
- [[InstructGPT]]
- [[few-shot learning]]
- [[transfer learning]]
- [[masked language model]]
- [[RLHF]]

## References
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
- "Training language models to follow instructions with human feedback" (Ouyang et al., 2022)
