This repository contains the **PROVISER** dataset and evaluation code for studying the *proviso problem* which is an unresolved issue in pragmatics where presuppositions in conditional sentences diverge between theoretical predictions and human interpretations.

Given a sentence like:

> *If Theo hates sonnets, so does his wife.*

- **Formal semantic theories** predict a *conditional* presupposition: *If Theo hates sonnets, then Theo has a wife.*
- **Human speakers** typically accommodate an *unconditional* presupposition: *Theo has a wife.*

We reformulate this phenomenon as a **Natural Language Inference (NLI)** task and evaluate RoBERTa, DeBERTa, LLaMA, and Gemma using classification accuracy and explainability analyses (Integrated Gradients, attention).

---

## Dataset

The PROVISER dataset contains approximately **8,500 NLI sentence pairs** with controlled linguistic variations, organized into four subsets:

| Subset | Description |
|--------|-------------|
| 1. Original Sentences | 900 baseline NLI pairs from CONFER |
| 2. Structural Variation | Conjunction, disjunction, and belief-embedding modifications |
| 3. Trigger-Hypothesis Relatedness | Three levels of semantic relatedness between trigger and hypothesis |
| 4. Context-Trigger Relatedness | Logically related vs. unrelated antecedent–consequent pairs |

Each example includes both a **human label** and a **theory-based label**, enabling direct comparison of model alignment with human judgments versus formal semantic predictions.

### Download

The dataset is available on Hugging Face:

```python
from datasets import load_dataset
dataset = load_dataset("ConditionalNLI/PROVISER")
```

Or download directly from the [Hugging Face page](https://huggingface.co/datasets/ConditionalNLI/PROVISER).

---

PROVISER is built on top of **CONFER**, a dataset for evaluating NLI models on conditional inference and presupposition. The original 900 sentence pairs used as the basis for this dataset come from CONFER.

- CONFER Repository: [https://github.com/ConditionalNLI/CONFER](https://github.com/Conditional-NLI/CONFER)

---

## Models and Setup

All models were fine-tuned on the CONFER training set for one epoch (learning rate `5e-5`):

- `roberta-large-mnli`
- `deberta-large-mnli`
- `meta-llama/Llama-3.2-1B`
- `google/gemma-3-1b`

Zero-shot evaluation was also conducted for all four models prior to fine-tuning.


---

## Citation

If you use PROVISER in your work, please cite:

```bibtex
@inproceedings{azin-etal-2026-do,
  title = {Do Language Models Know Theo Has a Wife? Investigating the Proviso Problem},
  author = {Azin, Tara and Dumitrescu, Daniel and Inkpen, Diana and Singh, Raj},
  booktitle = {Proceedings of the Fifteenth Language Resources and Evaluation Conference (LREC 2026)},
  month = {May},
  year = {2026},
  pages = {1977--1988},
  address = {Palma, Mallorca, Spain},
  publisher = {European Language Resources Association (ELRA)},
  doi = {10.63317/547c6dmqaxgx},
}
```
