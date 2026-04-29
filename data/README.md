---
configs:
  - config_name: subset2_type4
    data_files:
    - split: test
      path: subset2_type4.csv

  - config_name: subset2_type5a
    data_files:
    - split: test
      path: subset2_type5a.csv

  - config_name: subset2_type5p
    data_files:
    - split: test
      path: subset2_type5p.csv

  - config_name: subset3_type4
    data_files:
    - split: test
      path: subset3_type4.csv

  - config_name: subset3_type5a
    data_files:
    - split: test
      path: subset3_type5a.csv

  - config_name: subset3_type5p
    data_files:
    - split: test
      path: subset3_type5p.csv

  - config_name: subset4_type4
    data_files:
    - split: test
      path: subset4_type4.csv

  - config_name: subset4_type5a
    data_files:
    - split: test
      path: subset4_type5a.csv

  - config_name: subset4_type5p
    data_files:
    - split: test
      path: subset4_type5p.csv
---

# Proviso-NLI Dataset

A Natural Language Inference (NLI) dataset with examples constructed using different trigger types.

## Dataset Summary

This dataset contains Natural Language Inference examples across three subsets (2, 3, and 4) with three different trigger types:
- **Type 4**: Possessive triggers
- **Type 5a**: Again triggers  
- **Type 5p**: Possessive triggers

The dataset is designed for evaluating NLI models.

## Dataset Structure

### Data Fields

- `premise` (string): The premise sentence
- `hypothesis` (string): The hypothesis sentence
- `gold_label` (string): Gold standard label (E, C, or N for Entailment, Contradiction, Neutral)
- `trigger` (string): The type of trigger used (e.g., "possessive", "again")
- `SetID` (int): Set identifier
- `UID` (string): Unique identifier
- `trigger_words` (string): The specific trigger words in the example
- `premise_type` (string): The type of premise (e.g., "Attitude Premise", "Conjunction Premise")

### Splits

The dataset is organized into 9 subsets:

| Subset | Type | Description |
|--------|------|-------------|
| `subset2_type4` | Possessive | Subset 2 - Possessive triggers |
| `subset2_type5a` | Again | Subset 2 - Again triggers |
| `subset2_type5p` | Possessive | Subset 2 - Possessive triggers |
| `subset3_type4` | Possessive | Subset 3 - Possessive triggers |
| `subset3_type5a` | Again | Subset 3 - Again triggers |
| `subset3_type5p` | Possessive | Subset 3 - Possessive triggers |
| `subset4_type4` | Possessive | Subset 4 - Possessive triggers |
| `subset4_type5a` | Again | Subset 4 - Again triggers |
| `subset4_type5p` | Possessive | Subset 4 - Possessive triggers |

## Loading the Dataset

```python
from datasets import load_dataset

# Load a specific subset
dataset = load_dataset("ConditionalNLI/PROVISER", name="subset2_type4")

# Load all subsets
datasets = load_dataset("ConditionalNLI/PROVISER")
```
