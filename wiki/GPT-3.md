# GPT-3

## Summary
GPT-3 is an autoregressive language model with 175 billion parameters that demonstrates strong [[few-shot learning]] capabilities without gradient updates or fine-tuning.

## Explanation
GPT-3 (Generative Pre-trained Transformer 3) showed that scaling up language models greatly improves task-agnostic, few-shot performance. Unlike [[BERT]], GPT-3 performs tasks purely through text interaction without any task-specific fine-tuning.

### Key Capabilities
- **[[In-Context Learning]]**: Absorbs task patterns from examples provided in the prompt
- **[[Few-Shot Learning]]**: Performs well with just a few demonstrations (typically 10-100 examples)
- **[[Zero-Shot Learning]]**: Can attempt tasks with no examples, just instructions
- **[[One-Shot Learning]]**: Learns from a single example

### Architecture
- 175 billion parameters (10x larger than any previous non-sparse language model at the time)
- Based on [[Transformer]] decoder architecture
- Autoregressive (unidirectional) [[attention mechanism]]

### Scale Effects
Larger models show:
- Steeper in-context learning curves
- Better few-shot performance compared to zero-shot
- [[Emergent abilities]] that smaller models don't exhibit

## Performance
Strong results on many NLP tasks including:
- Translation
- Question answering
- Cloze tasks
- On-the-fly reasoning
- 3-digit arithmetic

## Approach Differences
- **vs [[BERT]]**: GPT-3 is unidirectional and autoregressive; BERT is bidirectional. GPT-3 uses [[few-shot learning]]; BERT requires [[fine-tuning]].
- **vs [[InstructGPT]]**: GPT-3 is the base model, while InstructGPT adds [[RLHF]] to better follow instructions and align with user intent

## Related Concepts
- [[few-shot learning]]
- [[zero-shot learning]]
- [[in-context learning]]
- [[Transformer]]
- [[emergent abilities]]
- [[foundation models]]
- [[language modeling]]

## References
- Paper: "Language Models are Few-Shot Learners" (Brown et al., 2020)
- ArXiv: 2005.14165v4
