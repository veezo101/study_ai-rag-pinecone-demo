
# AI RAG Pinecone Demo

This repository demonstrates a minimal hybrid-search demo using Pinecone (dense + sparse) together with LangChain and local Hugging Face embeddings. The interactive example is a Jupyter notebook.

## Features
- Example of creating a Pinecone index (serverless spec) and using `PineconeHybridSearchRetriever`.
- Dense embeddings via Hugging Face (`all-MiniLM-L6-v2`) and sparse encoding via `BM25Encoder`.
- Notebook-driven workflow that shows end-to-end indexing and retrieval.

## Quick start

1. Create and activate a virtual environment (recommended):

```bash
python -m venv .venv
source .venv/bin/activate   # bash / WSL
```

2. Install dependencies (run inside the venv or your notebook environment):

```bash
pip install --upgrade pip
pip install python-dotenv pinecone pinecone-text pinecone-notebooks langchain langchain-community sentence-transformers langchain-huggingface torch
```

3. Create a local `.env` from the template and add your Pinecone key:

```bash
cp .env.example .env
# edit .env and replace the placeholder value with your real key
```


4. Open and run the notebook:

- Use Jupyter Lab/Notebook or VS Code's notebook UI and run `experiments.ipynb`.

The notebook loads environment variables using `python-dotenv` and reads the API key from `PINECONE_API_KEY`.

## Environment variables
- `.env` (ignored by git) — put your real credentials here. Example tracked file: `.env.example`.
- Key used: `PINECONE_API_KEY`

Security note: Do not commit `.env` or real credentials. For CI/production, provide secrets via your CI provider or a managed secret store.
