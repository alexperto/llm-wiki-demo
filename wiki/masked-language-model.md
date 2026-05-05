# Masked Language Model

## Summary
A pre-training objective where some tokens are randomly masked in the input, and the model must predict the original tokens based only on their context.

## Explanation
The Masked Language Model (MLM) is a key innovation introduced in [[BERT]] that enables bidirectional pre-training. Inspired by the Cloze task (Taylor, 1953), MLM randomly masks some percentage of input tokens and trains the model to predict them.

### How It Works
1. Randomly select tokens (typically 15% of input)
2. Replace with [MASK] token (80%), random token (10%), or keep unchanged (10%)
3. Predict the original token based on surrounding context
4. Only masked tokens contribute to the loss

### Key Advantage
Unlike left-to-right [[language-modeling]], MLM enables the model to:
- Use context from both directions (bidirectional)
- Learn deeper representations
- Avoid unidirectional bias

## Comparison with Other Approaches
- **vs Autoregressive LM** (used in [[GPT-3]]): MLM is bidirectional; autoregressive is unidirectional
- **Enables [[BERT]]'s bidirectionality**: Critical for [[BERT]]'s superior performance on tasks requiring full context understanding

## Limitations
- Creates pre-training/fine-tuning mismatch: [MASK] token appears in pre-training but not in fine-tuning
- Assumes independence of predicted tokens (doesn't model joint probability)

## Related Concepts
- [[BERT]]
- [[pre-training-and-fine-tuning]]
- [[language-modeling]]
- [[bidirectional-vs-unidirectional-models]]
- [[next-sentence-prediction]]

## References
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
- Taylor, W. L. (1953). Cloze procedure: A new tool for measuring readability
