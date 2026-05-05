# Tokenization

## Summary
Tokenization is the process of breaking text into smaller units (tokens) that serve as the basic elements for language model processing, with subword methods like BPE being standard for modern LLMs.

## Explanation
Before a language model can process text, it must be converted into a sequence of tokens. Tokenization determines the vocabulary and granularity at which the model operates.

### Types of Tokenization

**Character-level:**
- Split into individual characters
- Very small vocabulary
- Long sequences
- Rarely used for LLMs

**Word-level:**
- Split on spaces/punctuation
- Large vocabulary (hundreds of thousands)
- Cannot handle unknown words
- Not used in modern Transformers

**Subword-level (Modern Approach):**
- Split into meaningful chunks smaller than words
- Balanced vocabulary size (30k-50k tokens)
- Handles rare/unknown words
- Used by [[BERT]], [[GPT-3]], [[InstructGPT]]

### Byte Pair Encoding (BPE)

BPE is the most common subword tokenization method:

**How it works:**
1. Start with character-level vocabulary
2. Iteratively merge most frequent adjacent pairs
3. Stop at desired vocabulary size
4. Use learned merges to tokenize new text

**Example:**
- "tokenization" might become: ["token", "ization"]
- "untokenized" might become: ["un", "token", "ized"]

**Benefits:**
- Handles rare words by breaking into subwords
- Common words remain single tokens
- Unknown words decomposed into known pieces
- Efficient vocabulary size

### Tokenization in Practice

**Process:**
1. **Tokenize**: "Thanks for all the" → ["Thanks", "for", "all", "the"]
2. **Convert to IDs**: Look up vocab indices → [5, 4000, 10532, 2224]
3. **Embed**: Map IDs to embedding vectors
4. **Add position**: Combine with [[positional encoding]]

### Model-Specific Approaches

**[[BERT]]:**
- Uses WordPiece tokenization (similar to BPE)
- Vocabulary ~30,000 tokens
- Special tokens: [CLS], [SEP], [MASK]

**[[GPT-3]]:**
- Uses Byte-Pair Encoding (BPE)
- Vocabulary ~50,000 tokens
- Consistent with GPT-2

**Modern Trends:**
- SentencePiece: language-agnostic tokenization
- Larger vocabularies for better multilingual support
- Byte-level BPE for handling any text

### Impact on Model Behavior

**Vocabulary size affects:**
- **Sequence length**: Fewer tokens = longer sequences to represent text
- **Performance**: Better tokenization → better understanding
- **Multilinguality**: Subwords help with morphologically rich languages
- **Rare words**: Subword splitting handles out-of-vocabulary words

**Token boundaries affect:**
- What patterns the model learns
- How it handles word parts (prefixes, suffixes)
- Sensitivity to spelling variations

## Relationship to Other Concepts

- **Feeds into [[Transformer]]**: Tokens are basic input units
- **Affects [[in-context learning]]**: Token limit determines context window
- **Impacts [[few-shot learning]]**: More examples need more tokens
- **Embedding**: Each token ID maps to learned vector

## Common Issues

**Token limits:**
- [[GPT-3]]: 2048 tokens context window
- [[BERT]]: 512 tokens max sequence length
- Truncation or chunking needed for longer text

**Tokenization artifacts:**
- Model behavior can depend on how text is tokenized
- Leading spaces, capitalization affect tokenization
- Important for prompt engineering

## Related Concepts
- [[Transformer]]
- [[BERT]]
- [[GPT-3]]
- [[positional encoding]]
- [[in-context learning]]
- [[contextual embeddings]]

## References
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018) - mentions WordPiece
- Sennrich et al., "Neural Machine Translation of Rare Words with Subword Units" (2016) - BPE for NMT
- Educational materials on Transformer architecture
