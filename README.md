# Information Retrieval (RI26A) - Recuperación de Información

A Python-based information retrieval project implementing classical and modern text search algorithms using corpus data from Project Gutenberg books.

## Project Overview

This project demonstrates core information retrieval techniques for document ranking and search, featuring implementations of:
- **TF-IDF** (Term Frequency-Inverse Document Frequency)
- **BM25** (Best Matching 25) - Probabilistic relevance ranking

## Directory Structure

```
Recuperacion_Informacion/
├── README.md                          # This file
├── debug_subjects.py                  # Debug script for subject exploration
├── ver_subject.py                     # Script to view subject details
│
├── 03tfidf/
│   └── 03tfidf.ipynb                 # TF-IDF implementation notebook
│
├── 04bm25/
│   └── 04bm25.ipynb                  # BM25 implementation notebook
│
└── data/
    ├── 01_corpus_turismo_500.txt     # Tourism corpus (500 documents)
    ├── descargar_gutenberg.py        # Book downloader from Project Gutenberg API
    ├── gutenberg/                    # API metadata cache
    │   ├── datasource.txt
    │   └── data/
    └── libros_gutenberg/             # Downloaded book collection (~1000 books)
        └── [book files]
```

## Features

### Algorithms
- **TF-IDF**: Vector space model implementation for document similarity
- **BM25**: Probabilistic model for ranking search results

### Data Sources
- **Tourism Corpus**: Pre-processed collection of 500 documents on tourism topics
- **Gutenberg Books**: Parallel downloader for ~1000 books from Project Gutenberg API with auto-retry and cleanup

### Utilities
- `debug_subjects.py`: Explore and debug Project Gutenberg API subject structure
- `ver_subject.py`: View detailed subject information from the API

## Setup

1. Clone or navigate to the project directory
2. Install dependencies:
   ```bash
   pip install requests
   ```

3. (Optional) Download additional books from Project Gutenberg:
   ```bash
   python data/descargar_gutenberg.py
   ```

## Usage

### Running Notebooks
Open and run the notebooks in Jupyter:
- `03tfidf/03tfidf.ipynb` - TF-IDF implementation and experiments
- `04bm25/04bm25.ipynb` - BM25 implementation and experiments

### Utilities
```bash
# Explore subjects from Project Gutenberg API
python debug_subjects.py

# View specific subject details
python ver_subject.py
```

## Key Components

### TF-IDF Implementation
- Creates document-term matrix
- Computes inverse document frequency weights
- Ranks documents by cosine similarity

### BM25 Implementation
- Probabilistic relevance model
- Considers term saturation and document length
- Generally outperforms TF-IDF for ranking quality

## Data Processing

The project includes:
- Pre-processed tourism corpus for testing
- Automated Gutenberg book downloader with parallel execution (10 workers)
- Support for text cleaning modes ("simple" or "super")
- Rate-limit handling and automatic retries

## Requirements

- Python 3.7+
- requests library
- Jupyter Notebook/Lab (for running .ipynb files)

## Notes

- API keys are configured in the downloader scripts
- The Gutenberg downloader supports ~1000 concurrent book downloads
- All text files are stored in `.txt` format

## Course Context

This is part of the RI26A (Information Retrieval 2026A) course, covering fundamental IR techniques and their practical implementation.
