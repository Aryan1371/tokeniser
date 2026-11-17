# NeuroParse Studio — LLM Tokenizer & Latent Space Explorer

[![Live Demo](https://img.shields.io/badge/Live_Demo-GitHub_Pages-6366f1?style=for-the-badge&logo=github)](https://aryan1371.github.io/tokeniser/)
[![GitHub Repo](https://img.shields.io/badge/Repository-Aryan1371%2Ftokeniser-06b6d4?style=for-the-badge&logo=github)](https://github.com/Aryan1371/tokeniser)

🌐 **Live Demo Website**: [https://aryan1371.github.io/tokeniser/](https://aryan1371.github.io/tokeniser/)

**NeuroParse Studio** is a comprehensive, standalone educational web application designed to demonstrate the internal data pipelines powering modern Large Language Models (LLMs) and Transformer architectures.

---

## 🌟 Key Features & Innovations

### 1. Multi-Strategy Tokenizer Engine
- **Subword (WordPiece)**: Greedy longest-match tokenization with `##` prefix continuation logic.
- **Byte-Pair Encoding (BPE) Simulation**: Iterative character pairing and subword segmentation.
- **Character-Level Tokenizer**: Inspect raw unigram character decompositions.
- **Dynamic Vocabulary Pruner Slider**: Live slider that dynamically caps the active dictionary, forcing unknown words into smaller subword fragments so students can visualize the trade-off between **vocabulary size** and **token sequence length**.

### 2. Live Detokenizer (String Reconstruction)
- Reconstructs text from token IDs, automatically stripping subword continuations (`##`) and properly formatting punctuation boundaries.

### 3. Interactive Token Inspector (Click-to-Inspect)
- Click on **any** token chip in the stream to open an inspector card displaying:
  - Token String & Raw text
  - Decimal Token ID & Hexadecimal representation (`0x...`)
  - Full UTF-8 byte stream representation in Hex
  - Continuation flag (Subword piece vs Root token)

### 4. Next-Token Probability Simulator (N-Gram Language Model)
- Directly links tokenization to **Generative AI**:
  - Calculates transition probability distributions $P(\text{token}_{t} \mid \text{token}_{t-1})$ across the learned corpus.
  - Displays the top-3 predicted next tokens with live probability percentage bars.
  - Features an **"Autoregressively Append"** button to simulate next-token generation!

### 5. Dataset Presets Selector
- Quickly toggle between realistic, domain-specific corpora:
  - 🤖 **AI & LLM Concepts** (Neural networks, attention, weights, embeddings)
  - 💻 **Code & Software** (Compilers, bytecode, event loops, concurrency)
  - 🌌 **Astrophysics & Quantum** (Superposition, entanglement, relativity)
  - 💬 **Human Conversation** (Natural dialogue, questions & answers)

### 6. 64-Dimensional Character Trigram Embeddings & PCA 3D
- Computes normalized 64-dimensional character trigram frequency vectors ($L_2$ norm).
- Reduces the 64-dimensional space to 3 dimensions using **Principal Component Analysis (PCA)** with **Power Iteration and Deflation**.
- Renders an interactive 3D WebGL scatter plot using Plotly.
- Computes pairwise cosine similarity rankings with visual percentage bars.
- Tracks custom user queries through the entire pipeline:
  $$\text{Input Query} \longrightarrow \text{Tokens} \longrightarrow \text{64D Vector} \longrightarrow \text{3D Coordinate} \longrightarrow \text{Nearest Neighbors}$$

### 7. Export Capabilities
- One-click **"Export Vocab JSON"** button to download the learned vocabulary as a formatted JSON file.

---

## 🚀 How to Open and Run

The entire application is completely self-contained in a single file: `index.html`.

### Method 1: Open in Default Browser
```bash
cd /Users/arya/tokeniser
open index.html
```

### Method 2: Localhost Server
```bash
cd /Users/arya/tokeniser
python3 -m http.server 8000
```
Then visit: [http://localhost:8000](http://localhost:8000)

---

## 🛠 Tech Stack

- **HTML5 & CSS3**: Custom dark-mode UI with responsive grid, glassmorphism, and custom scrollbars.
- **Vanilla JavaScript (ES6+)**: Zero external JavaScript frameworks.
- **Plotly.js (v2.35.2)**: 3D WebGL scatter visualization.
