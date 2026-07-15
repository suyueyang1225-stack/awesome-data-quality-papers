# Reading Plan

This reading plan turns the repository into a research workflow.

## Week 1: Scope and Taxonomy

- Read the surveys in "General Surveys".
- Build a private glossary for quality, utility, diversity, provenance, and contamination.
- Decide whether the target paper is primarily about scaling laws, data selection and improvement, or quality evaluation metrics.

## Week 2: Scaling Laws

- Read scaling-law papers for pretraining, data-constrained regimes, data mixing, downstream transfer, and post-training.
- Extract the variables each paper scales: model size, token count, data mixture, data quality, SFT/RL data volume, and reward optimization budget.
- Identify which scaling laws can predict returns from better data before full-scale training.

## Week 3: Data Selection and Improvement

- Read Data Shapley, TracIn, Datamodels, LESS, AlpaGasus, LIMA, pretraining-data selection, filtering, deduplication, and synthetic-data curation papers.
- Compare per-example value, subset value, target-task influence, data mixture optimization, cleaning, deduplication, and generation quality control.
- Study when fewer, cleaner, denser, or better-selected examples improve model behavior, and when filtering harms coverage or robustness.

## Week 4: Quality Evaluation Metrics

- Read toxicity, detoxification, factual/semantic consistency, LLM-as-judge, knowledge-density, and educational-value metric papers.
- Map metrics to data operations: filtering, rewriting, correction, deduplication, densification, and selection.
- Record metric disagreements, false positives, minority-language or dialect risks, and task-specific failure modes.

## Week 5: Tools and Reproducibility

- Try Data-Juicer, Dingo, Dolma Toolkit, and DCLM on a small dataset.
- Draft an executable data recipe with input schema, filters, metrics, thresholds, and evaluation scripts.
- Record failure cases and quality-metric disagreements.

## Week 6: Paper Design

- Convert the taxonomy into a problem statement.
- Define baselines, target datasets, quality metrics, improvement operations, and validation tasks.
- Write the first version of the experiment table.
