# LLM Wiki Demo

An AI-curated knowledge base of foundational concepts in Large Language Models and Transformer architectures.

## Overview

This project demonstrates how LLMs can create interconnected wiki-style documentation by:
- Reading and analyzing research papers
- Extracting key concepts and relationships
- Creating cross-referenced entity pages
- Identifying and documenting contradictions between papers
- Maintaining consistency through automated auditing

**Inspiration**: Based on https://datasciencedojo.com/blog/llm-wiki-tutorial

## What's Inside

### 📚 Source Papers (6)
1. **"Attention Is All You Need"** (Vaswani et al., 2017) - The Transformer architecture
2. **"BERT"** (Devlin et al., 2018) - Bidirectional pre-training
3. **"Language Models are Few-Shot Learners"** (Brown et al., 2020) - GPT-3
4. **"On the Opportunities and Risks of Foundation Models"** (Bommasani et al., 2021)
5. **"Training language models to follow instructions with human feedback"** (Ouyang et al., 2022) - InstructGPT
6. **"Introduction to Transformers"** - Educational resource

### 📖 Wiki Contents (32 entity pages)

**Core Models:**
- Transformer, BERT, GPT-3, InstructGPT, Foundation Models

**Architecture Components:**
- Attention mechanism, Query-Key-Value, Self-attention, Multi-head attention
- Layer normalization, Residual connections, Feed-forward networks
- Positional encoding, Encoder-decoder architecture

**Training & Learning:**
- Pre-training, Fine-tuning, Masked Language Model, Language Modeling
- Transfer Learning, RLHF, Alignment

**Capabilities:**
- Few-shot learning, Zero-shot learning, One-shot learning, In-context learning
- Emergent abilities, Contextual embeddings

**Technical Concepts:**
- Tokenization (BPE), Scaled dot-product attention
- Bidirectional vs Unidirectional models

### ✨ Key Features

- **Cross-referenced**: All pages use `[[wiki-links]]` for easy navigation
- **Contradiction tracking**: Documents where papers disagree (e.g., BERT vs GPT-3 on unidirectional models)
- **Evolution narrative**: Shows how ideas developed across papers (2017-2022)
- **Comprehensive coverage**: From architecture details to training paradigms to emergent properties
- **Maintained consistency**: 206 reference inconsistencies fixed during audit

## Project Structure

```
llm-wiki-demo/
├── raw/                    # Source papers (PDFs)
│   ├── 1706.03762v7.pdf   # Transformer paper
│   ├── 1810.04805v2.pdf   # BERT paper
│   ├── 2005.14165v4.pdf   # GPT-3 paper
│   ├── 2108.07258v3.pdf   # Foundation Models
│   ├── 2203.02155v1.pdf   # InstructGPT
│   └── new_source.pdf     # Educational material
└── wiki/                   # Generated knowledge base
    ├── index.md           # Main entry point with full listing
    └── *.md               # 32 entity pages (one per concept)
```


## How It Was Built

This wiki was created through a multi-stage process using Claude as a research assistant:

### Stage 1: Initial Compilation

Extract concepts from papers and create interconnected pages.

**Prompt:**

```
Read the papers in raw/ and create entity pages in wiki/. For each key concept create a markdown file with a summary, explanation, related links using [[brackets]], and note any contradictions between papers. Create and index.md file listing every entity page with a one-line description. 
```

**Result:** 24 initial entity pages covering key concepts from 5 papers

### Stage 2: Incremental Updates

Add new sources and integrate their concepts into existing wiki.

**Prompt:**

```
A new resource has been added. Read it alongside the existing wiki pages. Update any existing entity pages affected by this new source. Create new entity pages for any new concepts introduced.
Flag any contradictions with previously compiled knowledge.
```

**Result:** 5 new entity pages added (Query-Key-Value, Layer Normalization, Residual Connections, Contextual Embeddings, Tokenization), existing pages enhanced

### Stage 3: Quality Audit

Ensure consistency, completeness, and accuracy across the entire wiki.

**Prompt:**

```
Audit the entire wiki/ folder. Identify: 1. Orphan pages -- pages that no other page links to 2. Missing pages -- concepts referenced with [[brackets]] that don't have their own page yet 3. Contradictions -- claims that conflict across pages 4. Stale claims -- things that may have been superseded by a more recent source in raw/ Suggest fixes and, where confident, apply them directly.
```

