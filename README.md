# Knowledge-Graph-Prompting-for-Multi-Document-Question-Answering
A modern implementation of Knowledge Graph Prompting (KGP) for Multi-Document Question Answering (MD-QA) — integrating knowledge graphs, semantic embeddings, and LLM-based traversal agents.
<div align="center">

# 🧩 Knowledge Graph Prompting for Multi-Document Question Answering  
### 🚀 A Modern Implementation & Enhancement

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-red?logo=pytorch)
![spaCy](https://img.shields.io/badge/spaCy-green?logo=spacy)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![LLM](https://img.shields.io/badge/Model-LLaMA%203.3--70B--Turbo-orange?logo=openai)

</div>

---

## 🧠 Overview

This repository presents a **faithful implementation and improvement** of the paper  
> *"Knowledge Graph Prompting for Multi-Document Question Answering"* (Wang et al., 2024)

The project constructs a **Knowledge Graph (KG)** from multiple documents, then guides a **Large Language Model (LLM)** to **traverse** this graph to find the most relevant evidence and generate accurate, grounded answers.

---

## ⚙️ Key Components

| Component | Description |
|------------|--------------|
| 🗂️ **Knowledge Graph Builder** | Extracts passages, tables, and pages from PDFs and connects them via structural & semantic edges. |
| 🔍 **Semantic Embeddings** | Uses `BAAI/bge-large-en-v1.5` for rich contextual vector representations. |
| 🧭 **LLM Traversal Agent** | A reasoning agent built on `meta-llama/Llama-3.3-70B-Instruct-Turbo`, performing adaptive graph traversal. |
| 💡 **Enhanced Seeding Mechanism** | Replaces TF-IDF with semantic similarity search for more meaningful seed nodes. |

---

## 📈 Improvements Over Original Paper

✅ **Stronger Embedding Model** (`bge-large-en-v1.5`)  
✅ **Semantic Seeding** instead of TF-IDF  
✅ **Efficient Graph Traversal** guided by LLM reasoning  
✅ **Reduced Hallucination & Improved Contextual Coherence**

---

## 🧩 System Architecture

```mermaid
flowchart TD
    A[📄 Documents (PDFs)] --> B[🔧 Preprocessing & Parsing]
    B --> C[🧠 Knowledge Graph Construction]
    C --> D[📈 Embedding with BGE Model]
    D --> E[🧭 LLM Traversal Agent]
    E --> F[🗣️ Answer Generation]
    F --> G[✅ Final Response]
