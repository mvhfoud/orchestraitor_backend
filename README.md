# README: Orchestraitor Backend

## Overview
`VectorDatabase.py` is a notebook designed to build a model router that selects the best-performing model for answering user queries based on well-known large language model (LLM) benchmarks. It leverages FAISS and Sentence Transformers to efficiently retrieve and index high-dimensional vector representations of text data, allowing users to compare their input with benchmark questions and determine the optimal model for response generation.

## Features
- **Dataset Preparation**: Loads multiple LLM benchmark datasets from Hugging Face and processes them into JSON format.
- **Vectorization**: Uses `SentenceTransformer` (all-mpnet-base-v2) to encode textual data into embeddings.
- **Vector Indexing**: Utilizes FAISS for efficient similarity search.
- **Visualization**: Implements 3D PCA visualization with Plotly to explore vector space.
- **Query Search**: Compares user input against famous LLM benchmark questions to find the closest matches.

## Requirements
All required dependencies are already specified within the notebook, so no additional installation steps are needed outside of running the provided cells.

### Libraries Used
- `faiss-cpu` - Efficient similarity search library.
- `datasets` - Loading various LLM benchmark datasets.
- `pandas` - Data manipulation.
- `numpy` - Numerical computations.
- `json` - Handling JSON formatted datasets.
- `sentence-transformers` - Text embedding model.
- `plotly` - 3D visualization.
- `scikit-learn` - PCA for dimensionality reduction.

 **Compare User Input to LLM Benchmarks**:
   Modify the `user_query` variable inside the script to test retrieval:
   ```python
   user_query = "What is the fastest way to sort an array?"
   results = search_query(user_query, index, metadata, model, k=10)
   ```
   The script will return the most similar benchmark questions from the indexed datasets.

## Output Files
- `formatted_*.json` - Processed dataset files.
- `merged_benchmarks.json` - Merged benchmark dataset.
- `benchmark.index` - FAISS index file.
- `benchmarks.json` - Metadata for vector search.

