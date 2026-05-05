# Contextual Embeddings

## Summary
Contextual embeddings are representations where each word has a different vector depending on its surrounding context, as opposed to static embeddings where each word has a single fixed vector regardless of context.

## Explanation
Contextual embeddings solve a fundamental limitation of static word embeddings like Word2Vec: the inability to represent different meanings of a word in different contexts.

### The Problem with Static Embeddings

**Example**: "The chicken didn't cross the road because **it** was too tired"
- What does "it" refer to? The chicken
- Static embedding for "it" is always the same vector
- Cannot distinguish between "it = chicken" vs "it = road"

**Another Example**: "The chicken didn't cross the road because **it** was too wide"
- Here "it" refers to the road
- Same word, completely different meaning
- Static embedding cannot capture this difference

### How Contextual Embeddings Work

Each word gets a **different vector** that changes based on:
- Surrounding words in the sentence
- Position in the sequence
- Semantic relationships with neighbors

**Computed via [[attention mechanism]]:**
- Build embedding by selectively integrating information from neighboring words
- Word "attends to" relevant context words
- Different contexts → different attention patterns → different embeddings

### Implementation in Transformers

Contextual embeddings are created through [[self-attention]]:

1. **Start**: Static token embedding + position embedding
2. **Layer 1**: Attention creates first contextual representation
3. **Layer 2**: Further refines based on Layer 1's context
4. **Layer N**: Final highly contextualized representation

Each layer creates increasingly sophisticated contextual embeddings.

### Key Properties

**Context-Dependent:**
- "bank" in "river bank" ≠ "bank" in "savings bank"
- Representation captures current usage

**Bidirectional (in [[BERT]]):**
- Uses context from both left and right
- "The cat sat on the ___" - knows "cat" and "sat" exist

**Unidirectional (in [[GPT-3]]):**
- Uses only left context
- "The cat sat on the ___" - only knows "The cat sat on the"

## Evolution Across Papers

### Pre-Transformer Era (pre-2017)
- Static embeddings: Word2Vec, GloVe
- Same vector for word regardless of context

### Transformer (2017)
- [[Transformer]] architecture enables contextual embeddings through [[attention mechanism]]
- Each layer produces more contextual representations

### BERT (2018)
- **"Pre-training Deep Bidirectional **Contextual** Representations"**
- Explicitly designed for contextual embeddings
- Bidirectional context from [[masked language model]]
- Called "contextual word embeddings"

### GPT-3 (2020)
- Extremely deep contextual embeddings (96 layers)
- Unidirectional context for generation
- Context window up to 2048 tokens

### Modern Understanding (Foundation Models, 2021)
- Contextual embeddings recognized as core capability
- Scale increases richness of contextual representations
- [[In-context learning]] leverages contextual embeddings

## Comparison: Static vs Contextual

| Aspect | Static Embeddings | Contextual Embeddings |
|--------|------------------|----------------------|
| Representation | One vector per word | Different vector per occurrence |
| Context | Ignores context | Incorporates context |
| Polysemy | Cannot distinguish senses | Captures different meanings |
| Method | Lookup table | Computed by [[Transformer]] layers |
| Examples | Word2Vec, GloVe | [[BERT]], [[GPT-3]] outputs |

## Related Concepts
- [[attention mechanism]]
- [[self-attention]]
- [[Transformer]]
- [[BERT]]
- [[GPT-3]]
- [[multi-head attention]]
- [[in-context learning]]

## References
- "Attention Is All You Need" (Vaswani et al., 2017)
- "BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding" (Devlin et al., 2018)
- Educational materials on Transformer architecture
- Word2Vec (Mikolov et al., 2013) - for comparison
