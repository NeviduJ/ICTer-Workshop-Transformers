## ICTer Workshop – Sinhala & Tamil Corpora for Transformers

This repository collects large Sinhala **and** Tamil text corpora (see the `Data/` directory) and a set of teaching notebooks used in an ICTer workshop on **demystifying the GPT core** and **building a transformer-style language model from scratch**.

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

### Workshop notebooks – demystifying GPT and transformers

All workshop material lives under the `Notebooks/` directory.

- **Data preparation (`Notebooks/Data Preparation/`)**
  - **`ICTer_Sinhala_Data_Prep.ipynb`**: Uses the `sinhala-nlp/Sinhala-Corpus` dataset from Hugging Face to stream, filter, and export Sinhala text for language modeling.
  - **`ICTer_Tamil_Data_Prep.ipynb`**: Uses the `aitamilnadu/tamil_stories` dataset from Hugging Face to build a Tamil corpus, including basic cleaning and export.
- **GPT-from-scratch training (`Notebooks/Atto-GPT-Training/`)**
  - **`Sinhala_gpt_dev.ipynb`**: A step-by-step, Karpathy-inspired “Building a GPT” notebook that:
    - Downloads Sinhala raw text.
    - Explores the character vocabulary.
    - Builds a tiny GPT-style character-level language model in PyTorch.
    - Trains and samples text, illustrating how the GPT core works on Sinhala.
  - **`Tamil_gpt_dev.ipynb`**: The Tamil counterpart of the above, training a tiny GPT-style model on Tamil stories.
- **Pretrained tiny models (restricted)**
  - Under `Notebooks/DO NOT TOUCH/I SAID DON'T/LEAVE/RESTRICTED/Pico-GPT Training/` you will find:
    - Example development notebooks (`Sinhala_1_8m_gpt_dev.ipynb`, `Tamil_1_8m_gpt_dev.ipynb`).
    - Saved model weights (`sinhala_model_weights.pth`, `tamil_model_weights.pth`) for small trained models.
  - These are **reference artifacts** and are not intended to be edited during the workshop.

Together, these notebooks are designed to walk participants from:

1. **Raw Sinhala/Tamil text** → cleaned corpora suitable for modeling.  
2. **Token/character exploration** → understanding vocabularies and sequence encoding.  
3. **Implementing a tiny GPT core in PyTorch** → self-attention blocks, residual connections, and training loops.  
4. **Training & sampling** → generating Sinhala and Tamil text to see the model’s behavior.

### License and usage

Please ensure that any downstream use of this corpus complies with the original data source licenses and with your institutional or workshop guidelines. If you plan to redistribute models trained on this corpus, clearly document data provenance and any preprocessing steps you applied.


