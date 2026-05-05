# In-Context Learning

## Summary
The ability of language models to learn and perform tasks by absorbing patterns from examples provided in the input context, without any parameter updates.

## Explanation
In-context learning describes how models like [[GPT-3]] can identify and execute tasks purely through the text input, using the context window as a form of task specification. This represents the "inner loop" of the learning process that occurs at inference time.

### Mechanism
1. Examples and instructions provided in the prompt
2. Model's attention mechanism identifies patterns
3. Applies learned pattern to new inputs in the same context
4. No weight updates - everything happens through forward pass

### Scale Effects
[[GPT-3]] demonstrated that in-context learning:
- Improves significantly with model scale
- Larger models show steeper learning curves
- Enables [[emergent-abilities]] at sufficient scale
- Works across diverse task types

### Terminology
The papers use related terms:
- **"In-context learning"**: General ability to learn from context
- **"[[few-shot-learning]]"**: In-context learning with multiple examples
- **"[[zero-shot-learning]]"**: In-context learning with just task description
- **"[[one-shot-learning]]"**: In-context learning with single example

## Theoretical Understanding
The [[foundation-models]] report notes:
- In-context learning involves absorbing many skills within model parameters during [[pre-training]]
- Creates a form of meta-learning capability
- Mechanism not fully understood despite widespread use

## Performance Characteristics
- Larger context windows enable more examples
- Quality of demonstrations matters significantly
- Prompt engineering crucial for best results

## Related Concepts
- [[few-shot-learning]]
- [[zero-shot-learning]]
- [[GPT-3]]
- [[foundation-models]]
- [[emergent-abilities]]
- [[Transformer]]
- [[attention-mechanism]]

## References
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
- "On the Opportunities and Risks of Foundation Models" (Bommasani et al., 2021)
