# Multi-Modal RAG with Gemini Embedding 2

This project demonstrates a **Retrieval-Augmented Generation (RAG)** pipeline that uses **Google Gemini Embedding 2** for multi-modal data (text and other supported formats) and an LLM for answering user queries grounded in your own documents.

The core workflow is implemented in the Jupyter notebook **Multi_Model_RAG.ipynb**.

## Features
- Ingestion of your own data (e.g. text, PDFs, audios, videos, images, etc.)
- Chunking and preprocessing of documents
- Embedding generation using **Gemini Embedding 2**
- Storage of embeddings in a vector store (in-memory or external, depending on your implementation)
- Retrieval of top-k relevant chunks for a query
- Context-aware answer generation using an LLM with retrieved context
- Designed to be extended to multi-modal inputs (text + other supported modalities)

## Project Structure
- `Multi_Model_RAG.ipynb` – main notebook with the end-to-end RAG pipeline.

If you add more scripts or modules later (e.g. for data loaders or vector DB integrations), list them here.

## Prerequisites
- Python 3.9+ (recommended)
- A Google AI / Gemini API key with access to **Gemini Embedding 2**
- Jupyter (or VS Code with the Jupyter extension)

### Recommended Python Packages
Your exact dependencies may differ, but typical packages used in a RAG pipeline include:
- `google-generativeai` (or the official Gemini client you use)
- `python-dotenv` (for loading environment variables)
- `numpy`, `pandas`
- `faiss-cpu` or `chromadb` (or another vector store)
- `tqdm`

Consider creating a `requirements.txt` once your environment is stable.

## Configuration
1. **Set your Gemini API key** as an environment variable, for example:
   - On Windows (PowerShell):
     ```powershell
     $env:GOOGLE_API_KEY = "YOUR_API_KEY_HERE"
     ```
   Or use a `.env` file with a variable such as `GOOGLE_API_KEY` and load it in the notebook using `python-dotenv`.

2. If your notebook expects other configuration values (e.g. model names, vector DB paths), document or set them in a configuration cell in `Multi_Model_RAG.ipynb`.

## How to Run
1. Create and activate a Python virtual environment (optional but recommended).
2. Install required packages (for example):
   ```bash
   pip install -r requirements.txt
   ```
   or install the packages manually (e.g. `pip install google-generativeai chromadb python-dotenv`).
3. Open the notebook:
   - From the command line: `jupyter notebook Multi_Model_RAG.ipynb`
   - Or open it directly in VS Code and select a Python kernel.
4. Run the notebook cells from top to bottom:
   - Ingest / load your documents.
   - Build the embeddings index.
   - Ask questions and inspect the retrieved context and generated answers.

## Usage
- Replace or extend the sample documents in the ingestion step with your own data.
- Adjust chunking parameters (chunk size, overlap) to fit your use case.
- Tune the retrieval parameters (e.g. `top_k`) for better results.
- Experiment with different Gemini models for the **generation** step while keeping **Gemini Embedding 2** for retrieval.

## Extending the Project
- Add support for more data sources (databases, APIs, cloud storage).
- Swap or scale the vector store (e.g. use a managed vector DB in production).
- Wrap the notebook logic into Python modules and expose a REST API or a simple UI (e.g. Streamlit or Gradio).
- Add evaluation scripts to measure retrieval and answer quality.

## Notes
- This README is a generic template for a multi-modal RAG system using Gemini Embedding 2. Adjust section names, dependency lists, and configuration details to match the exact code and libraries used in your `Multi_Model_RAG.ipynb` notebook.