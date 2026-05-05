# Alignment

## Summary
Alignment refers to ensuring AI models behave in accordance with human values and intentions, producing outputs that are helpful, honest, and harmless.

## Explanation
The alignment problem arises because language models trained on next-token prediction don't inherently optimize for following user intent. They may generate outputs that are untruthful, toxic, biased, or unhelpful despite being fluent and coherent.

### The Alignment Problem
Language models face a mismatch between:
- **Training objective**: Predict next token from internet text
- **Desired objective**: Follow user instructions helpfully and safely

### Alignment Techniques

#### InstructGPT Approach
[[InstructGPT]] demonstrates alignment through:
- [[RLHF]] to incorporate human preferences
- Supervised fine-tuning on high-quality demonstrations
- Training reward models from human feedback

#### Alignment Tax
[[InstructGPT]] introduces the concept of "alignment tax":
- Optimizing for alignment may reduce performance on standard benchmarks
- Trade-off between benchmark scores and actual usefulness
- Reflects that benchmarks don't fully capture desired behavior

### Broader Considerations
The [[foundation models]] report emphasizes:
- Alignment is fundamentally sociotechnical, not just technical
- Must consider inequity, misuse, and ethical implications
- Homogenization means alignment failures propagate widely

## Multi-faceted Nature
Alignment encompasses:
- **Helpfulness**: Following instructions accurately
- **Honesty**: Truthful outputs, acknowledging uncertainty
- **Harmlessness**: Avoiding toxic, biased, or dangerous outputs

## Current State
Papers acknowledge:
- Alignment remains an open challenge
- Current techniques show promise but are incomplete
- Need for interdisciplinary approaches

## Related Concepts
- [[InstructGPT]]
- [[RLHF]]
- [[foundation models]]
- [[GPT-3]]
- [[fine-tuning]]

## References
- "Training language models to follow instructions with human feedback" (Ouyang et al., 2022)
- "On the Opportunities and Risks of Foundation Models" (Bommasani et al., 2021)
- Leike et al., 2018 (scalable agent alignment)
