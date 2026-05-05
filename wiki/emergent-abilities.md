# Emergent Abilities

## Summary
Capabilities that arise in language models at sufficient scale that are not present in smaller models, often appearing qualitatively rather than as smooth improvements.

## Explanation
Emergent abilities are behaviors that appear when models reach certain scale thresholds. These abilities are not explicitly programmed but emerge from the combination of scale, architecture, and training.

### Examples from GPT-3
[[GPT-3]] demonstrated several emergent abilities:
- Strong [[few-shot learning]] without any fine-tuning
- [[In-context learning]] from demonstrations
- Arithmetic reasoning (3-digit arithmetic)
- Word unscrambling
- Novel word usage
- On-the-fly domain adaptation

### Scale Dependence
- Abilities often appear suddenly at certain model sizes
- Not simply smooth improvements with scale
- Larger models show qualitatively different behaviors
- Smaller models may not show the ability at all

### Foundation Models Perspective
The [[foundation models]] report notes:
- Scale results in new emergent capabilities
- We lack clear understanding of what models are capable of
- Emergent properties make behavior prediction difficult
- Critical need to study and understand these phenomena

## Implications

### Positive
- Enables new applications without explicit training
- Single model can perform diverse tasks
- Capabilities may continue emerging with further scale

### Concerns
- Hard to predict what abilities will emerge
- May include undesirable behaviors
- Difficult to ensure safety when capabilities are unpredictable
- Testing becomes challenging

## Related to Scale
The papers show consistent theme:
- [[GPT-3]]: Larger models → better few-shot learning (emergent capability)
- [[Foundation models]]: Scale creates emergence and new challenges
- [[InstructGPT]]: Even small aligned models can outperform large base models (emergence from alignment, not just scale)

## Related Concepts
- [[GPT-3]]
- [[foundation models]]
- [[few-shot learning]]
- [[in-context learning]]
- [[language modeling]]

## References
- "Language Models are Few-Shot Learners" (Brown et al., 2020)
- "On the Opportunities and Risks of Foundation Models" (Bommasani et al., 2021)
