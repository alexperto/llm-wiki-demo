# RLHF

## Summary
Reinforcement Learning from Human Feedback (RLHF) is a technique that uses human preferences to fine-tune language models, making them better aligned with human intent.

## Explanation
RLHF addresses the limitation that language models optimized solely for next-token prediction don't necessarily follow user instructions well or produce helpful, safe outputs. The technique was prominently used in [[InstructGPT]].

### Three-Stage Process

#### 1. Supervised Fine-Tuning (SFT)
- Collect labeler demonstrations of desired behavior
- [[Fine-tuning]] base model ([[GPT-3]]) on these demonstrations
- Creates initial instruction-following model

#### 2. Reward Model Training
- Collect rankings of model outputs from human labelers
- Train a reward model to predict human preferences
- Model learns to score outputs based on human judgment

#### 3. RL Fine-tuning
- Use Proximal Policy Optimization (PPO)
- Optimize model to maximize reward model scores
- May include pre-training mix to prevent performance degradation

### Key Innovation
Aligns model objectives with actual human preferences rather than just likelihood of training data.

## Results from InstructGPT
- Models preferred by humans over much larger base models
- Improvements in truthfulness and safety
- Better instruction following
- Some "alignment tax" on standard benchmarks

## Relationship to Other Concepts
- **Builds on [[pre-training-and-fine-tuning]]**: RLHF is an additional fine-tuning stage
- **Enables [[alignment]]**: Core technique for aligning models with human values
- **Used in [[InstructGPT]]**: Primary training method
- **Applied to [[foundation-models]]**: Can be applied to various base models

## Broader Context
The [[foundation-models]] report discusses RLHF as one approach to addressing safety and alignment concerns with large models.

## Related Concepts
- [[InstructGPT]]
- [[alignment]]
- [[fine-tuning]]
- [[GPT-3]]
- [[foundation-models]]

## References
- "Training language models to follow instructions with human feedback" (Ouyang et al., 2022)
- Christiano et al., 2017 (original RLHF paper)
- Stiennon et al., 2020 (summarization with human feedback)
