
# 🧠 Quantitative Discourse Analysis with Python

This repository contains a complete pipeline for **quantitative discourse analysis** using modern NLP tools. It demonstrates how to collect, embed, cluster, and analyse historical texts using sentence-level methods, topic modelling, and frequency analysis. The workflow centres on two works by **Samuel Smiles**—*Self-Help* and *Thrift*—which are compared across multiple dimensions.

---

## 📂 Notebooks Overview

### 📌 [1. Web Scrape – Text Acquisition & Preprocessing](https://colab.research.google.com/drive/19rUD3E9UbiqVW4PtNam0xklP1k1-YW1r?usp=drive_link)

- Downloads *Self-Help* and *Thrift* from Project Gutenberg.
- Removes boilerplate headers/footers.
- Tokenises texts into sentence lists.
- Outputs: `self_help.pkl`, `thrift.pkl`

---

### 📌 [2. Sentence Analysis – Embedding + FAISS Indexing](https://colab.research.google.com/drive/1tLHsa4z5VM2X__j1gvWfvYATDL1m0SoE?usp=sharing)

- Loads sentence-level corpora and computes dense vector embeddings using `all-mpnet-base-v2`.
- Embeds both *Self-Help* and *Thrift* corpora with `SentenceTransformer`.
- Builds **FAISS indexes** for fast semantic search and retrieval.
- Saves embeddings and index files for later modelling or querying.

---

### 📌 [3. BERTopic – Custom Topic Modelling](https://colab.research.google.com/drive/1KG_x_4bCzasG94ZWz16hmsoW4r1CnXY2?usp=sharing)

- Runs BERTopic using a custom setup:
  - `UMAP` for dimensionality reduction
  - `HDBSCAN` for clustering
  - `CountVectorizer` for topic term extraction
- Produces interpretable, clustered topics on the *Self-Help* corpus.
- Customisable via `min_topic_size`, `nr_topics`, `min_cluster_size`, etc.

---

### 📌 [4. Word Frequencies – Unigrams, Bigrams & Trigrams](https://colab.research.google.com/drive/1n7lNWZ72gNMlytTv6C8jsfDDQpfuI8vS?usp=drive_link)

- Cleans and tokenises full corpora.
- Computes:
  - Word frequencies
  - Bigrams and trigrams
- Visualises top phrases across both corpora to identify recurring linguistic structures.

---

## 📘 Project Purpose

This project was designed to demonstrate how **quantitative methods** can be applied to historical or literary texts for:
- Comparative discourse analysis
- Topic exploration
- Language pattern detection

Although it uses Victorian texts, the workflow is fully transferable to other corpora.

---

## 🔧 Requirements

Each notebook includes setup steps. Core packages:
- `sentence-transformers`, `faiss-cpu`, `bertopic`
- `nltk`, `spacy`, `scikit-learn`, `matplotlib`
- `requests`, `beautifulsoup4`
