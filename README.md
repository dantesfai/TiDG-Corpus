# Tigrinya Text Categorization Dataset

This repository hosts a clean, labeled dataset of Tigrinya text documents for multi-class text classification. The dataset is preprocessed and structured to support research in natural language processing (NLP) for low-resource languages.

## Dataset Description

- **Language**: Tigrinya (with transliteration using the SERA standard)
- **Total Samples**: 8,067 text documents
- **Split**:
  - Train: 80% (6,453 samples)
  - Validation: 10% (807 samples)
  - Test: 10% (807 samples)
- **Format**: CSV files (`train.csv`, `val.csv`, `test.csv`)
- **Columns**:
  - `cleaned_text`: Preprocessed and normalized Tigrinya text
  - `transliteration`: SERA transliteration of the original text
  - `label`: Numeric label corresponding to one of the categories

## Categories

The dataset includes 7 classes labeled from 0 to 6:

| Label | Category            |
|-------|---------------------|
| 0     | Culture             |
| 1     | Economy             |
| 2     | Health              |
| 3     | Politics            |
| 4     | Religion            |
| 5     | scitech             |
| 6     | Sport               |

A `label_encoder.pkl` file is provided to map between category names and numeric labels.

## Usage

```python
import pandas as pd
import pickle

# Load dataset
train_df = pd.read_csv("data/train.csv")
val_df = pd.read_csv("data/val.csv")
test_df = pd.read_csv("data/test.csv")

# Load label encoder
with open("data/label_encoder.pkl", "rb") as f:
    label_encoder = pickle.load(f)

# Decode label example
decoded_label = label_encoder.inverse_transform([3])[0]  # 'Culture'


## License
This dataset is made available for academic and non-commercial use under the MIT License.

## Citation
If you use this dataset for research or publication, please cite or reference this repository.

## Acknowledgments
This dataset was curated and cleaned to support research in low-resource language NLP, particularly for the Tigrinya language.