# Metamorphic Testing for Sentiment Analysis Models

This repository contains the implementation and experimental results for the paper:

**“Metamorphic Testing for Evaluating Robustness of Sentiment Analysis Models”**

## Overview

The project evaluates the robustness of a pretrained sentiment analysis model using metamorphic testing. Instead of relying only on traditional metrics such as accuracy, the experiment analyzes how model predictions behave under different linguistic transformations.

The study focuses on identifying whether the model:
- maintains consistent predictions for meaning-preserving transformations
- correctly changes predictions when semantic meaning changes

---

## Transformations Used

The following text transformations are evaluated:

1. **Synonym Replacement**
   - replaces words with semantically similar alternatives

2. **Typo Injection**
   - introduces small spelling mistakes

3. **Word-Order Variation**
   - modifies word order while preserving meaning

4. **Negation**
   - inserts negation terms to reverse sentiment

---

## Model

The experiment uses a pretrained DistilBERT-based sentiment analysis model from the Hugging Face Transformers library.

Model:
- `distilbert-base-uncased-finetuned-sst-2-english`

---

## Evaluation Metrics

The following robustness metrics are computed:

- **Consistency Score**
  - percentage of unchanged predictions for invariance transformations

- **Flip Accuracy**
  - percentage of correctly flipped predictions for negation

- **Confidence Change**
  - difference in confidence between original and transformed inputs

---

## Repository Structure

```text
.
├── notebooks/
│   └── metamorphic_testing_experiment.ipynb
│
├── results/
│   ├── metamorphic_testing_summary.csv
│   ├── metamorphic_testing_detailed_results.csv
│   ├── sample_violation_examples.csv
│   ├── top_violation_examples.csv
│   ├── figure_1_confidence_comparison.png
│   ├── figure_2_confidence_simple.png
│   ├── figure_3_confidence_change.png
│   ├── figure_4_pass_vs_violation.png
│   └── figure_5_robustness.png
│
└── README.md
```

---

## Requirements

Install dependencies:

```bash
pip install transformers datasets pandas matplotlib torch
```

---

## Running the Experiment

Run the notebook:

```bash
jupyter notebook
```

Open:

```text
notebooks/metamorphic_testing_experiment.ipynb
```

The notebook:
- loads the dataset
- applies transformations
- runs model inference
- computes robustness metrics
- generates figures and tables

---

## Results

The experiment demonstrates that:
- the model performs well under synonym replacement and minor word-order changes
- typographical errors reduce robustness
- negation remains a major challenge for sentiment analysis models

The generated figures and tables are available in the `results/` directory.

---

## References

Key references used in this work include:
- Metamorphic Testing
- METTLE
- DeepGauge
- CheckList
- NLP robustness and adversarial testing literature

Please refer to the paper for the complete reference list.
