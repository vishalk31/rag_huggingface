# RAG HuggingFace Integration

This repository contains a Jupyter Notebook (`RAG_huggingface.ipynb`) that demonstrates how to integrate Retrieval-Augmented Generation (RAG) with HuggingFace models and other tools.

## Setup

### Prerequisites

- Python 3.x
- Jupyter Notebook

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/vishalk31/rag_huggingface.git
    cd rag_huggingface
    ```

2. Install the required packages:
    ```bash
    pip install llama-index-llms-bedrock
    pip install llama-index datasets llama-index-callbacks-arize-phoenix llama-index-vector-stores-chroma llama-index-llms-huggingface-api -U -q
    ```

## Notebook Overview

### 1. Installing Dependencies

The notebook starts by installing the necessary dependencies using `pip`.

### 2. Setting Up LLM

The notebook configures and initializes an LLM (Large Language Model) using `llama_index.llms.bedrock.Bedrock`. AWS credentials are needed to access the model.

### 3. Loading and Preparing Dataset

The dataset is loaded using the `datasets` library. The dataset is then saved as individual text files in the `data` directory.

### 4. Loading Documents

Documents are loaded from the `data` directory using `SimpleDirectoryReader`.

### 5. Embedding and Ingestion Pipeline

An ingestion pipeline is created using `llama_index.core.ingestion.IngestionPipeline`, which includes transformations like sentence splitting and embedding using `HuggingFaceEmbedding`.

### 6. Setting Up Vector Store

A persistent Chroma vector store is set up to store the embeddings. The ingestion pipeline is run to process the documents and store the embeddings in the vector store.

### 7. Creating Vector Store Index

A vector store index is created using `VectorStoreIndex` and the embeddings from the vector store.

### 8. Query Engine

A query engine is created using the vector store index and the LLM. The query engine is used to query the model with specific questions.

## Running the Notebook

1. Open the Jupyter Notebook:
    ```bash
    jupyter notebook RAG_huggingface.ipynb
    ```

2. Execute the cells sequentially to run the code.

## Example Query

The query engine can be used to answer questions like:
```python
response = query_engine.query(
    "Who found the answer to a search query collar george herbert essay?"
)
print(response)
```

## Notes

- Ensure that you have the necessary AWS credentials for accessing the LLM.
- The notebook uses the `HuggingFaceEmbedding` model `BAAI/bge-small-en-v1.5` for embeddings.

---

Feel free to modify the README as per your specific requirements.
