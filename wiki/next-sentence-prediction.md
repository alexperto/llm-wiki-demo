# Next Sentence Prediction

## Summary
A [[pre-training]] objective used in [[BERT]] where the model learns to predict whether two sentences are consecutive in the original text.

## Explanation
Next Sentence Prediction (NSP) is one of two pre-training tasks in BERT, designed to help the model understand relationships between sentences.

### How It Works
1. Given two sentences A and B
2. 50% of time: B actually follows A (labeled IsNext)
3. 50% of time: B is random sentence (labeled NotNext)
4. Model predicts the relationship

### Purpose
Enables BERT to:
- Learn sentence-pair relationships
- Better performance on tasks requiring sentence understanding (e.g., question answering, natural language inference)
- Jointly pre-train text-pair representations

## Training Details
- Combined with [[masked-language-model]] during pre-training
- Both objectives trained simultaneously
- Contributes to [[BERT]]'s bidirectional understanding

## Relationship to BERT
Part of [[BERT]]'s two-task pre-training:
1. **[[masked-language-model]]** (MLM): Token-level understanding
2. **Next Sentence Prediction** (NSP): Sentence-level understanding

Together they enable:
- Token-level tasks (NER, QA)
- Sentence-level tasks (NLI, paraphrasing)

## Later Developments
Subsequent research (not in these papers) has questioned NSP's necessity, with some models achieving good results without it.

## Related Concepts
- [[BERT]]
- [[masked-language-model]]
- [[pre-training-and-fine-tuning]]
- [[transfer-learning]]

## References
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
