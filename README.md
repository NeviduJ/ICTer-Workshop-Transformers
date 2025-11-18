## ICTer Workshop – Sinhala & Tamil Corpora for Transformers

This repository collects large Sinhala **and** Tamil text corpora (see the `Data/` directory) for transformer-based NLP experiments and tutorials (e.g. BERT, mBERT, XLM-R, encoder–decoder architectures).

### Repository contents

- **`Data/sinhala_phrases.txt`**: A plain-text file (tracked via Git LFS) with Sinhala sentences and paragraphs, including:
  - News-style articles and reports
  - Narrative and descriptive passages
  - Mixed-length sentences suitable for language modeling and sequence-to-sequence tasks
- **`Data/tamil_phrases_filtered.txt`** *(optional / filtered subset)*: Tamil phrases and paragraphs suitable for training Tamil-only or multilingual models. If you create additional Tamil datasets (e.g., `Data/tamil_phrases.txt`), store them here and consider tracking with Git LFS if they exceed 100 MB.
- **`Data/sinhala_phrases_filtered.txt`** *(optional / filtered subset)*: Example of a derived Sinhala file after preprocessing or filtering.
- **`.gitattributes`**: Configures Git LFS to track `Data/sinhala_phrases.txt`.
- **`.gitignore`**: Standard ignores for macOS, Python, virtual environments, IDE metadata, and notebook checkpoints.

### Use cases

- **Language modeling**: Train transformer-based language models on Sinhala, Tamil, or combined corpora.
- **Sentence/paragraph classification**: Build classifiers for topics, sentiment, or other labels once annotations are added.
- **Sequence-to-sequence tasks**: Use as source data for summarization, translation (Sinhala ↔ Tamil, Sinhala ↔ English, Tamil ↔ English), or style transfer after aligning with appropriate targets.
- **Tokenization experiments**: Explore subword tokenizers (BPE, SentencePiece) specialized for Sinhala and Tamil, jointly or separately.
- **Multilingual transfer**: Experiment with multilingual transformer fine-tuning using both corpora to test cross-lingual generalization.

### Getting started

1. **Clone the repository**

```bash
git clone https://github.com/NeviduJ/ICTer-Workshop-Transformers.git
cd ICTer-Workshop-Transformers
```

2. **Ensure Git LFS is installed**

If you have not already installed Git LFS:

```bash
git lfs install
```

Git LFS will automatically fetch `Data/sinhala_phrases.txt` when needed.

3. **Basic data loading example (Python)**

```python
from pathlib import Path

for lang_file in ["Data/sinhala_phrases.txt", "Data/tamil_phrases_filtered.txt"]:
    path = Path(lang_file)
    if not path.exists():
        print(f"{path} not found, skipping.")
        continue

    with path.open("r", encoding="utf-8") as f:
        lines = f.readlines()

    print(path.name, "lines:", len(lines))
    print("Sample:", lines[:3])
```

You can then wrap this in a PyTorch `Dataset`, a Hugging Face `datasets` loader, or any other framework of your choice.

### Suggested project structure (for future code)

If you extend this repo during the workshop, a simple structure might be:

- **`notebooks/`** – Exploratory notebooks for tokenization, training, and evaluation.
- **`src/`** – Reusable Python modules (data loading, model definitions, training loops).
- **`scripts/`** – Command-line entry points for training and inference.

This is only a suggestion; feel free to adapt it to your workflow.

### License and usage

Please ensure that any downstream use of this corpus complies with the original data source licenses and with your institutional or workshop guidelines. If you plan to redistribute models trained on this corpus, clearly document data provenance and any preprocessing steps you applied.


