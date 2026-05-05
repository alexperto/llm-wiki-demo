# Few-Shot Learning

## Summary
The ability of a model to perform a task given only a few demonstrations (typically 10-100 examples) in the input context, without any gradient updates or parameter changes.

## Explanation
Few-shot learning is a key capability demonstrated by large [[foundation-models]], particularly [[GPT-3]]. The model learns to perform tasks purely from examples provided in the prompt during inference.

### How It Works
1. Provide a few examples of the desired task in the prompt
2. Model identifies the pattern through [[in-context-learning]]
3. Applies the pattern to new inputs
4. No parameter updates occur

### Scale Dependency
[[GPT-3]] showed that few-shot learning performance:
- Improves dramatically with model size
- Larger models have steeper "in-context learning curves"
- Can sometimes match or exceed fine-tuned models

## Spectrum of Learning
- **[[zero-shot-learning]]**: No examples, just task description
- **[[one-shot-learning]]**: Single example
- **Few-shot learning**: Multiple examples (10-100)
- **[[Fine-tuning]]**: Thousands of examples with gradient updates

## Advantages
- No need for large labeled datasets
- No gradient updates required
- Single model can perform many tasks
- Rapid task switching

## Contradictions with Other Approaches
- **vs [[BERT]]**: BERT requires [[fine-tuning]] with substantial task-specific datasets; GPT-3 performs competitively with just few-shot examples
- **vs Traditional ML**: Traditional approaches typically need many more examples to achieve similar performance

## Related Concepts
- [[GPT-3]]
- [[in-context-learning]]
- [[zero-shot-learning]]
- [[one-shot-learning]]
- [[foundation-models]]
- [[emergent-abilities]]
- [[pre-training-and-fine-tuning]]

## References
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
- "On the Opportunities and Risks of Foundation Models" (Bommasani et al., 2021)
