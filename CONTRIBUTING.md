# Contributing

Thanks for helping improve this research map.

## What to Add

Good additions usually satisfy at least one of these criteria:

- The work proposes a data quality evaluation method, metric, benchmark, or diagnostic.
- The work improves data quality through filtering, deduplication, selection, rewriting, augmentation, or synthesis.
- The work studies how data quality affects model capability, safety, robustness, fairness, or evaluation reliability.
- The tool or dataset is useful for reproducible data-centric AI research.

## Entry Format

Use concise, research-oriented summaries:

```markdown
- **Title** - [原文](paper-url) · [阅读笔记](docs/reading-notes.md#title-anchor) - One-sentence summary focused on data quality. Optional: [Code](code-url), [Dataset](dataset-url).
```

Also add a matching section in `docs/reading-notes.md` with a stable anchor:

```markdown
<a id="title-anchor"></a>
## Title

- Primary taxonomy category:
- Cross-tags:
- README subsection:
- Original:
- README summary:
```

Use [docs/taxonomy.md](docs/taxonomy.md) to choose one primary taxonomy category:

- `A1-A5`: Scaling Laws
- `B1-B6`: Data Selection and Improvement
- `C1-C6`: Quality Evaluation Metrics

If the resource is mainly a tool, dataset, benchmark, or modality-specific application, use the closest README subsection and add cross-tags such as `B2 LLM pretraining data selection`, `B6 filtering/cleaning/deduplication`, or `C2 semantic consistency`.

For a careful paper read, expand the lightweight entry with [docs/paper-note-template.md](docs/paper-note-template.md). The full template is designed for deep notes that capture equations, figures, tables, data-quality signals, limitations, and reproducibility.

Prefer stable links in this order:

1. Publisher or conference page
2. arXiv or OpenReview
3. Official project page
4. GitHub repository
5. Hugging Face dataset/model page

## Quality Bar

- Avoid adding generic LLM papers unless the data quality connection is explicit.
- Prefer primary sources over blog posts.
- Add tool links only when the tool is maintained or historically important.
- Keep descriptions neutral and avoid hype.
- If a method has known risks, add a short note.

## Suggested Tags

Use tags in descriptions when useful:

- `A1 pretraining scaling`
- `A2 data-constrained scaling`
- `A3 data mixture scaling`
- `A5 post-training scaling`
- `B1 data valuation`
- `B2 LLM pretraining data selection`
- `B6 filtering cleaning deduplication`
- `B4 alignment data selection`
- `C1 toxicity`
- `C2 semantic consistency`
- `C3 knowledge density`
- `pretraining`
- `instruction tuning`
- `alignment`
- `synthetic data`
- `deduplication`
- `data valuation`
- `influence`
- `RAG`
- `multimodal`
- `contamination`
- `safety`
