# LightRAG Integration with Web Crawling and Ollama LLM

This project provides a simple, Jupyter Notebook-based workflow to:
- **Crawl Websites:** Extract text data from one or more websites using the `crawl4ai` Python package.
- **Preprocess and Store Data:** Save the extracted texts in a structured format for further processing.
- **Build a LightRAG System:** Integrate the preprocessed data with LightRAG (using `lightrag-hku`), which leverages faiss-gpu for efficient vector storage.
- **Configure Local LLM:** Use your local Ollama LLM (which must support at least 32k tokens of context) along with the nomic-embed-text embedding model.
- **Interactive Querying:** Use `ipywidgets` within Jupyter Notebook to interactively query the system and choose different response modes.

## Features

- **Automated Data Extraction:** Use crawl4ai to recursively extract data from a website and its subpages.
- **Vectorized Indexing:** Utilize faiss-gpu to create and update a vector index from the crawled data.
- **Customizable LLM Integration:** Easily configure your local LLM and ensure it supports a large context size (minimum 32k tokens) for LightRAG.
- **User-Friendly Interface:** The notebook includes interactive widgets for entering URLs, setting configurations, and querying the system.

## Environment Setup

This project uses a dedicated Conda environment. We define an environment YAML file with Python version 3.11 and the following packages:

- `crawl4ai` for crawling websites,
- `lightrag-hku` for LightRAG creation,
- `faiss-gpu` for vector storage,
- `ipywidgets` for interactive inputs.
- `playwright` needed for crawl4ai's asynchronous browser access

**Instructions:**
1. **Create the Environment:**  
   Open your terminal and run:
   ```bash
   conda env create -f environment.yml
   ```

2. **Activate the Environment:**
    Once created, activate it with:
    ```bash
   conda activate lightrag
   ```

3. **Run playwright update**
    Needed from Crawl4Ai to asynchronous browser access 
    ```bash
    playwright install
    ```

4. **Launch Jupyter Notebook:**
    With the environment activated, start Jupyter Notebook:
    ```bash
    jupyter notebook
    ```

## Getting Started

1. **Clone the Repository:**
     ```bash
    git clone https://github.com/Bjobster/LightRAG
    cd lightRAG
    ```

2. **Set Up the Environment:**
Follow the instructions above to create and activate the Conda environment.

3. **Open the Notebook:**
Launch the provided Jupyter Notebook (e.g., lightRAG.ipynb) and follow the step-by-step instructions to crawl websites, configure your LLM, build the LightRAG system, update the index with new data, and perform queries.

3. **Project Structure**
environment.yml – Conda environment configuration file.
README.md – Project description and setup instructions.
lightRAG.ipynb – Jupyter Notebook containing the code and interactive elements.