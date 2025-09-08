# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Python-based research and financial analysis application that leverages AI and data processing capabilities. The project integrates with multiple APIs including OpenAI, Google Search, Perplexity, and uses MongoDB for data storage.

## Key Dependencies

The project uses the following major libraries:
- **Streamlit**: Web application framework for the UI
- **pandas/numpy**: Data manipulation and analysis
- **openai/anthropic**: AI model integration
- **pymongo**: MongoDB database connectivity
- **yfinance**: Financial data retrieval
- **plotly**: Data visualization
- **PyPDF2/pdf2image/pytesseract**: PDF processing and OCR capabilities
- **streamlit-aggrid**: Advanced grid components for Streamlit

## Environment Configuration

The project requires a `.env` file with the following API keys and configurations:
- `OPENAI_API_KEY`: OpenAI API access
- `GOOGLE_API_KEY`: Google services integration
- `GOOGLE_SEARCH_ENGINE_ID`: Custom search engine ID
- `PERPLEXITY_API_KEY`: Perplexity AI access
- `MONGODB_CONNECTION_STRING`: MongoDB connection details
- `MONGODB_DATABASE`: Target database name
- `MONGODB_COLLECTION`: Collection name for data storage

## Data Files

The repository contains various data files for financial analysis:
- `.parquet` files: Processed financial data (FA_processed.parquet, MktCap_processed.parquet)
- `.csv` files: Market data (MoC_Data.csv, Val_processed.csv)
- `.pdf` files: Financial reports with OCR extraction capabilities

## Development Commands

### Installing Dependencies
```bash
pip install -r requirements.txt
```

### Running the Application
Since this is a Streamlit application, use:
```bash
streamlit run [main_app_file.py]
```

### Python Environment
Ensure Python 3.7+ is installed with all dependencies from requirements.txt.

## Architecture Notes

- The application processes financial data from multiple sources (PDFs, APIs, databases)
- OCR capabilities are integrated for extracting text from PDF financial reports
- Data is stored and retrieved from MongoDB for persistence
- Visualization is handled through Plotly integrated with Streamlit
- The system supports both OpenAI and Anthropic AI models for analysis