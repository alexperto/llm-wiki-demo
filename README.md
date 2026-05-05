# LLM wiki demo

Based on https://datasciencedojo.com/blog/llm-wiki-tutorial


## Prompts

### Initial compilation:

```
Read the papers in raw/ and create entity pages in wiki/. For each key concept create a markdown file with a summary, explanation, related links using [[brackets]], and note any contradictions between papers. Create and index.md file listing every entity page with a one-line description. 
```

### Update sources and compound

```
A new resource has been added. Read it alongside the existing wiki pages. Update any existing entity pages affected by this new source. Create new entity pages for any new concepts introduced.
Flag any contradictions with previously compiled knowledge.
```

### Linting Pass

Run linting after every 20 new pages, or any time you add a source that significantly updates a topic already in the wiki

```
Audit the entire wiki/ folder. Identify: 1. Orphan pages -- pages that no other page links to 2. Missing pages -- concepts referenced with [[brackets]] that don't have their own page yet 3. Contradictions -- claims that conflict across pages 4. Stale claims -- things that may have been superseded by a more recent source in raw/ Suggest fixes and, where confident, apply them directly.
```