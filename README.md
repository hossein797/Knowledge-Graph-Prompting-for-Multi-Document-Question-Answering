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

flowchart TD  
    A[📄 Documents (PDFs)] --> B[🔧 Preprocessing & Parsing]  
    B --> C[🧠 Knowledge Graph Construction]  
    C --> D[📈 Embedding with BGE Model]  
    D --> E[🧭 LLM Traversal Agent]  
    E --> F[🗣️ Answer Generation]  
    F --> G[✅ Final Response]  

---

## 🧰 Installation

# 1️⃣ Clone the repository

```
git@github.com:hossein797/Knowledge-Graph-Prompting-for-Multi-Document-Question-Answering.git
```

# 2️⃣Install dependencies

```
pip install -r requirements.txt
```

---

## 🚀 Usage

# Follow the steps below to run the project correctly:  
1️⃣ Prepare your documents  
* Place all your PDF files in a single folder.  
* In the main script or notebook, replace the path variable with the path to your folder.
  
2️⃣ Set your LLM API key  
* The project uses a large language model (e.g., LLaMA-3.3-70B or OpenAI-compatible API).  
* Replace the placeholder with your own API key

3️⃣ Run the pipeline  
```python
from kgp import GraphBuilder, TraversalAgent

# Build the knowledge graph
builder = GraphBuilder(pdf_folder)
kg = builder.build()

# Create the traversal agent
agent = TraversalAgent(kg, api_key=os.environ["OPENAI_API_KEY"])

# Ask a question
response = agent.query("What are the main contributions of the KGP method?")
print("\n✅ Final Answer:\n", response)
```

✅ The model will:  
1.Extract and embed all documents  
2.Build a structured Knowledge Graph  
3.Traverse relevant nodes guided by LLM reasoning  
4.Return the synthesized multi-document answer

---
