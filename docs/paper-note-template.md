# Paper Reading Note Template

Use this template for high-quality paper notes in this repository. It is adapted from the `paper-reader` workflow and customized for data quality evaluation and improvement research.

Every completed note should answer four questions:

- What problem does this paper solve?
- What is the exact method, metric, dataset, or scaling claim?
- How does it change our understanding of data quality?
- What should a future researcher trust, question, reproduce, or build on?

````markdown
<a id="{stable-paper-anchor}"></a>
## {Paper Title}

- Primary taxonomy category: {A1-A5 / B1-B6 / C1-C6}
- Cross-tags: {optional: A3, B2, C3, C5, ...}
- README subsection: {README section or subsection}
- Original: {paper URL}
- Code: {code URL or N/A}
- Dataset: {dataset URL or N/A}
- Year / Venue: {year, venue}
- Authors: {authors}
- Reading status: {skimmed / carefully read / reproduced / used in experiments}
- README summary: {one-sentence summary used in README}

### 1. One-Sentence Takeaway

> {One sentence explaining the paper's core contribution and why it matters for data quality.}

### 2. Research Question

- **Problem**: {What data-quality problem is the paper trying to solve?}
- **Setting**: {pretraining / post-training / RAG / multimodal / benchmark / classical ML / other}
- **Why it matters**: {What breaks if this problem is not solved?}
- **Main claim**: {The paper's strongest empirical or theoretical claim.}

### 3. Taxonomy Placement

| Field | Answer |
| --- | --- |
| Main branch | {Scaling Laws / Data Selection and Improvement / Quality Evaluation Metrics} |
| Subcategory | {A1-A5 / B1-B6 / C1-C6 with name} |
| Data object | {document / token / example / instruction / preference pair / chunk / benchmark item / image-text pair / other} |
| Quality signal | {toxicity / semantic consistency / knowledge density / diversity / influence / deduplication / contamination / other} |
| Data operation | {measure / select / filter / deduplicate / repair / synthesize / mix / schedule / audit} |

### 4. Background and Motivation

- **Prior approach**: {What did previous work do?}
- **Limitation**: {What gap, failure mode, cost, or bias does this paper identify?}
- **Key intuition**: {The central idea behind the paper.}
- **Assumptions**: {Assumptions about data, model, annotators, metric, scale, or benchmark.}

### 5. Method / Metric / System

#### 5.1 Method Overview

{Describe the method in 5-10 precise bullets. Avoid vague summaries.}

- Input:
- Output:
- Core algorithm / metric:
- Training or evaluation loop:
- Model or judge used:
- Human annotation, if any:
- Thresholds, prompts, or scoring rules:

#### 5.2 Key Equations or Scoring Rules

List every important equation, objective, score, or decision rule.

##### Equation / Score 1: {name}

$$
{latex}
$$

**Meaning**: {What the equation measures or optimizes.}

**Symbols**:
- ${symbol}$: {meaning}
- ${symbol}$: {meaning}

##### Equation / Score 2: {name}

$$
{latex}
$$

**Meaning**:

**Symbols**:

#### 5.3 Algorithm Details

```text
Input:
Steps:
1.
2.
3.
Output:
````

### 6. Data and Experimental Setup

| Item | Details |
| --- | --- |
| Training data | {datasets, scale, domains, languages, filtering state} |
| Evaluation data | {benchmarks, held-out sets, human eval, contamination checks} |
| Models | {model family, size, checkpoints, reward model, judge model} |
| Baselines | {baselines compared against} |
| Metrics | {metrics and what each measures} |
| Compute | {hardware, budget, training tokens, API cost, if reported} |
| Reproducibility assets | {code, data recipe, prompts, checkpoints, configs} |

### 7. Figures, Tables, and Evidence

Record every important Figure and Table. For a full paper read, do not skip figures, formulas, or tables.

#### Figure Checklist

| Figure | What It Shows | Key Takeaway | Data-Quality Relevance |
| --- | --- | --- | --- |
| Figure 1 | {overview} | {takeaway} | {why it matters} |
| Figure 2 | {results/analysis} | {takeaway} | {why it matters} |

#### Table Checklist

| Table | What It Reports | Best / Worst Result | Interpretation |
| --- | --- | --- | --- |
| Table 1 | {main results} | {numbers} | {meaning} |
| Table 2 | {ablation/error analysis} | {numbers} | {meaning} |

### 8. Main Results

- **Result 1**: {claim + evidence + number if available}
- **Result 2**: {claim + evidence + number if available}
- **Result 3**: {claim + evidence + number if available}
- **Ablation insight**: {which component matters most?}
- **Negative result**: {what did not work, if reported?}

### 9. Data Quality Angle

#### 9.1 What Quality Means in This Paper

{Define the paper's implicit or explicit notion of quality.}

#### 9.2 Quality Signals

| Signal | How It Is Measured | Strength | Weakness |
| --- | --- | --- | --- |
| {signal} | {metric/judge/rule} | {why useful} | {failure mode} |

#### 9.3 Quality Improvement Operation

| Operation | Target Data | Expected Benefit | Possible Side Effect |
| --- | --- | --- | --- |
| {filter/select/repair/synthesize/mix} | {data type} | {benefit} | {risk} |

### 10. Critical Assessment

#### Strengths

1. {Strength with evidence.}
2. {Strength with evidence.}
3. {Strength with evidence.}

#### Limitations

1. {Limitation with consequence.}
2. {Limitation with consequence.}
3. {Limitation with consequence.}

#### Failure Modes and Risks

- **Metric gaming**:
- **Bias or coverage loss**:
- **Toxicity / safety regression**:
- **Data contamination**:
- **Overfitting to judge / benchmark**:
- **Generalization across domains or languages**:

### 11. Reproducibility Assessment

| Item | Status | Notes |
| --- | --- | --- |
| Code released | {yes/no/partial} | {link or limitation} |
| Data released | {yes/no/partial} | {link or limitation} |
| Data recipe released | {yes/no/partial} | {filters, prompts, thresholds} |
| Prompts / annotation guide released | {yes/no/partial} | {details} |
| Hyperparameters released | {yes/no/partial} | {details} |
| Compute reported | {yes/no/partial} | {details} |
| Contamination checks | {yes/no/partial} | {details} |

### 12. Relation to Other Papers

- **Builds on**:
  - {Paper}: {relationship}
- **Compared with**:
  - {Paper}: {difference}
- **Contradicts or complicates**:
  - {Paper}: {tension}
- **Should be read with**:
  - {Paper}: {reason}

### 13. Implications for Our Research

- **Useful idea to borrow**:
- **Potential baseline**:
- **Potential metric**:
- **Potential dataset or benchmark**:
- **Experiment we should run**:
- **Open question created by this paper**:

### 14. Open Questions

1. {Question}
2. {Question}
3. {Question}

### 15. Note Completion Checklist

- [ ] Original link is included.
- [ ] Reading note anchor is stable and matches the README link.
- [ ] Primary taxonomy category is filled.
- [ ] Cross-tags are filled when the paper spans multiple branches.
- [ ] All important equations or scoring rules are captured.
- [ ] All main figures are summarized.
- [ ] All main tables are summarized.
- [ ] Data, models, metrics, and baselines are recorded.
- [ ] Data-quality angle is explicit.
- [ ] Limitations and failure modes are explicit.
- [ ] Reproducibility status is assessed.
```

## Taxonomy Quick Reference

| Code | Meaning |
| --- | --- |
| A1 | Pretraining compute/token scaling |
| A2 | Data-constrained scaling |
| A3 | Data mixture and domain scaling |
| A4 | Downstream transfer scaling |
| A5 | Post-training and alignment scaling |
| B1 | Data valuation and influence |
| B2 | LLM pretraining data selection |
| B3 | Mixture optimization and curriculum |
| B4 | Instruction and alignment data selection |
| B5 | Synthetic and rewritten data selection |
| B6 | Filtering, cleaning, and deduplication |
| C1 | Toxicity, safety, and detoxification |
| C2 | Semantic and factual consistency |
| C3 | Knowledge density and educational value |
| C4 | Diversity, coverage, and representativeness |
| C5 | Contamination and evaluation reliability |
| C6 | Multimodal quality signals |
