# Foundation Models

## Summary
Foundation models are models trained on broad data at scale that can be adapted to a wide range of downstream tasks. The term emphasizes their critically central yet incomplete character.

## Explanation
The "On the Opportunities and Risks of Foundation Models" report (2021) introduced this term to describe a paradigm shift in AI where models like [[BERT]], [[GPT-3]], and DALL-E are trained using self-supervision at scale and then adapted to many tasks.

### Key Characteristics
1. **Emergence**: Scale results in new [[emergent abilities]] and capabilities
2. **Homogenization**: Effectiveness across many tasks incentivizes using the same base model
3. **Transfer**: Based on [[transfer learning]] principles but at unprecedented scale

### Capabilities
Foundation models span multiple domains:
- Language (e.g., [[BERT]], [[GPT-3]], [[InstructGPT]])
- Vision
- Robotics
- Reasoning and search
- Human interaction

### Critical Concerns
- **Inherited Defects**: Homogenization means defects in the foundation model propagate to all adapted models downstream
- **Unclear Understanding**: Lack of clear understanding of how they work, when they fail, and their full capabilities
- **Emergent Properties**: Unexpected behaviors arise from scale

### Societal Impact
The report emphasizes foundation models are fundamentally sociotechnical, requiring consideration of:
- Inequity and fairness
- Potential for misuse
- Economic and environmental impact
- Legal and ethical considerations

## Relationship to Other Concepts
- **Examples**: [[BERT]], [[GPT-3]], [[InstructGPT]] are all foundation models
- **Training**: Relies on [[pre-training]] at massive scale
- **Adaptation**: Uses [[fine-tuning]], [[few-shot learning]], or [[RLHF]]
- **Properties**: Exhibits [[emergent abilities]]

## Related Concepts
- [[pre-training and fine-tuning]]
- [[transfer learning]]
- [[emergent abilities]]
- [[BERT]]
- [[GPT-3]]
- [[InstructGPT]]
- [[few-shot learning]]

## References
- Paper: "On the Opportunities and Risks of Foundation Models" (Bommasani et al., 2021)
- ArXiv: 2108.07258v3
