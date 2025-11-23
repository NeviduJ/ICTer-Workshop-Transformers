## ICTer Workshop – Sinhala & Tamil Mini GPT Implementations (Atto-GPT & Pico-GPT)

This repository accompanies an ICTer workshop focused on **demystifying the GPT core** and **building tiny transformer-style language models from scratch** for Sinhala and Tamil.

The emphasis is on understanding how GPT-like models work internally by building **very small, inspectable implementations**:

- **Atto-GPT**: character-level GPT-style implementations built live during the workshop on Sinhala and Tamil.  
- **Pico-GPT**: slightly larger, pre-trained reference implementations whose weights and training notebooks are provided for inspection.

Any text files in `Data/` are simply raw material to feed these implementations and are **not** the focus of the workshop.

### Atto-GPT – implementations we build live

The **Atto-GPT** notebooks live in `Notebooks/Atto-GPT-Training/`:

- **`Sinhala_gpt_dev.ipynb`** – Basic Atto-GPT implementation for Sinhala
- **`Tamil_gpt_dev.ipynb`** – Basic Atto-GPT implementation for Tamil
- **`Sinhala_1_8m_gpt_dev.ipynb`** – Larger 1.8M parameter version for Sinhala
- **`Tamil_1_8m_gpt_dev.ipynb`** – Larger 1.8M parameter version for Tamil

In these notebooks you will:

- Implement a **tiny GPT-style, decoder-only transformer** in PyTorch (multi-head self-attention, feed-forward blocks, residual connections, layer norm).  
- Train **character-level** language models for Sinhala and Tamil from scratch.  
- Inspect the vocabulary, context window, and parameter count so the models remain small enough to understand.  
- Generate Sinhala and Tamil text samples and relate the behavior back to the underlying architecture.

The goal is **intuition**: by the end, participants should feel comfortable reading and modifying GPT-style model code rather than treating it as a black box.

### Pico-GPT – pre-trained reference implementations

The **Pico-GPT** artifacts live in `Notebooks/Pico-GPT-Training/`:

- **Training/dev notebooks**: 
  - `Sinhala_1_8m_gpt_dev.ipynb`
  - `Tamil_1_8m_gpt_dev.ipynb`
- **Saved model weights** (in `Saved_Model_Weights/`):
  - `sinhala_model_weights.pth`
  - `tamil_model_weights.pth`

Pico-GPT implementations are slightly larger than the basic Atto-GPT implementations and are intended for:

- Inspecting a more fully trained mini GPT in Sinhala and Tamil.  
- Comparing training curves, capacity, and sample quality vs. the smaller Atto-GPT implementations.

These assets are **reference implementations**—they exist so you can poke at a working mini GPT without waiting for training to finish.

### Repository structure

```
Notebooks/
├── Atto-GPT-Training/          # Implementations built live during workshop
│   ├── Sinhala_gpt_dev.ipynb
│   ├── Tamil_gpt_dev.ipynb
│   ├── Sinhala_1_8m_gpt_dev.ipynb
│   └── Tamil_1_8m_gpt_dev.ipynb
├── Pico-GPT-Training/          # Pre-trained reference implementations
│   ├── Sinhala_1_8m_gpt_dev.ipynb
│   ├── Tamil_1_8m_gpt_dev.ipynb
│   └── Saved_Model_Weights/
│       ├── sinhala_model_weights.pth
│       └── tamil_model_weights.pth
└── Data Preparation/          # Data preprocessing notebooks
    ├── ICTer_Sinhala_Data_Prep.ipynb
    └── ICTer_Tamil_Data_Prep.ipynb
```

### How to use this repository in the workshop

- **Clone the repo and open the Atto-GPT notebooks** in Colab or a local Jupyter environment.  
- **Follow the cells** to implement, train, and sample from tiny GPT-style implementations for Sinhala and Tamil.  
- Optionally, **explore the Pico-GPT notebooks and weights** to see how a slightly larger mini GPT behaves on the same languages.

### Credits and acknowledgments

The GPT implementation and training approach in this workshop is inspired by and adapted from **Andrej Karpathy's "Zero to Hero" series**:

- **"Let's build GPT: from scratch, in code, spelled out"** – [karpathy.ai/zero-to-hero](https://karpathy.ai/zero-to-hero.html)
- The notebooks follow Karpathy's pedagogical style of building a GPT-style transformer from scratch, step by step, with clear explanations of each component.

This workshop adapts those concepts to build tiny GPT implementations on **Sinhala and Tamil** text, making the transformer architecture accessible to participants working with these languages.

### License and usage

Please ensure that any downstream use of this corpus complies with the original data source licenses and with your institutional or workshop guidelines. If you plan to redistribute models trained on this corpus, clearly document data provenance and any preprocessing steps you applied.


