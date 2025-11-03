# Adversarial NLP Attacks with TextAttack on Rotten Tomatoes Reviews

This notebook demonstrates how to train, evaluate, and adversarially attack a transformer model for text classification using the TextAttack library. Using the Rotten Tomatoes dataset, it covers clean training, attack evaluation, and adversarial training for robustness.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Tech Stack](#tech-stack)
- [Dataset](#dataset)
- [Workflow](#workflow)
- [Models & Training](#models--training)
- [Adversarial Attack Methods](#adversarial-attack-methods)
- [Robustness Evaluation](#robustness-evaluation)
- [Getting Started](#getting-started)
- [References](#references)

---

## Project Overview

This project uses TextAttack to highlight vulnerabilities in NLP models to adversarial word-level attacks. With a transformer model trained on Rotten Tomatoes movie reviews, the notebook demonstrates how attacks severely degrade classification accuracy and how adversarial training improves resilience.

---

## Tech Stack

- Python (3.11+)
- HuggingFace Transformers
- TextAttack
- PyTorch
- NLTK, pandas, matplotlib

---

## Dataset

- **Rotten Tomatoes Movie Reviews**: Sentiment analysis data, loaded via HuggingFace Datasets, with train, validation, and test splits.

---

## Workflow

1. **Install dependencies**: TextAttack, transformers, and related libraries.
2. **Train model**: DistilBERT transformer for binary sentiment classification.
3. **Evaluate model**: Check accuracy on the test set.
4. **Attack model**: Use TextFooler to generate adversarial samples and measure the drop in accuracy.
5. **Adversarial training**: Fine-tune model using adversarial examples to increase robustness.
6. **Re-evaluate robustness**: Attack the robust model and compare metrics.

---

## Models & Training

- Model: `distilbert-base-uncased` fine-tuned for 2-class sentiment.
- Training configuration: 2 epochs, batch size 128, max length 64.
- Achieved clean test accuracy: 86%
- Adversarial training procedures included for robustness analysis.

---

## Adversarial Attack Methods

- **TextFooler**: Generates adversarial examples by substituting words while maintaining sentence meaning.
- Attack results: Accuracy under attack dropped to 2%, with a 97.67% attack success rate (only 2 out of 100 were robust).

---

## Robustness Evaluation

- Adversarial training improved resistance somewhat, though attacks continued to be effective.
- Metrics: After adversarial training, clean accuracy was ~80% and adversarial accuracy improved but attacks still succeeded on many samples.
- The workflow demonstrates steps to iteratively improve model robustness.

---

## Getting Started

### Installation

pip install textattack transformers torch datasets nltk pandas matplotlib

### Usage

- Run each notebook cell in order.
- Follow code comments for attack and robustness evaluations.
- Adapt training or attack parameters to fit runtime constraints.

---

## References

- [TextAttack Documentation](https://textattack.readthedocs.io/)
- [HuggingFace Datasets](https://huggingface.co/datasets)
- [DistilBERT](https://huggingface.co/distilbert-base-uncased)

---
