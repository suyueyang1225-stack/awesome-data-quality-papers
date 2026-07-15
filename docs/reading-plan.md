# Reading Plan

This reading plan turns the repository into a research workflow.

## Week 1: Scope and Taxonomy

- Read the surveys in "General Surveys and Position Papers".
- Build a private glossary for quality, utility, diversity, provenance, and contamination.
- Decide whether the target paper is primarily about evaluation, improvement, or a closed-loop system.

## Week 2: Pretraining Data Quality

- Read DataComp-LM, FineWeb, Dolma, RedPajama, and QuRating.
- Extract each paper's quality signals, filters, ablation protocol, and downstream metrics.
- Compare rule-based, model-based, and human-preference-inspired quality signals.

## Week 3: Instruction and Alignment Data

- Read AlpaGasus, LESS, LIMA, and instruction backtranslation.
- Study when fewer examples improve model behavior.
- Map quality dimensions for instruction-response pairs: correctness, helpfulness, diversity, safety, and target skill transfer.

## Week 4: Data Valuation and Influence

- Read Data Shapley, TracIn, Datamodels, and LESS.
- Compare per-example value, subset value, and target-task influence.
- Identify which methods can scale to foundation-model data.

## Week 5: Tools and Reproducibility

- Try Data-Juicer, Dingo, Dolma Toolkit, and DCLM on a small dataset.
- Draft an executable data recipe with input schema, filters, metrics, thresholds, and evaluation scripts.
- Record failure cases and quality-metric disagreements.

## Week 6: Paper Design

- Convert the taxonomy into a problem statement.
- Define baselines, target datasets, quality metrics, improvement operations, and validation tasks.
- Write the first version of the experiment table.

