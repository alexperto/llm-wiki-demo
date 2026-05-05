# BERT

## Summary
BERT (Bidirectional Encoder Representations from Transformers) is a language representation model designed to pre-train deep bidirectional representations from unlabeled text by conditioning on both left and right context.

## Explanation
BERT revolutionized NLP by introducing bidirectional [[pre-training]] for language representations. Unlike previous models that used unidirectional language models, BERT uses two novel pre-training objectives:

### Pre-training Tasks
1. **[[masked-language-model]] (MLM)**: Randomly masks tokens and predicts them based on surrounding context
2. **[[next-sentence-prediction]] (NSP)**: Predicts whether two sentences are consecutive

### Key Innovations
- **Bidirectional Context**: Can incorporate context from both left and right, unlike autoregressive models
- **[[transfer-learning]]**: Pre-trained model can be fine-tuned with just one additional output layer
- **Task-Agnostic Architecture**: Same architecture works for many downstream tasks

### Architecture
- Based on [[Transformer]] encoder (12 or 24 layers)
- Uses WordPiece tokenization
- Position embeddings for sequence order

## Performance
Achieved state-of-the-art on 11 NLP tasks including:
- GLUE score: 80.5%
- SQuAD v1.1 F1: 93.2
- MultiNLI accuracy: 86.7%

## Contradiction with Other Approaches
- **vs GPT-3**: BERT uses bidirectional attention and requires [[fine-tuning]] for downstream tasks, while [[GPT-3]] uses unidirectional attention and performs [[few-shot-learning]] without fine-tuning
- **vs InstructGPT**: BERT focuses on learning representations, while [[InstructGPT]] focuses on [[alignment]] with user intent

## Related Concepts
- [[pre-training-and-fine-tuning]]
- [[masked-language-model]]
- [[next-sentence-prediction]]
- [[Transformer]]
- [[bidirectional-vs-unidirectional-models]]
- [[transfer-learning]]

## References
- Paper: "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
- ArXiv: 1810.04805v2
