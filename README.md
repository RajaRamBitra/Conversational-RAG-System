# Conversational RAG System

This project is a simple yet powerful implementation of a Retrieval-Augmented Generation (RAG) system in a Jupyter Notebook. The system can answer questions based on a knowledge base of text files. It uses the `sentence-transformers` library to create embeddings, `faiss` for efficient similarity search, and the `groq` API for language model interaction.

## Features

* **Local Knowledge Base:** Uses a directory of `.txt` files as its knowledge source.
* **Efficient Retrieval:** Employs FAISS for fast and accurate retrieval of relevant document chunks.
* **Advanced Generation:** Leverages the Groq API with the Llama 3 model for generating human-like answers.
* **Interactive Chat:** An easy-to-use interface to ask questions and get answers from your documents.

## Getting Started

### Prerequisites

* Python 3.x
* Jupyter Notebook or JupyterLab
* A Groq API key

### Installation

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-link>
    cd <your-repo-name>
    ```

2.  **Install the required libraries:**
    ```bash
    pip install -q sentence-transformers faiss-cpu groq
    ```

3.  **Set up your knowledge base:**
    * Create a folder named `Jupiter_Files` (or update the `knowledge_base_dir` variable in the notebook).
    * Add your `.txt` files to this directory.

4.  **Add your Groq API Key:**
    * You will need to set your Groq API key as an environment variable or directly in the notebook.

### Usage

1.  **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook RAG.ipynb
    ```

2.  **Run all the cells in the notebook.**

3.  **Ask a question in the interactive prompt at the end of the notebook.**

## How It Works

1.  **Load Knowledge Base:** The system reads all `.txt` files from the specified directory.
2.  **Create Embeddings:** The `SentenceTransformer` model converts the text from the files into numerical embeddings.
3.  **Index Embeddings:** The embeddings are stored in a FAISS index for efficient searching.
4.  **Search:** When you ask a question, it is converted into an embedding and used to search the FAISS index for the most relevant text chunks.
5.  **Generate Answer:** The retrieved text and your original question are passed to the Groq API, which generates a final answer.

## Customization

* **Change the Model:** You can easily swap out the `all-MiniLM-L6-v2` model with any other model from the `sentence-transformers` library.
* **Use a Different LLM:** The `get_completion` function can be modified to use a different language model or API.
* **Adjust Search Parameters:** You can change the number of retrieved documents by modifying the `k` parameter in the `search` function.
