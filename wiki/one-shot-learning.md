# One-Shot Learning

## Summary
The ability of a model to perform a task given exactly one demonstration example in the input context, without any parameter updates.

## Explanation
One-shot learning sits between [[zero-shot-learning]] (no examples) and [[few-shot-learning]] (multiple examples) in the spectrum of [[in-context-learning]] capabilities.

### How It Works
1. Provide single example of desired task behavior
2. Model learns the pattern from this one instance
3. Applies pattern to new inputs
4. No gradient updates occur

### Position in Learning Spectrum
- **[[zero-shot-learning]]**: No examples, just description
- **One-shot**: Single example ←
- **[[few-shot-learning]]**: Multiple examples (10-100)
- **Fine-tuning**: Thousands of examples with training

## Performance in GPT-3
[[GPT-3]] evaluates one-shot learning as middle ground:
- Better than zero-shot for most tasks
- Not as good as few-shot
- Useful when context length limits examples
- Some tasks benefit significantly from even one example

### Use Cases
One-shot particularly valuable when:
- Limited context window space
- Quick task specification needed
- Format needs to be demonstrated
- Zero-shot fails but few examples not available

## Scale Dependency
Like other [[in-context-learning]] modes:
- Performance improves with model size
- Larger models better utilize single example
- Part of broader emergent capability from scale

## Related Concepts
- [[few-shot-learning]]
- [[zero-shot-learning]]
- [[in-context-learning]]
- [[GPT-3]]
- [[emergent-abilities]]

## References
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
