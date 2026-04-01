# ai-reliability-study

# AI Reliability Under Data Noise: A Real-World Evaluation Study

## Overview

Modern AI systems are widely deployed in real-world decision-making tasks such as hiring, finance, and risk assessment. However, these systems often operate under imperfect conditions, including noisy or inconsistent data.

This project investigates how machine learning models behave under increasing levels of label noise, simulating real-world data imperfections such as annotation errors and human disagreement.

---

## Objective

The goal of this study is to evaluate:

- How model performance changes under noisy data
- Whether performance degradation is linear or nonlinear
- How errors are distributed across different groups and features
- What this implies for real-world AI reliability

---

## Methodology

### Dataset
- Adult Income Dataset (UCI)
- Task: Predict whether income exceeds $50K/year

### Model
- Random Forest Classifier (baseline)

### Experiments
1. Train model on clean data
2. Introduce controlled label noise (0% → 30%)
3. Measure performance at each noise level
4. Analyze prediction errors and failure patterns

---

## Results

### Performance vs Noise

- Accuracy decreases as noise increases
- Degradation is **nonlinear**, with sharper decline beyond 20% noise

### Key Observation

> Model performance remains relatively stable under low noise but collapses more rapidly at higher noise levels.

---

## Error Analysis

The model's errors are not random and reveal structured weaknesses:

### Class Imbalance
- Lower recall for high-income class (>50K)
- Indicates difficulty identifying minority class

### Demographic Patterns
- Errors are disproportionately concentrated in specific groups

### Feature-Level Failures
- Certain education levels show higher error rates
- Suggests model struggles with specific feature distributions

---

## Key Insights

1. **Data quality is critical** — even moderate noise reduces performance
2. **Model degradation is nonlinear**, indicating sensitivity thresholds
3. **Errors are structured, not random**, revealing bias and instability
4. **Minority classes are more vulnerable** to performance degradation

---

## Implications

These findings highlight the importance of:

- Robust data pipelines
- Careful evaluation beyond accuracy
- Monitoring model behavior under real-world conditions

AI systems deployed in production must account for data imperfections to ensure fairness, reliability, and safety.

---

## Project Structure
ai-reliability-study/
│── data/
│── notebooks/
│ └── 01_baseline_model.ipynb
│── src/
│── results/
│── reports/
│── README.md
│── requirements.txt


---

## Future Work

- Add bias/fairness metrics
- Evaluate different model types
- Apply noise-robust training methods
- Extend analysis to other datasets

---

## Author

Built as part of a research-focused portfolio project demonstrating applied machine learning, experimental design, and system-level analysis.

