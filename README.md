## ICTer Workshop – Sinhala & Tamil Mini GPT Models (Atto-GPT & Pico-GPT)

This repository accompanies an ICTer workshop focused on **demystifying the GPT core** and **building tiny transformer-style language models from scratch** for Sinhala and Tamil.

The emphasis is on understanding how GPT-like models work internally by training **very small, inspectable models**:

- **Atto-GPT**: character-level GPT-style models trained live during the workshop on Sinhala and Tamil.  
- **Pico-GPT**: slightly larger, pre-trained reference models whose weights and training notebooks are provided for inspection.

Any text files in `Data/` are simply raw material to feed these models and are **not** the focus of the workshop.

### Atto-GPT – models we build live

The **Atto-GPT** notebooks live in `Notebooks/Atto-GPT-Training/`:

- **`Sinhala_gpt_dev.ipynb`**
- **`Tamil_gpt_dev.ipynb`**

In these notebooks you will:

- Implement a **tiny GPT-style, decoder-only transformer** in PyTorch (multi-head self-attention, feed-forward blocks, residual connections, layer norm).  
- Train **character-level** language models for Sinhala and Tamil from scratch.  
- Inspect the vocabulary, context window, and parameter count so the models remain small enough to understand.  
- Generate Sinhala and Tamil text samples and relate the behavior back to the underlying architecture.

The goal is **intuition**: by the end, participants should feel comfortable reading and modifying GPT-style model code rather than treating it as a black box.

### Pico-GPT – pre-trained reference mini models

The **Pico-GPT** artifacts live in:

- `Notebooks/DO NOT TOUCH/I SAID DON'T/LEAVE/RESTRICTED/Pico-GPT Training/`

This directory contains:

- **Training/dev notebooks**: `Sinhala_1_8m_gpt_dev.ipynb`, `Tamil_1_8m_gpt_dev.ipynb`  
- **Saved model weights**: `sinhala_model_weights.pth`, `tamil_model_weights.pth`

Pico-GPT models are slightly larger than the Atto-GPT models and are intended for:

- Inspecting a more fully trained mini GPT in Sinhala and Tamil.  
- Experimenting with sampling strategies (temperature, top-k / top-p) and prompt design.  
- Comparing training curves, capacity, and sample quality vs. the smaller Atto-GPT models.

These assets are **read-only during the workshop**—they exist so you can poke at a working mini GPT without waiting for training to finish.

### How to use this repository in the workshop

- **Clone the repo and open the Atto-GPT notebooks** in Colab or a local Jupyter environment.  
- **Follow the cells** to implement, train, and sample from tiny GPT-style models for Sinhala and Tamil.  
- Optionally, **explore the Pico-GPT notebooks and weights** to see how a slightly larger mini GPT behaves on the same languages.

### License and usage

Please ensure that any downstream use of this corpus complies with the original data source licenses and with your institutional or workshop guidelines. If you plan to redistribute models trained on this corpus, clearly document data provenance and any preprocessing steps you applied.


