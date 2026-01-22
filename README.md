# Bank of England Employer Project: NLP-driven Insight Extraction from Quarterly Earnings Data

Group project completed as part of the University of Cambridge Institute for Continuing Education Career Accelerator (Data Science with AI and Machine Learning).

The goal of this project was to explore whether narrative signals from quarterly earnings call transcripts can complement prudential indicators and help surface early qualitative warning signals.

## Project overview
We worked with earnings call transcripts from multiple global banks across several quarters and combined NLP-based features with prudential metrics to support structured analysis and supervisor-style Q&A.

Key components included:
- **Transcript parsing and speaker attribution** (executives vs analysts)
- **Sentiment analysis** using FinBERT
- **Aspect-Based Sentiment Analysis (ABSA)** to capture topic-level sentiment
- A **“spin” metric** to detect positive language paired with uncertainty/hedging
- **Temporal analysis** linking language features to prudential ratios (e.g., CET1, LCR, NSFR, LDR)
- **XGBoost modelling** to test predictive relationships
- **Retrieval Augmented Generation (RAG)** prototype for transcript search and Q&A

## My contribution (RAG)
My main responsibility in the group project was developing the **RAG pipeline and chatbot prototype**.

Implementation highlights:
- Chunked transcripts (800 tokens, 100 overlap)
- Embedded text using `sentence-transformers/all-mpnet-base-v2`
- Stored embeddings in **Chroma**
- Built retrieval + Q&A using **LangChain**
- Used **Phi-4-mini-instruct** as the generator model
- Added metadata (bank, quarter, source) to support targeted retrieval and comparisons

## Tech stack
- **Python**
- **Pandas / NumPy**
- **Hugging Face Transformers**
- **SentenceTransformers**
- **Chroma**
- **LangChain**
- **XGBoost**

## Notes
This repository contains project outputs from an academic employer project. All work was completed as part of the programme and does not represent employment with the sponsoring organisation.
