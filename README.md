## ICTer Workshop – Sinhala Phrases Dataset (Transformers)

This repository contains a large Sinhala text corpus in `Data/sinhala_phrases.txt`, intended for use in experiments and tutorials on modern NLP with transformer models (e.g. BERT, mBERT, XLM-R, encoder–decoder architectures).

### Repository contents

- **`Data/sinhala_phrases.txt`**: A plain-text file (tracked via Git LFS) with Sinhala sentences and paragraphs, including:
  - News-style articles and reports
  - Narrative and descriptive passages
  - Mixed-length sentences suitable for language modeling and sequence-to-sequence tasks
- **`.gitattributes`**: Configures Git LFS to track `Data/sinhala_phrases.txt`.
- **`.gitignore`**: Standard ignores for macOS, Python, virtual environments, IDE metadata, and notebook checkpoints.

### Use cases

- **Language modeling**: Train transformer-based language models on Sinhala text.
- **Sentence/paragraph classification**: Build classifiers for topics, sentiment, or other labels once annotations are added.
- **Sequence-to-sequence tasks**: Use as source data for summarization, translation, or style transfer after aligning with appropriate targets.
- **Tokenization experiments**: Explore subword tokenizers (BPE, SentencePiece) specialized for Sinhala.

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
data_path = "Data/sinhala_phrases.txt"

with open(data_path, "r", encoding="utf-8") as f:
    lines = f.readlines()

print("Total lines:", len(lines))
print("Sample:", lines[0:5])
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


