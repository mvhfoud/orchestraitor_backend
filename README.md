# README: VectorDatabase.py

## Overview
`VectorDatabase.py` is a Python script designed to build a model router that selects the best-performing model for answering user queries based on well-known large language model (LLM) benchmarks. It leverages FAISS and Sentence Transformers to efficiently retrieve and index high-dimensional vector representations of text data, allowing users to compare their input with benchmark questions and determine the optimal model for response generation.

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

## Usage Instructions
1. **Run the script**:
   ```bash
   python vectordatabase.py
   ```
2. The script will:
   - Download LLM benchmark datasets from Hugging Face.
   - Format them into JSON files.
   - Convert text data into embeddings.
   - Store embeddings in a FAISS index.
   - Provide visualization and search capabilities.

3. **Compare User Input to LLM Benchmarks**:
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

## Potential Use Cases
- Building a model router to dynamically select the best-performing LLM for each benchmark.
- Comparing user questions to established LLM benchmark datasets.
- Evaluating AI model performance based on benchmark similarity.
- Identifying patterns in question similarity.
- AI-driven document retrieval and FAQ recommendation.

## Author
This script was developed for exploring vector database applications using FAISS and embedding models.

## License
This project is released under the MIT License.
