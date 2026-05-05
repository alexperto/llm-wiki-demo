# LLM Wiki Index

This wiki contains key concepts extracted from foundational papers in large language model research.

## Source Papers
1. "Attention Is All You Need" (Vaswani et al., 2017) - ArXiv: 1706.03762v7
2. "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018) - ArXiv: 1810.04805v2
3. "Language Models are Few-Shot Learners" (Brown et al., 2020) - ArXiv: 2005.14165v4
4. "On the Opportunities and Risks of Foundation Models" (Bommasani et al., 2021) - ArXiv: 2108.07258v3
5. "Training language models to follow instructions with human feedback" (Ouyang et al., 2022) - ArXiv: 2203.02155v1

## Core Concepts

### Architectures & Components
- [[alignment]] - Ensuring AI models behave in accordance with human values and intentions
- [[attention-mechanism]] - Mechanism allowing models to focus on different parts of input when producing output
- [[encoder-decoder-architecture]] - Architecture with encoder processing input and decoder generating output
- [[feed-forward-networks]] - Position-wise fully connected layers in each Transformer layer
- [[multi-head-attention]] - Attention mechanism using multiple attention functions in parallel
- [[positional-encoding]] - Mechanism to inject token position information into Transformer models
- [[self-attention]] - Attention mechanism relating different positions within a single sequence
- [[Transformer]] - Neural network architecture based entirely on attention mechanisms

### Models
- [[BERT]] - Bidirectional encoder model using masked language modeling for pre-training
- [[foundation-models]] - Models trained on broad data at scale adaptable to many downstream tasks
- [[GPT-3]] - 175B parameter autoregressive model demonstrating strong few-shot learning
- [[InstructGPT]] - GPT-3 fine-tuned with RLHF to better follow user instructions

### Training Paradigms & Objectives
- [[language-modeling]] - Task of predicting next token given previous tokens
- [[masked-language-model]] - Pre-training objective where masked tokens are predicted from context
- [[next-sentence-prediction]] - BERT pre-training task predicting if sentences are consecutive
- [[pre-training-and-fine-tuning]] - Two-stage training with general pre-training then task-specific fine-tuning
- [[RLHF]] - Reinforcement Learning from Human Feedback for aligning models with human preferences
- [[transfer-learning]] - Applying knowledge from one task to different but related tasks

### Learning Modes & Capabilities
- [[emergent-abilities]] - Capabilities arising at scale not present in smaller models
- [[few-shot-learning]] - Performing tasks with only a few demonstrations without parameter updates
- [[in-context-learning]] - Learning from examples in the input context without parameter updates
- [[one-shot-learning]] - Performing tasks given exactly one demonstration example
- [[zero-shot-learning]] - Performing tasks without examples, using only task descriptions

### Architectural Choices
- [[bidirectional-vs-unidirectional-models]] - Comparison of models using context from both vs. one direction

## Key Contradictions & Tensions

### Bidirectional vs Unidirectional
- BERT argues unidirectional models are "sub-optimal" for many tasks
- GPT-3 shows unidirectional models achieve competitive performance through scale

### Fine-tuning vs Few-shot Learning
- BERT requires fine-tuning with substantial task-specific datasets
- GPT-3 demonstrates competitive performance with just few-shot examples

### Language Modeling vs Alignment
- Pure language modeling doesn't align with following user instructions
- InstructGPT shows RLHF necessary for better alignment, even with "alignment tax"

### Emergence vs Understanding
- Models exhibit emergent abilities at scale
- Foundation Models report notes we lack understanding of how they work and what they're capable of

## Navigation
All pages contain cross-references using [[double-bracket]] notation. Follow links to explore related concepts.
