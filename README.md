# Awesome Data Quality Evaluation and Improvement Papers

[![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

A curated research map of papers, datasets, benchmarks, tools, and open questions for **data quality evaluation and improvement** in modern AI systems.

This repository is designed to support research on how to measure, diagnose, select, clean, synthesize, and improve data for foundation models, instruction tuning, multimodal models, RAG systems, and classical machine learning pipelines.

Research context: [Feishu research note](https://hyjx6666.feishu.cn/docx/Ww2DdU7ftonL1bxrwvucUcRYnCb)

## Overview

Data quality is no longer only a preprocessing detail. In large-scale AI, data quality directly shapes model capability, safety, bias, factuality, compute efficiency, and evaluation reliability.

This repository organizes the field around three research directions:

- **Scaling laws**: how data quantity, data quality, data mixture, model size, compute, and post-training budget interact in pretraining and post-training.
- **Data selection**: how to select, value, filter, mix, and schedule data for target capabilities under compute and annotation constraints.
- **Quality evaluation metrics**: how to measure toxicity and detoxification effects, semantic/factual consistency, knowledge density, educational value, safety, and downstream utility.

### Key Dimensions

- **Correctness**: factuality, label validity, answer faithfulness, instruction-response alignment.
- **Usefulness**: task relevance, target capability transfer, educational value, information density.
- **Semantic Consistency**: entailment, contradiction, hallucination, source grounding, and cross-sample agreement.
- **Knowledge Density**: amount of useful, non-redundant, learnable knowledge per token or example.
- **Diversity**: coverage of domains, skills, languages, styles, difficulty levels, and demographics.
- **Safety**: toxicity, privacy leakage, prompt injection, bias, harmful instructions, unsafe outputs.
- **Freshness**: temporal validity, stale facts, outdated web content, versioned knowledge.
- **Deduplication**: exact duplicates, near duplicates, benchmark leakage, train-test contamination.
- **Traceability**: provenance, licenses, metadata, curation logs, and reproducible processing pipelines.

## Systematic Taxonomy

The repository uses a three-pillar taxonomy. See [docs/taxonomy.md](docs/taxonomy.md) for the full classification rules, cross-tag policy, and reading workflow.

| Pillar | Substructure | Main Result |
| --- | --- | --- |
| **Scaling Laws** | Pretraining scaling, data-constrained scaling, data mixture/domain scaling, downstream transfer scaling, post-training/alignment scaling | Predict how data quality and quantity interact with compute, model size, and training stage. |
| **Data Selection** | Data valuation/influence, quality filtering, mixture optimization, instruction/alignment data selection, synthetic data selection | Decide which data should be kept, weighted, mixed, scheduled, or generated for target capabilities. |
| **Quality Evaluation Metrics** | Toxicity/safety, semantic/factual consistency, knowledge density, diversity/coverage, contamination, multimodal quality | Measure whether data is useful, safe, consistent, dense, representative, and reliable. |

## Contents

### 1. Research Structure

- [Systematic Taxonomy](#systematic-taxonomy) - three-pillar classification and reading workflow.
- [General Surveys and Position Papers](#general-surveys-and-position-papers) - field-level maps and framing papers.

### 2. Core Research Directions

- [Scaling Laws (Pretraining and Post-training)](#scaling-laws-pretraining-and-post-training) - data quantity, quality, mixture, compute, and training-stage scaling.
- [Data Selection](#data-selection) - valuation, influence, filtering, mixture optimization, and targeted selection.
- [Quality Evaluation Metrics](#quality-evaluation-metrics) - toxicity, semantic consistency, knowledge density, diversity, and reliability metrics.

### 3. Data Scenarios and Improvement Methods

- [Data Quality for LLM Pretraining](#data-quality-for-llm-pretraining) - web corpora, corpus recipes, filtering, and pretraining data quality.
- [Instruction Tuning and Alignment Data](#instruction-tuning-and-alignment-data) - SFT, preference, and alignment data quality.
- [Filtering, Cleaning, and Deduplication](#filtering-cleaning-and-deduplication) - operational data repair and removal methods.
- [Synthetic Data Generation and Curation](#synthetic-data-generation-and-curation) - generation, rewriting, expansion, and post-generation curation.
- [Multimodal Data Quality](#multimodal-data-quality) - image-text, visual instruction, and multimodal quality signals.
- [RAG Data Quality](#rag-data-quality) - retrieval corpus, chunk, context, and answer quality.

### 4. Evaluation Reliability

- [Benchmark Contamination and Evaluation Reliability](#benchmark-contamination-and-evaluation-reliability) - leakage, memorization, and benchmark trustworthiness.

### 5. Resources and Project Docs

- [Tools and Systems](#tools-and-systems) - reusable software for processing, evaluation, and auditing.
- [Datasets and Data-Centric Benchmarks](#datasets-and-data-centric-benchmarks) - public corpora and benchmarks.
- [Research Roadmap](#research-roadmap) - open problems and research agenda.
- [Contribution Guide](#contribution-guide) - how to add papers and notes.
- [Reading Notes](docs/reading-notes.md) - structured notes for listed papers.

## General Surveys

- **Data-Centric Artificial Intelligence** - [原文](https://arxiv.org/abs/2212.11854) · [阅读笔记](docs/reading-notes.md#data-centric-artificial-intelligence) - A broad survey of data-centric AI goals, methods, and lifecycle thinking.
- **Systematic Review of Data-Centric Approaches in Artificial Intelligence and Machine Learning** - [原文](https://www.sciencedirect.com/science/article/pii/S2666764923000279) · [阅读笔记](docs/reading-notes.md#systematic-review-of-data-centric-approaches-in-artificial-intelligence-and-machine-learning) - Reviews data quality assessment, preprocessing, transfer learning, semi-supervised learning, MLOps, and data scale effects.
- **Data Valuation in Machine Learning: Ingredients, Strategies, and Open Challenges** - [原文](https://www.ijcai.org/proceedings/2022/782) · [阅读笔记](docs/reading-notes.md#data-valuation-in-machine-learning-ingredients-strategies-and-open-challenges) - Formalizes data valuation and compares major valuation strategies.
- **On LLMs-Driven Synthetic Data Generation, Curation, and Evaluation** - [原文](https://aclanthology.org/2024.findings-acl.658/) · [阅读笔记](docs/reading-notes.md#on-llms-driven-synthetic-data-generation-curation-and-evaluation) - Survey of synthetic data workflows, curation, evaluation, and risks.
- **What Makes a High-Quality Training Dataset for Large Language Models: A Practitioners' Perspective** - [原文](https://nzjohng.github.io/publications/papers/ase2024_1.pdf) · [阅读笔记](docs/reading-notes.md#what-makes-a-high-quality-training-dataset-for-large-language-models-a-practitioners-perspective) - Practitioner-oriented discussion of dataset quality factors for LLM development.

## Scaling Laws (Pretraining and Post-training)

- **Scaling Laws for Neural Language Models** - [原文](https://arxiv.org/abs/2001.08361) · [阅读笔记](docs/reading-notes.md#scaling-laws-for-neural-language-models) - Foundational scaling law for language-model loss as a function of model size, dataset size, and compute.
- **Training Compute-Optimal Large Language Models** - [原文](https://arxiv.org/abs/2203.15556) · [阅读笔记](docs/reading-notes.md#training-compute-optimal-large-language-models) - Chinchilla-style compute-optimal scaling law for balancing parameter count and training tokens.
- **Scaling Data-Constrained Language Models** - [原文](https://arxiv.org/abs/2305.16264) · [阅读笔记](docs/reading-notes.md#scaling-data-constrained-language-models) - Studies data repetition and data scarcity, useful for reasoning about finite high-quality data and reuse.
- **Data Mixing Laws: Optimizing Data Mixtures by Predicting Language Modeling Performance** - [原文](https://arxiv.org/abs/2403.16952) · [阅读笔记](docs/reading-notes.md#data-mixing-laws-optimizing-data-mixtures-by-predicting-language-modeling-performance) - Models how pretraining data mixture proportions affect language-model performance.
- **Scaling Laws for Downstream Task Performance of Large Language Models** - [原文](https://arxiv.org/abs/2402.04177) · [阅读笔记](docs/reading-notes.md#scaling-laws-for-downstream-task-performance-of-large-language-models) - Studies how pretraining data size and distribution alignment affect fine-tuned downstream performance.
- **Scaling Laws for Reward Model Overoptimization** - [原文](https://arxiv.org/abs/2210.10760) · [阅读笔记](docs/reading-notes.md#scaling-laws-for-reward-model-overoptimization) - Post-training scaling study of reward model overoptimization and Goodhart-style failure modes.
- **Scaling Laws for Reward Model Overoptimization in Direct Alignment Algorithms** - [原文](https://arxiv.org/abs/2406.02900) · [阅读笔记](docs/reading-notes.md#scaling-laws-for-reward-model-overoptimization-in-direct-alignment-algorithms) - Extends overoptimization scaling analysis to direct alignment objectives such as DPO-style training.
- **Scaling Behaviors of LLM Reinforcement Learning Post-Training: An Empirical Study in Mathematical Reasoning** - [原文](https://arxiv.org/abs/2509.25300) · [阅读笔记](docs/reading-notes.md#scaling-behaviors-of-llm-reinforcement-learning-post-training-an-empirical-study-in-mathematical-reasoning) - Empirical study of model scale, data volume, and compute in RL-based post-training for reasoning.

## Data Quality for LLM Pretraining

- **DataComp-LM: In Search of the Next Generation of Training Sets for Language Models** - [原文](https://arxiv.org/abs/2406.11794) · [阅读笔记](docs/reading-notes.md#datacomp-lm-in-search-of-the-next-generation-of-training-sets-for-language-models) - Controlled testbed for language-model data curation, including filtering, deduplication, data mixing, and downstream evaluation.
- **The FineWeb Datasets: Decanting the Web for the Finest Text Data at Scale** - [原文](https://arxiv.org/abs/2406.17557) · [阅读笔记](docs/reading-notes.md#the-fineweb-datasets-decanting-the-web-for-the-finest-text-data-at-scale) - Documents large-scale web data filtering, deduplication, and ablations behind FineWeb and FineWeb-Edu.
- **Dolma: An Open Corpus of Three Trillion Tokens for Language Model Pretraining Research** - [原文](https://arxiv.org/abs/2402.00159) · [阅读笔记](docs/reading-notes.md#dolma-an-open-corpus-of-three-trillion-tokens-for-language-model-pretraining-research) - Open corpus and toolkit with documented curation choices and intermediate analyses.
- **RedPajama: An Open Dataset for Training Large Language Models** - [原文](https://papers.nips.cc/paper_files/paper/2024/hash/d34497330b1fd6530f7afd86d0df9f76-Abstract-Datasets_and_Benchmarks_Track.html) · [阅读笔记](docs/reading-notes.md#redpajama-an-open-dataset-for-training-large-language-models) - Open reproduction-oriented dataset effort emphasizing transparency, access, and metadata.
- **QuRating: Selecting High-Quality Data for Training Language Models** - [原文](https://arxiv.org/abs/2402.09739) · [阅读笔记](docs/reading-notes.md#qurating-selecting-high-quality-data-for-training-language-models) - LLM-assisted quality ratings over writing style, expertise, facts/trivia, and educational value for pretraining data selection.
- **Analyzing Similarity Metrics for Data Selection for Language Model Pretraining** - [原文](https://arxiv.org/abs/2502.02494) · [阅读笔记](docs/reading-notes.md#analyzing-similarity-metrics-for-data-selection-for-language-model-pretraining) - Studies how embedding similarity relates to pretraining-loss similarity and data diversification.
- **Rethinking Classifier-Based Quality Filtering for LLM Pretraining** - [原文](https://openreview.net/forum?id=vSBACt34gS) · [阅读笔记](docs/reading-notes.md#rethinking-classifier-based-quality-filtering-for-llm-pretraining) - Analyzes classifier-based quality filtering and challenges simple interpretations of quality scores.

## Instruction Tuning and Alignment Data

- **AlpaGasus: Training a Better Alpaca with Fewer Data** - [原文](https://openreview.net/forum?id=FdVXgSJhvz) · [阅读笔记](docs/reading-notes.md#alpagasus-training-a-better-alpaca-with-fewer-data) - Filters low-quality instruction data with an LLM judge and improves instruction tuning with fewer examples.
- **LESS: Selecting Influential Data for Targeted Instruction Tuning** - [原文](https://proceedings.mlr.press/v235/xia24c.html) · [阅读笔记](docs/reading-notes.md#less-selecting-influential-data-for-targeted-instruction-tuning) - Optimizer-aware influence-based selection for inducing target capabilities.
- **What Makes Good Data for Alignment? A Comprehensive Study of Automatic Data Selection in Instruction Tuning** - [原文](https://openreview.net/forum?id=BTKAeLqLMw) · [阅读笔记](docs/reading-notes.md#what-makes-good-data-for-alignment-a-comprehensive-study-of-automatic-data-selection-in-instruction-tuning) - Studies automatic instruction-data selection for alignment.
- **Self-Alignment with Instruction Backtranslation** - [原文](https://openreview.net/forum?id=1oijHJBRsT) · [阅读笔记](docs/reading-notes.md#self-alignment-with-instruction-backtranslation) - Uses model-generated instructions from high-quality responses to improve instruction tuning data.
- **LIMA: Less Is More for Alignment** - [原文](https://arxiv.org/abs/2305.11206) · [阅读笔记](docs/reading-notes.md#lima-less-is-more-for-alignment) - Shows strong alignment behavior can emerge from a small carefully curated supervised fine-tuning dataset.

## Data Selection

- **Data Shapley: Equitable Valuation of Data for Machine Learning** - [原文](https://arxiv.org/abs/1904.02868) · [阅读笔记](docs/reading-notes.md#data-shapley-equitable-valuation-of-data-for-machine-learning) - Shapley-value framework for assigning value to individual training examples.
- **Estimating Training Data Influence by Tracing Gradient Descent** - [原文](https://proceedings.neurips.cc/paper/2020/hash/e6385d39ec9394f2f3a354d9d2b88eec-Abstract.html) · [阅读笔记](docs/reading-notes.md#estimating-training-data-influence-by-tracing-gradient-descent) - TracIn estimates example influence using checkpoints and gradient information.
- **Data Valuation Using Reinforcement Learning** - [原文](https://arxiv.org/abs/1909.11671) · [阅读笔记](docs/reading-notes.md#data-valuation-using-reinforcement-learning) - Learns data valuation policies for selecting beneficial samples.
- **Datamodels: Predicting Predictions from Training Data** - [原文](https://arxiv.org/abs/2202.00622) · [阅读笔记](docs/reading-notes.md#datamodels-predicting-predictions-from-training-data) - Models how training subsets affect predictions and supports dataset debugging.
- [LESS](https://github.com/princeton-nlp/LESS) - Codebase for influence-based targeted instruction data selection.
- [pyDVL](https://pydvl.org/stable/value/) - Python library for data valuation methods and workflows.

## Quality Evaluation Metrics

- **Evaluating Neural Toxic Degeneration in Language Models** - [原文](https://arxiv.org/abs/2009.11462) · [阅读笔记](docs/reading-notes.md#evaluating-neural-toxic-degeneration-in-language-models) - Introduces RealToxicityPrompts for measuring toxic generations and evaluating detoxification behavior.
- **ToxiGen: A Large-Scale Machine-Generated Dataset for Adversarial and Implicit Hate Speech Detection** - [原文](https://arxiv.org/abs/2203.09509) · [阅读笔记](docs/reading-notes.md#toxigen-a-large-scale-machine-generated-dataset-for-adversarial-and-implicit-hate-speech-detection) - Adversarial toxicity benchmark targeting implicit hate speech and spurious identity correlations.
- **Detoxifying Language Models Risks Marginalizing Minority Voices** - [原文](https://arxiv.org/abs/2104.06390) · [阅读笔记](docs/reading-notes.md#detoxifying-language-models-risks-marginalizing-minority-voices) - Shows that toxicity correction can harm utility for marginalized dialects and identity mentions.
- **TRUE: Re-evaluating Factual Consistency Evaluation** - [原文](https://arxiv.org/abs/2204.04991) · [阅读笔记](docs/reading-notes.md#true-re-evaluating-factual-consistency-evaluation) - Standardized meta-evaluation of factual and semantic consistency metrics across grounded generation tasks.
- **SelfCheckGPT: Zero-Resource Black-Box Hallucination Detection for Generative Large Language Models** - [原文](https://arxiv.org/abs/2303.08896) · [阅读笔记](docs/reading-notes.md#selfcheckgpt-zero-resource-black-box-hallucination-detection-for-generative-large-language-models) - Uses cross-sample agreement as a semantic consistency signal for hallucination detection.
- **G-Eval: NLG Evaluation using GPT-4 with Better Human Alignment** - [原文](https://arxiv.org/abs/2303.16634) · [阅读笔记](docs/reading-notes.md#g-eval-nlg-evaluation-using-gpt-4-with-better-human-alignment) - LLM-as-judge framework for evaluating generated text quality with natural-language rubrics.
- **Textbooks Are All You Need** - [原文](https://arxiv.org/abs/2306.11644) · [阅读笔记](docs/reading-notes.md#textbooks-are-all-you-need) - Demonstrates textbook-quality and knowledge-dense data as a strong signal for data-efficient model training.
- **The FineWeb Datasets: Decanting the Web for the Finest Text Data at Scale** - [原文](https://arxiv.org/abs/2406.17557) · [阅读笔记](docs/reading-notes.md#the-fineweb-datasets-decanting-the-web-for-the-finest-text-data-at-scale) - Includes FineWeb-Edu, an educational-quality filter that operationalizes knowledge density and learning value.
- **QuRating: Selecting High-Quality Data for Training Language Models** - [原文](https://arxiv.org/abs/2402.09739) · [阅读笔记](docs/reading-notes.md#qurating-selecting-high-quality-data-for-training-language-models) - Uses LLM-based ratings for educational value, expertise, writing style, and factual content as quality metrics.

## Filtering, Cleaning, and Deduplication

- **Data-Juicer: A One-Stop Data Processing System for Large Language Models** - [原文](https://arxiv.org/abs/2309.02033) · [阅读笔记](docs/reading-notes.md#data-juicer-a-one-stop-data-processing-system-for-large-language-models) - System for scalable LLM data processing, analysis, and data recipe exploration.
- **Data-Juicer 2.0: Cloud-Scale Adaptive Data Processing for and with Foundation Models** - [原文](https://proceedings.neurips.cc/paper_files/paper/2025/file/76dbd7e897be2eb883ede598b91270fb-Paper-Datasets_and_Benchmarks_Track.pdf) · [阅读笔记](docs/reading-notes.md#data-juicer-2-0-cloud-scale-adaptive-data-processing-for-and-with-foundation-models) - Extends data processing to multimodal and cloud-scale pipelines.
- **Deduplicating Training Data Makes Language Models Better** - [原文](https://arxiv.org/abs/2107.06499) · [阅读笔记](docs/reading-notes.md#deduplicating-training-data-makes-language-models-better) - Studies exact and near-deduplication effects on language modeling.
- **SemDeDup: Data-Efficient Learning at Web-Scale Through Semantic Deduplication** - [原文](https://arxiv.org/abs/2303.09540) · [阅读笔记](docs/reading-notes.md#semdedup-data-efficient-learning-at-web-scale-through-semantic-deduplication) - Semantic deduplication method for reducing redundancy while preserving performance.
- **CCNet: Extracting High Quality Monolingual Datasets from Web Crawl Data** - [原文](https://arxiv.org/abs/1911.00359) · [阅读笔记](docs/reading-notes.md#ccnet-extracting-high-quality-monolingual-datasets-from-web-crawl-data) - Classic Common Crawl filtering pipeline for language-model corpora.
- [deduplicate-text-datasets](https://github.com/google-research/deduplicate-text-datasets) - Official code for exact-substring deduplication from "Deduplicating Training Data Makes Language Models Better".

## Synthetic Data Generation and Curation

- **Self-Instruct: Aligning Language Models with Self-Generated Instructions** - [原文](https://arxiv.org/abs/2212.10560) · [阅读笔记](docs/reading-notes.md#self-instruct-aligning-language-models-with-self-generated-instructions) - Bootstraps instruction-following data from model-generated instructions.
- **Evol-Instruct** - [原文](https://arxiv.org/abs/2304.12244) · [阅读笔记](docs/reading-notes.md#evol-instruct) - Evolves instruction data to increase complexity and diversity.
- **WizardLM** - [原文](https://arxiv.org/abs/2304.12244) · [阅读笔记](docs/reading-notes.md#wizardlm) - Uses evolved instructions to improve instruction-following models.
- **Orca: Progressive Learning from Complex Explanation Traces of GPT-4** - [原文](https://arxiv.org/abs/2306.02707) · [阅读笔记](docs/reading-notes.md#orca-progressive-learning-from-complex-explanation-traces-of-gpt-4) - Uses explanation-rich synthetic data for imitation learning.
- **Phi-1: Textbooks Are All You Need** - [原文](https://arxiv.org/abs/2306.11644) · [阅读笔记](docs/reading-notes.md#phi-1-textbooks-are-all-you-need) - Demonstrates the power of high-quality synthetic textbook-style data for code models.
- **LLMs-Driven Synthetic Data Generation, Curation, and Evaluation** - [原文](https://arxiv.org/abs/2406.15126) · [阅读笔记](docs/reading-notes.md#llms-driven-synthetic-data-generation-curation-and-evaluation) - Survey of synthetic data generation and evaluation pipelines.

## Multimodal Data Quality

- **DataComp: In Search of the Next Generation of Multimodal Datasets** - [原文](https://arxiv.org/abs/2304.14108) · [阅读笔记](docs/reading-notes.md#datacomp-in-search-of-the-next-generation-of-multimodal-datasets) - Benchmark for dataset filtering strategies in multimodal contrastive learning.
- **LAION-5B: An Open Large-Scale Dataset for Training Next Generation Image-Text Models** - [原文](https://arxiv.org/abs/2210.08402) · [阅读笔记](docs/reading-notes.md#laion-5b-an-open-large-scale-dataset-for-training-next-generation-image-text-models) - Large-scale image-text dataset with filtering and safety-related documentation.
- **CLIPScore: A Reference-free Evaluation Metric for Image Captioning** - [原文](https://arxiv.org/abs/2104.08718) · [阅读笔记](docs/reading-notes.md#clipscore-a-reference-free-evaluation-metric-for-image-captioning) - Uses image-text alignment as a quality signal.
- **TIVE: Less is More: High-Value Data Selection for Visual Instruction Tuning** - [原文](https://github.com/simplelifetime/TIVE) · [阅读笔记](docs/reading-notes.md#tive-less-is-more-high-value-data-selection-for-visual-instruction-tuning) - Studies redundancy and data selection in visual instruction data.
- **A Comprehensive Study of Multimodal Large Language Models for Image Quality Assessment** - [原文](https://arxiv.org/abs/2403.10854) · [阅读笔记](docs/reading-notes.md#a-comprehensive-study-of-multimodal-large-language-models-for-image-quality-assessment) - Evaluates multimodal LLMs as image quality assessors.

## RAG Data Quality

- **RAGAS: Automated Evaluation of Retrieval Augmented Generation** - [原文](https://arxiv.org/abs/2309.15217) · [阅读笔记](docs/reading-notes.md#ragas-automated-evaluation-of-retrieval-augmented-generation) - Evaluation framework for context relevance, faithfulness, answer correctness, and related RAG metrics.
- **ARES: An Automated Evaluation Framework for Retrieval-Augmented Generation Systems** - [原文](https://arxiv.org/abs/2311.09476) · [阅读笔记](docs/reading-notes.md#ares-an-automated-evaluation-framework-for-retrieval-augmented-generation-systems) - Automated RAG evaluation with synthetic queries and judge models.
- **Corrective Retrieval Augmented Generation** - [原文](https://arxiv.org/abs/2401.15884) · [阅读笔记](docs/reading-notes.md#corrective-retrieval-augmented-generation) - Adds retrieved-document quality checks and correction behavior.
- **Contextual Retrieval** - [原文](https://www.anthropic.com/engineering/contextual-retrieval) · [阅读笔记](docs/reading-notes.md#contextual-retrieval) - Enriches chunks with context before indexing to reduce retrieval failures.
- **RAGChecker** - [原文](https://arxiv.org/abs/2408.08067) · [阅读笔记](docs/reading-notes.md#ragchecker) - Fine-grained diagnostic framework for RAG systems.

## Benchmark Contamination and Evaluation Reliability

- **Benchmark Data Contamination of Large Language Models: A Survey** - [原文](https://arxiv.org/abs/2406.04244) · [阅读笔记](docs/reading-notes.md#benchmark-data-contamination-of-large-language-models-a-survey) - Reviews benchmark leakage, detection, and mitigation for LLM evaluation.
- **Data Contamination: From Memorization to Exploitation** - [原文](https://arxiv.org/abs/2312.08242) · [阅读笔记](docs/reading-notes.md#data-contamination-from-memorization-to-exploitation) - Studies contamination effects and evaluation reliability.
- **Detecting Pretraining Data from Large Language Models** - [原文](https://arxiv.org/abs/2310.16789) · [阅读笔记](docs/reading-notes.md#detecting-pretraining-data-from-large-language-models) - Detects whether text was likely present in model pretraining data.
- **The WMDP Benchmark: Measuring and Reducing Malicious Use With Unlearning** - [原文](https://arxiv.org/abs/2403.03218) · [阅读笔记](docs/reading-notes.md#the-wmdp-benchmark-measuring-and-reducing-malicious-use-with-unlearning) - Useful for safety-sensitive data filtering and unlearning-oriented evaluation.

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

- **DataComp-LM** - [原文](https://github.com/mlfoundations/dclm) · [阅读笔记](docs/reading-notes.md#datacomp-lm) - Benchmark and corpus for language-model data curation experiments.
- [FineWeb](https://huggingface.co/datasets/HuggingFaceFW/fineweb) - Large-scale filtered web corpus.
- [FineWeb-Edu](https://huggingface.co/datasets/HuggingFaceFW/fineweb-edu) - Educational-quality subset derived from FineWeb.
- [Dolma](https://huggingface.co/datasets/allenai/dolma) - Open pretraining corpus from AI2.
- [RedPajama-Data](https://github.com/togethercomputer/RedPajama-Data) - Open LLM pretraining data recipes and metadata.
- **The Pile** - [原文](https://arxiv.org/abs/2101.00027) · [阅读笔记](docs/reading-notes.md#the-pile) - Large open text corpus with diverse sources.
- [OpenWebText](https://skylion007.github.io/OpenWebTextCorpus/) - Open reproduction-style web text corpus.

## Research Roadmap

### 1. Scaling Laws

- Study pretraining scaling laws under data quality, data repetition, data mixture, and data scarcity.
- Extend scaling analysis to post-training, including SFT, DPO/RLHF, reward model overoptimization, and RL reasoning.
- Report compute-normalized and data-normalized gains, not only final benchmark scores.

### 2. Data Selection

- Compare rule-based filters, model-based filters, influence methods, and LLM judges.
- Separate intrinsic quality, target-task influence, domain coverage, and diversity.
- Treat data mixture optimization and curriculum scheduling as first-class research objects.

### 3. Quality Evaluation Metrics

- Build task-aware quality metrics instead of relying only on generic heuristics.
- Separate intrinsic data quality from model-, objective-, and evaluation-dependent utility.
- Measure toxicity detection and correction, semantic consistency, factuality, knowledge density, diversity, safety, freshness, and provenance.

### 4. Evaluation Protocols

- Use controlled ablations that isolate one data operation at a time.
- Report compute-normalized gains, not only final model scores.
- Evaluate side effects: bias, language/domain coverage, memorization, and safety.

### 5. Data Improvement Methods

- Study data rewriting, detoxification, consistency repair, knowledge densification, and answer correction, not only removal.
- Pair every improvement operation with regression tests for robustness, diversity, and safety.

### 6. Reproducibility

- Version datasets, filters, thresholds, prompts, and model checkpoints.
- Publish metadata schemas and data cards.
- Prefer executable data recipes over prose-only descriptions.

### 7. Open Problems

- How can we predict returns from better data using scaling laws before training expensive models?
- Do pretraining and post-training share the same data-quality scaling behavior?
- Which data selection methods transfer across target capabilities, domains, and languages?
- How can we evaluate data quality without training expensive proxy models?
- Can quality metrics generalize across domains, languages, and modalities?
- When does filtering improve benchmark scores while harming diversity, robustness, or minority-language performance?
- How should we evaluate generated, detoxified, consistency-repaired, or knowledge-densified data when references are unavailable?
- Can data quality improvement be made interactive, auditable, and human-controllable?

## Contribution Guide

Contributions are welcome. Please see [CONTRIBUTING.md](CONTRIBUTING.md).

Every paper should have one primary taxonomy category and optional cross-tags. Use [docs/taxonomy.md](docs/taxonomy.md) to decide whether the entry belongs under Scaling Laws, Data Selection, Quality Evaluation Metrics, or a supporting section.

When adding a paper, prefer this format:

```markdown
- **Paper Title** - [原文](paper-url) · [阅读笔记](docs/reading-notes.md#paper-title-anchor) - One-sentence summary focused on data quality evaluation or improvement. Optional: [Code](code-url), [Dataset](dataset-url).
```

## Related Awesome Lists

- [Awesome RAG](https://github.com/Danielskry/Awesome-RAG)
- [Awesome Data Quality](https://github.com/MigoXLab/awesome-data-quality)
- [Data-Centric AI](https://github.com/daochenzha/data-centric-ai)
- [Awesome Data Valuation](https://github.com/daviddao/awesome-data-valuation)

## License

This repository is released under the [CC0 1.0 Universal](LICENSE) public domain dedication.
