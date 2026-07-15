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
- **Title** - [原文](paper-url) · [阅读笔记](docs/paper-note-template.md) - One-sentence summary focused on data quality. Optional: [Code](code-url), [Dataset](dataset-url).
```

All paper entries should link `阅读笔记` to `docs/paper-note-template.md` unless the repository later adds a dedicated completed-note file for that specific paper.

## Required Reading Note Standard

Completed paper notes must follow [docs/paper-note-template.md](docs/paper-note-template.md). This is required for collaborative reading, so contributors can compare notes across papers without reverse-engineering each person's style.

Do not remove template sections. If a paper has no equations, figures, tables, code, released data, or contamination checks, keep the section and write `N/A` with a short reason.

A completed note must include:

- Primary taxonomy category and cross-tags from [docs/taxonomy.md](docs/taxonomy.md).
- Original paper link, code link, dataset link, year, venue, and authors.
- One-sentence takeaway and research question.
- Method, metric, system, or scaling-law details.
- Equations or scoring rules, if present.
- Figure and table summaries, if present.
- Data and experimental setup.
- Data-quality angle, including quality signals and improvement operations.
- Critical assessment, failure modes, and reproducibility status.
- Implications for this repository's research direction.

Use `docs/reading-notes.md` only as a lightweight reading-progress index:

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

For a careful paper read, copy the full structure from [docs/paper-note-template.md](docs/paper-note-template.md) and fill it completely.

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
