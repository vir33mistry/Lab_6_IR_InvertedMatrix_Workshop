# Inverted Matrix Workshop

## Student Information
- **Student Name:** Viraj Dipakkumar Mistry
- **Student ID:** 9088985


This project demonstrates how to build an **Inverted Matrix / Inverted Index** for a small text corpus using Python in Jupyter Notebook.

## Project Goal
The notebook shows the full information retrieval workflow:

1. Create or load a document collection
2. Tokenize text
3. Normalize tokens
4. Build an inverted index
5. Test phrase queries
6. Build positional indexes
7. Optimize positional storage
8. Compute IDF
9. Compute TF and TF-IDF

The notebook is designed for learning, classroom review, and basic experimentation with information retrieval concepts.

## File Structure
- `IR_InvertedMatrix_Workshop_completed_filled_tables.ipynb` — main notebook
- `sample_docs/` — text documents used as the corpus
- `README.md` — project overview and usage
- `.gitignore` — ignores cache, checkpoints, and environment files

## Main Concepts Covered

### 1. Document Collection
The notebook either creates a fallback corpus or loads `.txt` files from the `sample_docs` folder.  
This gives the project a set of documents to index.

### 2. Tokenization
Text is converted into tokens using:
- lowercasing
- regex-based word extraction

This prepares raw text for processing.

### 3. Normalization
Tokens are normalized by:
- removing stop words
- applying Porter stemming

This reduces variations of similar words, such as:
- `software`
- `softwares`
- `software-based`

into a more consistent stem, often something like `softwar`.

### 4. Inverted Index
An inverted index maps:
- **term -> list of document IDs containing that term**

This is the core structure behind search engines because it allows fast lookup of documents containing a query term.

### 5. Phrase Query
The notebook checks whether an exact sequence of normalized tokens appears in a document.  
Example phrases:
- `machine learning`
- `open source`

### 6. Positional Index
A positional index extends the inverted index by storing token positions:
- **term -> document ID -> positions**

This is useful for phrase search and proximity search.

### 7. Optimized Positional Index
The optimized version stores positions using `array("I")` instead of Python lists to reduce memory overhead.

### 8. IDF
Inverse Document Frequency measures how rare or informative a term is in the corpus:

IDF(term) = log(total_documents / documents_containing_term)

A rare term gets a higher IDF score.

### 9. TF and TF-IDF
Term Frequency counts how often a term appears in one document.

TF-IDF is calculated as:

TF-IDF = TF × IDF

This helps identify terms that are important in a specific document but not too common across all documents.

## How to Run

### Requirements
Recommended Python version:
- Python 3.10 or 3.11

Install packages:
```bash
pip install nltk pandas notebook
```

### Run the notebook
```bash
jupyter notebook
```

Then open:
`IR_InvertedMatrix_Workshop_completed_filled_tables.ipynb`

## Notes
- If NLTK stopwords are not available locally, the notebook uses a fallback stop-word set.
- The notebook is built to remain runnable even without internet access.
- The code is educational and focuses on clarity rather than production-scale indexing.

## Example Learning Outcomes
By reviewing this notebook, you should be able to explain:
- what tokenization does
- why normalization is important
- how an inverted index works
- why positional indexes help phrase searching
- how TF, IDF, and TF-IDF are calculated

## Suggested Classroom Review Points
- Why lowercasing improves consistency
- Why stop-word removal reduces noise
- Why stemming reduces vocabulary size
- Why sets are used first in the inverted index
- Why sorted posting lists make output cleaner
- Why positional indexes are needed for phrase queries
- Why IDF gives more value to rare terms
- Why TF-IDF is better than raw frequency alone
