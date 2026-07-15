# Awesome Data Quality Evaluation and Improvement Papers

[![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

A curated research map of papers, datasets, benchmarks, tools, and open questions for **data quality evaluation and improvement** in modern AI systems.

This repository is designed to support research on how to measure, diagnose, select, clean, synthesize, and improve data for foundation models, instruction tuning, multimodal models, RAG systems, and classical machine learning pipelines.

Research context: [Feishu research note](https://hyjx6666.feishu.cn/docx/Ww2DdU7ftonL1bxrwvucUcRYnCb)

## Overview

Data quality is no longer only a preprocessing detail. In large-scale AI, data quality directly shapes model capability, safety, bias, factuality, compute efficiency, and evaluation reliability.

This repository organizes the field around three questions:

- **How do we evaluate data quality?** Metrics, quality signals, data attribution, contamination checks, diversity/coverage analysis, and task-aware utility.
- **How do we improve data quality?** Filtering, deduplication, data selection, rewriting, augmentation, synthetic data generation, curriculum design, and data mixture optimization.
- **How do we validate improvement?** Controlled ablations, downstream evaluation, robustness/safety checks, cost-quality tradeoffs, and reproducible data recipes.

### Key Dimensions

- **Correctness**: factuality, label validity, answer faithfulness, instruction-response alignment.
- **Usefulness**: task relevance, target capability transfer, educational value, information density.
- **Diversity**: coverage of domains, skills, languages, styles, difficulty levels, and demographics.
- **Safety**: toxicity, privacy leakage, prompt injection, bias, harmful instructions, unsafe outputs.
- **Freshness**: temporal validity, stale facts, outdated web content, versioned knowledge.
- **Deduplication**: exact duplicates, near duplicates, benchmark leakage, train-test contamination.
- **Traceability**: provenance, licenses, metadata, curation logs, and reproducible processing pipelines.

## Contents

- [General Surveys and Position Papers](#general-surveys-and-position-papers)
- [Data Quality for LLM Pretraining](#data-quality-for-llm-pretraining)
- [Instruction Tuning and Alignment Data](#instruction-tuning-and-alignment-data)
- [Data Selection, Valuation, and Influence](#data-selection-valuation-and-influence)
- [Filtering, Cleaning, and Deduplication](#filtering-cleaning-and-deduplication)
- [Synthetic Data Generation and Curation](#synthetic-data-generation-and-curation)
- [Multimodal Data Quality](#multimodal-data-quality)
- [RAG Data Quality](#rag-data-quality)
- [Benchmark Contamination and Evaluation Reliability](#benchmark-contamination-and-evaluation-reliability)
- [Tools and Systems](#tools-and-systems)
- [Datasets and Data-Centric Benchmarks](#datasets-and-data-centric-benchmarks)
- [Research Roadmap](#research-roadmap)
- [Contribution Guide](#contribution-guide)

## General Surveys and Position Papers

- [Data-Centric Artificial Intelligence](https://arxiv.org/abs/2212.11854) - A broad survey of data-centric AI goals, methods, and lifecycle thinking.
- [Systematic Review of Data-Centric Approaches in Artificial Intelligence and Machine Learning](https://www.sciencedirect.com/science/article/pii/S2666764923000279) - Reviews data quality assessment, preprocessing, transfer learning, semi-supervised learning, MLOps, and data scale effects.
- [Data Valuation in Machine Learning: Ingredients, Strategies, and Open Challenges](https://www.ijcai.org/proceedings/2022/782) - Formalizes data valuation and compares major valuation strategies.
- [On LLMs-Driven Synthetic Data Generation, Curation, and Evaluation](https://aclanthology.org/2024.findings-acl.658/) - Survey of synthetic data workflows, curation, evaluation, and risks.
- [What Makes a High-Quality Training Dataset for Large Language Models: A Practitioners' Perspective](https://nzjohng.github.io/publications/papers/ase2024_1.pdf) - Practitioner-oriented discussion of dataset quality factors for LLM development.

## Data Quality for LLM Pretraining

- [DataComp-LM: In Search of the Next Generation of Training Sets for Language Models](https://arxiv.org/abs/2406.11794) - Controlled testbed for language-model data curation, including filtering, deduplication, data mixing, and downstream evaluation.
- [The FineWeb Datasets: Decanting the Web for the Finest Text Data at Scale](https://arxiv.org/abs/2406.17557) - Documents large-scale web data filtering, deduplication, and ablations behind FineWeb and FineWeb-Edu.
- [Dolma: An Open Corpus of Three Trillion Tokens for Language Model Pretraining Research](https://arxiv.org/abs/2402.00159) - Open corpus and toolkit with documented curation choices and intermediate analyses.
- [RedPajama: An Open Dataset for Training Large Language Models](https://papers.nips.cc/paper_files/paper/2024/hash/d34497330b1fd6530f7afd86d0df9f76-Abstract-Datasets_and_Benchmarks_Track.html) - Open reproduction-oriented dataset effort emphasizing transparency, access, and metadata.
- [QuRating: Selecting High-Quality Data for Training Language Models](https://arxiv.org/abs/2402.09739) - LLM-assisted quality ratings over writing style, expertise, facts/trivia, and educational value for pretraining data selection.
- [Analyzing Similarity Metrics for Data Selection for Language Model Pretraining](https://arxiv.org/abs/2502.02494) - Studies how embedding similarity relates to pretraining-loss similarity and data diversification.
- [Rethinking Classifier-Based Quality Filtering for LLM Pretraining](https://openreview.net/forum?id=vSBACt34gS) - Analyzes classifier-based quality filtering and challenges simple interpretations of quality scores.

## Instruction Tuning and Alignment Data

- [AlpaGasus: Training a Better Alpaca with Fewer Data](https://openreview.net/forum?id=FdVXgSJhvz) - Filters low-quality instruction data with an LLM judge and improves instruction tuning with fewer examples.
- [LESS: Selecting Influential Data for Targeted Instruction Tuning](https://proceedings.mlr.press/v235/xia24c.html) - Optimizer-aware influence-based selection for inducing target capabilities.
- [What Makes Good Data for Alignment? A Comprehensive Study of Automatic Data Selection in Instruction Tuning](https://openreview.net/forum?id=BTKAeLqLMw) - Studies automatic instruction-data selection for alignment.
- [Self-Alignment with Instruction Backtranslation](https://openreview.net/forum?id=1oijHJBRsT) - Uses model-generated instructions from high-quality responses to improve instruction tuning data.
- [LIMA: Less Is More for Alignment](https://arxiv.org/abs/2305.11206) - Shows strong alignment behavior can emerge from a small carefully curated supervised fine-tuning dataset.

## Data Selection, Valuation, and Influence

- [Data Shapley: Equitable Valuation of Data for Machine Learning](https://arxiv.org/abs/1904.02868) - Shapley-value framework for assigning value to individual training examples.
- [Estimating Training Data Influence by Tracing Gradient Descent](https://proceedings.neurips.cc/paper/2020/hash/e6385d39ec9394f2f3a354d9d2b88eec-Abstract.html) - TracIn estimates example influence using checkpoints and gradient information.
- [Data Valuation Using Reinforcement Learning](https://arxiv.org/abs/1909.11671) - Learns data valuation policies for selecting beneficial samples.
- [Datamodels: Predicting Predictions from Training Data](https://arxiv.org/abs/2202.00622) - Models how training subsets affect predictions and supports dataset debugging.
- [LESS](https://github.com/princeton-nlp/LESS) - Codebase for influence-based targeted instruction data selection.
- [pyDVL](https://pydvl.org/stable/value/) - Python library for data valuation methods and workflows.

## Filtering, Cleaning, and Deduplication

- [Data-Juicer: A One-Stop Data Processing System for Large Language Models](https://arxiv.org/abs/2309.02033) - System for scalable LLM data processing, analysis, and data recipe exploration.
- [Data-Juicer 2.0: Cloud-Scale Adaptive Data Processing for and with Foundation Models](https://proceedings.neurips.cc/paper_files/paper/2025/file/76dbd7e897be2eb883ede598b91270fb-Paper-Datasets_and_Benchmarks_Track.pdf) - Extends data processing to multimodal and cloud-scale pipelines.
- [Deduplicating Training Data Makes Language Models Better](https://arxiv.org/abs/2107.06499) - Studies exact and near-deduplication effects on language modeling.
- [SemDeDup: Data-Efficient Learning at Web-Scale Through Semantic Deduplication](https://arxiv.org/abs/2303.09540) - Semantic deduplication method for reducing redundancy while preserving performance.
- [CCNet: Extracting High Quality Monolingual Datasets from Web Crawl Data](https://arxiv.org/abs/1911.00359) - Classic Common Crawl filtering pipeline for language-model corpora.
- [deduplicate-text-datasets](https://github.com/google-research/deduplicate-text-datasets) - Official code for exact-substring deduplication from "Deduplicating Training Data Makes Language Models Better".

## Synthetic Data Generation and Curation

- [Self-Instruct: Aligning Language Models with Self-Generated Instructions](https://arxiv.org/abs/2212.10560) - Bootstraps instruction-following data from model-generated instructions.
- [Evol-Instruct](https://arxiv.org/abs/2304.12244) - Evolves instruction data to increase complexity and diversity.
- [WizardLM](https://arxiv.org/abs/2304.12244) - Uses evolved instructions to improve instruction-following models.
- [Orca: Progressive Learning from Complex Explanation Traces of GPT-4](https://arxiv.org/abs/2306.02707) - Uses explanation-rich synthetic data for imitation learning.
- [Phi-1: Textbooks Are All You Need](https://arxiv.org/abs/2306.11644) - Demonstrates the power of high-quality synthetic textbook-style data for code models.
- [LLMs-Driven Synthetic Data Generation, Curation, and Evaluation](https://arxiv.org/abs/2406.15126) - Survey of synthetic data generation and evaluation pipelines.

## Multimodal Data Quality

- [DataComp: In Search of the Next Generation of Multimodal Datasets](https://arxiv.org/abs/2304.14108) - Benchmark for dataset filtering strategies in multimodal contrastive learning.
- [LAION-5B: An Open Large-Scale Dataset for Training Next Generation Image-Text Models](https://arxiv.org/abs/2210.08402) - Large-scale image-text dataset with filtering and safety-related documentation.
- [CLIPScore: A Reference-free Evaluation Metric for Image Captioning](https://arxiv.org/abs/2104.08718) - Uses image-text alignment as a quality signal.
- [TIVE: Less is More: High-Value Data Selection for Visual Instruction Tuning](https://github.com/simplelifetime/TIVE) - Studies redundancy and data selection in visual instruction data.
- [A Comprehensive Study of Multimodal Large Language Models for Image Quality Assessment](https://arxiv.org/abs/2403.10854) - Evaluates multimodal LLMs as image quality assessors.

## RAG Data Quality

- [RAGAS: Automated Evaluation of Retrieval Augmented Generation](https://arxiv.org/abs/2309.15217) - Evaluation framework for context relevance, faithfulness, answer correctness, and related RAG metrics.
- [ARES: An Automated Evaluation Framework for Retrieval-Augmented Generation Systems](https://arxiv.org/abs/2311.09476) - Automated RAG evaluation with synthetic queries and judge models.
- [Corrective Retrieval Augmented Generation](https://arxiv.org/abs/2401.15884) - Adds retrieved-document quality checks and correction behavior.
- [Contextual Retrieval](https://www.anthropic.com/engineering/contextual-retrieval) - Enriches chunks with context before indexing to reduce retrieval failures.
- [RAGChecker](https://arxiv.org/abs/2408.08067) - Fine-grained diagnostic framework for RAG systems.

## Benchmark Contamination and Evaluation Reliability

- [Benchmark Data Contamination of Large Language Models: A Survey](https://arxiv.org/abs/2406.04244) - Reviews benchmark leakage, detection, and mitigation for LLM evaluation.
- [Data Contamination: From Memorization to Exploitation](https://arxiv.org/abs/2312.08242) - Studies contamination effects and evaluation reliability.
- [Detecting Pretraining Data from Large Language Models](https://arxiv.org/abs/2310.16789) - Detects whether text was likely present in model pretraining data.
- [The WMDP Benchmark: Measuring and Reducing Malicious Use With Unlearning](https://arxiv.org/abs/2403.03218) - Useful for safety-sensitive data filtering and unlearning-oriented evaluation.

## Tools and Systems

- [Data-Juicer](https://github.com/datajuicer/data-juicer) - Modular data processing system for foundation-model data.
- [Dingo](https://github.com/DataEval/dingo) - AI data quality evaluation platform for training data, fine-tuning data, RAG systems, and model outputs.
- [Dolma Toolkit](https://github.com/allenai/dolma) - Toolkit for curation and documentation of large language-model corpora.
- [DCLM](https://github.com/mlfoundations/dclm) - DataComp-LM framework for controlled dataset experiments.
- [datasketch](https://github.com/ekzhu/datasketch) - MinHash and locality-sensitive hashing library useful for near-deduplication.
- [Cleanlab](https://github.com/cleanlab/cleanlab) - Data-centric AI package for label-error detection and dataset diagnostics.
- [Ragas](https://github.com/explodinggradients/ragas) - RAG evaluation library.
- [DeepEval](https://github.com/confident-ai/deepeval) - LLM and RAG evaluation framework.
- [Great Expectations](https://github.com/great-expectations/great_expectations) - Data quality validation framework for structured data pipelines.

## Datasets and Data-Centric Benchmarks

- [DataComp-LM](https://github.com/mlfoundations/dclm) - Benchmark and corpus for language-model data curation experiments.
- [FineWeb](https://huggingface.co/datasets/HuggingFaceFW/fineweb) - Large-scale filtered web corpus.
- [FineWeb-Edu](https://huggingface.co/datasets/HuggingFaceFW/fineweb-edu) - Educational-quality subset derived from FineWeb.
- [Dolma](https://huggingface.co/datasets/allenai/dolma) - Open pretraining corpus from AI2.
- [RedPajama-Data](https://github.com/togethercomputer/RedPajama-Data) - Open LLM pretraining data recipes and metadata.
- [The Pile](https://arxiv.org/abs/2101.00027) - Large open text corpus with diverse sources.
- [OpenWebText](https://skylion007.github.io/OpenWebTextCorpus/) - Open reproduction-style web text corpus.

## Research Roadmap

### 1. Metric Design

- Build task-aware quality metrics instead of relying only on generic heuristics.
- Separate intrinsic data quality from model-, objective-, and evaluation-dependent utility.
- Measure quality across correctness, diversity, safety, freshness, and provenance.

### 2. Evaluation Protocols

- Use controlled ablations that isolate one data operation at a time.
- Report compute-normalized gains, not only final model scores.
- Evaluate side effects: bias, language/domain coverage, memorization, and safety.

### 3. Data Improvement Methods

- Compare rule-based filters, model-based filters, influence methods, and LLM judges.
- Study data rewriting and repair, not only removal.
- Treat data mixture optimization as a first-class research object.

### 4. Reproducibility

- Version datasets, filters, thresholds, prompts, and model checkpoints.
- Publish metadata schemas and data cards.
- Prefer executable data recipes over prose-only descriptions.

### 5. Open Problems

- How can we evaluate data quality without training expensive proxy models?
- Can quality metrics generalize across domains, languages, and modalities?
- When does filtering improve benchmark scores while harming diversity or robustness?
- How should we evaluate generated or rewritten data when references are unavailable?
- Can data quality improvement be made interactive, auditable, and human-controllable?

## Contribution Guide

Contributions are welcome. Please see [CONTRIBUTING.md](CONTRIBUTING.md).

When adding a paper, prefer this format:

```markdown
- [Paper Title](paper-url) - One-sentence summary focused on data quality evaluation or improvement. Optional: [Code](code-url), [Dataset](dataset-url).
```

## Related Awesome Lists

- [Awesome RAG](https://github.com/Danielskry/Awesome-RAG)
- [Awesome Data Quality](https://github.com/MigoXLab/awesome-data-quality)
- [Data-Centric AI](https://github.com/daochenzha/data-centric-ai)
- [Awesome Data Valuation](https://github.com/daviddao/awesome-data-valuation)

## License

This repository is released under the [CC0 1.0 Universal](LICENSE) public domain dedication.
