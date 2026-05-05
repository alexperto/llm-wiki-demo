# Zero-Shot Learning

## Summary
The ability of a model to perform a task without any task-specific training examples, using only a natural language description or instruction.

## Explanation
Zero-shot learning represents the most extreme form of [[transfer learning]], where a model attempts tasks it has never seen examples of during training or in the prompt.

### How It Works
1. Provide task description in natural language
2. Model infers the desired behavior from the description
3. No examples or demonstrations given
4. No gradient updates occur

### In GPT-3
[[GPT-3]] demonstrates zero-shot capabilities:
- Task specified purely via text description
- Performance improves steadily with model size
- Some tasks work well zero-shot, others benefit more from [[few-shot learning]]

### Terminology Note
The [[GPT-3]] paper notes the term is "potentially ambiguous":
- "Zero-shot" in that no gradient updates occur
- But often involves providing task description at inference time
- Not truly "zero information" about the task

## Performance Characteristics
From [[GPT-3]]:
- Zero-shot performance improves steadily with scale
- [[Few-shot learning]] improves more rapidly than zero-shot
- Larger models better leverage few-shot examples
- Some tasks remain challenging even at large scale

## Comparison with Other Learning Modes
- **Zero-shot**: Task description only
- **[[One-shot learning]]**: Single example
- **[[Few-shot learning]]**: Multiple examples (10-100)
- **[[Fine-tuning]]**: Thousands of examples with gradient updates

## InstructGPT Connection
[[InstructGPT]] improves zero-shot performance by:
- Training to follow natural language instructions via [[RLHF]]
- Better alignment with user intent
- More reliable zero-shot instruction following

## Related Concepts
- [[GPT-3]]
- [[few-shot learning]]
- [[one-shot learning]]
- [[in-context learning]]
- [[InstructGPT]]
- [[foundation models]]

## References
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
- "Training language models to follow instructions with human feedback" (Ouyang et al., 2022)
