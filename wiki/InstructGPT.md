# InstructGPT

## Summary
InstructGPT is a version of [[GPT-3]] fine-tuned with [[reinforcement learning from human feedback]] (RLHF) to better follow user instructions and align with human intent.

## Explanation
InstructGPT addresses a key limitation of large language models: they don't inherently follow user intent well, often generating outputs that are untruthful, toxic, or unhelpful. The model demonstrates that [[fine-tuning]] with human feedback can align language models with user intentions.

### Training Process
Three-stage procedure:
1. **Supervised Fine-Tuning (SFT)**: Collect labeler demonstrations and fine-tune [[GPT-3]]
2. **Reward Model (RM) Training**: Collect rankings of model outputs to train a reward model
3. **[[RLHF]]**: Further fine-tune using Proximal Policy Optimization (PPO) with the reward model

### Key Results
- 1.3B parameter InstructGPT preferred over 175B [[GPT-3]] (100x fewer parameters)
- Improvements in truthfulness
- Reductions in toxic output
- Better instruction following

### Alignment Tax
The paper notes an "alignment tax" - some performance regressions on public NLP datasets occur because the [[alignment]] procedure optimizes for following instructions rather than benchmark performance.

## Contradiction/Difference with Other Models
- **vs [[GPT-3]]**: InstructGPT is explicitly optimized for [[alignment]] with human intent, while GPT-3 is optimized only for next-token prediction
- **vs [[BERT]]**: Different training paradigm - InstructGPT uses [[RLHF]] on top of autoregressive pre-training, while BERT uses [[masked language model]] pre-training followed by supervised fine-tuning

## Related Concepts
- [[RLHF]]
- [[alignment]]
- [[GPT-3]]
- [[fine-tuning]]
- [[foundation models]]
- [[pre-training and fine-tuning]]

## References
- Paper: "Training language models to follow instructions with human feedback" (Ouyang et al., 2022)
- ArXiv: 2203.02155v1
