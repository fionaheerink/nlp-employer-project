# Bank of England Employer Project: NLP-Driven Insight Extraction from Quarterly Earnings Data

Group project completed as part of the University of Cambridge Institute for Continuing Education Career Accelerator (Data Science with AI and Machine Learning).

The goal of this project was to explore whether narrative signals from quarterly earnings call transcripts can complement prudential indicators and support earlier identification of emerging stress.

## Problem
Manual review of earnings calls is time-intensive and inconsistent, especially when comparing multiple banks over multiple quarters.

## Project overview
We worked with quarterly earnings call transcripts from major banks and built a pipeline combining NLP features with prudential indicators.

Key components included:
- Transcript extraction and parsing (including speaker attribution)
- FinBERT sentiment analysis (executives vs analysts)
- Aspect-Based Sentiment Analysis (ABSA) for topic-level sentiment
- Disagreement and evasiveness signals from Q&A interactions
- A “spin” metric to capture positive language combined with uncertainty/hedging
- Time-series alignment with prudential ratios (CET1, LCR, NSFR, LDR)
- XGBoost modelling to test short-horizon predictive relationships
- Retrieval Augmented Generation (RAG) prototype for transcript Q&A

## Data processing
We built a preprocessing pipeline to extract and structure transcripts from multiple banks, including:
- scraping PDFs from investor relations sources
- regex-based parsing and recursive text extraction
- handling inconsistent transcript formatting (especially speaker separation)
- adding an `exchange_id` to track new topics during Q&A sessions and enable analyst vs executive interaction analysis

## Cross-bank risk focus
Using topic-level signals, we compared recurring areas of analyst scrutiny across banks, for example:
- Funding and liquidity risk (Credit Suisse, UBS)
- Interest rate and market risk (HSBC, Deutsche Bank)
- Credit risk and asset quality (JP Morgan)

## RAG
My main responsibility in the group project was developing the **Retrieval Augmented Generation (RAG)** component, including a prototype chatbot to query transcripts across banks and quarters.

Implementation highlights:
- Chunked transcripts (800 tokens, 100 overlap)
- Embedded text using `sentence-transformers/all-mpnet-base-v2`
- Stored embeddings in **Chroma**
- Built retrieval + Q&A using **LangChain**
- Used **Phi-4-mini-instruct** as the generator model
- Added metadata (bank, quarter, source) to support targeted retrieval and comparisons

RAG was designed to support query-driven exploration of transcripts, including comparisons across banks and time periods.

## Results (high level)
Across the project, we observed patterns where analyst tone and evasiveness signals often appeared ahead of changes in prudential conditions.

## Notes
This project was completed as part of an academic programme and does not represent employment with the sponsoring organisation.

## Repository contents
- `EP_report.pdf`  
  Full group report describing the end-to-end approach, methodology, and results.

- `EP_presentation_slides.pdf`  
  Summary slides used for the final project presentation.

- `EP_rag_notebook.ipynb`  
  Focused notebook showing the Retrieval Augmented Generation (RAG) pipeline and chatbot prototype that I built as part of the project.
