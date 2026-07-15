# Systematic Taxonomy

This taxonomy defines the repository structure for data quality evaluation and improvement research.

Each paper should have:

- One primary category: where the paper should be listed first.
- Optional cross-tags: other directions it informs.
- Two required entrances from the README: `[原文](...)` and `[阅读笔记](...)`.

## Top-Level Structure

| Pillar | Core Question | Typical Outputs |
| --- | --- | --- |
| A. Scaling Laws | How do data quantity, quality, mixture, model scale, compute, and post-training budget interact? | Scaling curves, compute-optimal rules, data-mixture laws, transfer laws |
| B. Data Selection | Which data should be kept, weighted, mixed, scheduled, or generated for a target capability? | Selection scores, influence values, filters, curricula, data recipes |
| C. Quality Evaluation Metrics | How do we measure whether data is useful, safe, consistent, dense, and reliable? | Metrics, benchmarks, judges, diagnostic dashboards, audit protocols |

Supporting sections are used when a resource is primarily a system, dataset, benchmark, or modality-specific application rather than a method paper.

## A. Scaling Laws

Use this pillar when the paper studies predictable relationships between training resources, data properties, and model behavior.

| Code | Subcategory | Use When | Representative Papers |
| --- | --- | --- | --- |
| A1 | Pretraining compute/token scaling | The work models loss or capability as a function of parameters, tokens, or compute. | Scaling Laws for Neural Language Models; Training Compute-Optimal Large Language Models |
| A2 | Data-constrained scaling | The work studies finite high-quality data, repetition, scarcity, or data reuse. | Scaling Data-Constrained Language Models |
| A3 | Data mixture and domain scaling | The work predicts how mixture proportions or domain composition affect model performance. | Data Mixing Laws |
| A4 | Downstream transfer scaling | The work connects pretraining data and scale to fine-tuned or downstream task performance. | Scaling Laws for Downstream Task Performance of Large Language Models |
| A5 | Post-training and alignment scaling | The work studies SFT, RLHF, DPO, reward models, RL reasoning, or overoptimization as scale changes. | Scaling Laws for Reward Model Overoptimization; Scaling Behaviors of LLM Reinforcement Learning Post-Training |

Primary signals:

- Contains explicit scaling variables such as model size, tokens, compute, dataset size, data mixture, or post-training budget.
- Reports fitted laws, predictable trends, or compute/data tradeoffs.
- Helps estimate whether better data can substitute for more data or compute.

## B. Data Selection

Use this pillar when the paper decides which examples, documents, domains, instructions, or synthetic samples should enter training or evaluation.

| Code | Subcategory | Use When | Representative Papers |
| --- | --- | --- | --- |
| B1 | Data valuation and influence | The work estimates the marginal contribution of examples or subsets. | Data Shapley; TracIn; Datamodels; LESS |
| B2 | Quality filtering and document scoring | The work assigns quality scores or filters low-value data before training. | QuRating; FineWeb; Rethinking Classifier-Based Quality Filtering |
| B3 | Mixture optimization and curriculum | The work chooses domain proportions, schedules data, or balances diversity and specialization. | Data Mixing Laws; DataComp-LM |
| B4 | Instruction and alignment data selection | The work selects SFT, preference, or alignment data for target behavior. | AlpaGasus; What Makes Good Data for Alignment; LIMA |
| B5 | Synthetic and rewritten data selection | The work filters, validates, or selects generated data after synthesis or rewriting. | Self-Instruct; Instruction Backtranslation; LLMs-Driven Synthetic Data Generation, Curation, and Evaluation |

Primary signals:

- The central object is a selection, filtering, weighting, routing, or scheduling decision.
- The paper compares selected data against random, heuristic, or full-data baselines.
- The method is evaluated by downstream model utility, target capability transfer, or data efficiency.

## C. Quality Evaluation Metrics

Use this pillar when the paper defines, validates, or audits signals of data quality, regardless of whether the data is later selected or improved.

| Code | Subcategory | Use When | Representative Papers |
| --- | --- | --- | --- |
| C1 | Toxicity, safety, and detoxification | The work measures toxic content, bias, harmfulness, detoxification side effects, or safety risk. | RealToxicityPrompts; ToxiGen; Detoxifying Language Models Risks Marginalizing Minority Voices |
| C2 | Semantic and factual consistency | The work measures entailment, contradiction, hallucination, grounding, or cross-sample agreement. | TRUE; SelfCheckGPT; RAGAS |
| C3 | Knowledge density and educational value | The work measures useful knowledge per token, expertise, textbook quality, or learning value. | Textbooks Are All You Need; FineWeb-Edu; QuRating |
| C4 | Diversity, coverage, and representativeness | The work measures domain, language, skill, demographic, or difficulty coverage. | DataComp-LM; DataComp |
| C5 | Contamination and evaluation reliability | The work detects leakage, memorization, benchmark contamination, or unreliable evaluation data. | Benchmark Data Contamination Survey; Detecting Pretraining Data |
| C6 | Multimodal quality signals | The work evaluates image-text alignment, caption quality, visual instruction quality, or image quality. | CLIPScore; DataComp; MLLMs for Image Quality Assessment |

Primary signals:

- The main contribution is a metric, benchmark, judge, annotation protocol, or diagnostic.
- The paper validates correlation with human judgment, model performance, safety, or factuality.
- The metric can guide selection, cleaning, rewriting, or audit decisions.

## Supporting Sections

| Section | Role |
| --- | --- |
| General Surveys and Position Papers | Broad maps of data-centric AI, data valuation, synthetic data, or dataset quality. |
| Data Quality for LLM Pretraining | Corpus construction, web data filtering, deduplication, and pretraining data recipes. |
| Instruction Tuning and Alignment Data | SFT, preference, alignment, and instruction-response datasets. |
| Filtering, Cleaning, and Deduplication | Operational data repair and removal methods. |
| Synthetic Data Generation and Curation | Data creation, rewriting, expansion, and post-generation quality control. |
| Multimodal Data Quality | Image-text, video-text, visual instruction, and multimodal quality work. |
| RAG Data Quality | Retrieval corpus, chunk, query, context, and answer quality evaluation. |
| Tools and Systems | Reusable software for data processing, evaluation, and auditing. |
| Datasets and Data-Centric Benchmarks | Public corpora and benchmark suites used for data quality research. |

## Classification Rules

1. Choose the primary category by the paper's main research question, not by every method it uses.
2. If the paper predicts behavior under scale, use Scaling Laws.
3. If the paper chooses data to train on, use Data Selection.
4. If the paper measures quality or builds an evaluation signal, use Quality Evaluation Metrics.
5. If a paper spans multiple pillars, list it in the primary section and mention cross-tags in the reading note.
6. If a resource is mostly software or a dataset, list it under Tools and Systems or Datasets and Data-Centric Benchmarks, then cross-tag it in the reading note.

## Reading Workflow

| Research Goal | Start Here | Then Read |
| --- | --- | --- |
| Estimate the return from more or better data | A1, A2, A3 | B2, C3 |
| Build a data selection pipeline | B1, B2, B3 | A3, C2, C3, C4 |
| Study post-training data quality | A5, B4 | C1, C2, C3 |
| Design quality metrics | C1, C2, C3 | B2, Filtering/Cleaning |
| Work on toxicity correction | C1 | Synthetic Data Generation and Curation; Filtering/Cleaning |
| Work on semantic consistency repair | C2 | RAG Data Quality; Synthetic Data Generation and Curation |
| Work on knowledge-dense training data | C3 | A2, B2, Data Quality for LLM Pretraining |
