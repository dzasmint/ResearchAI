# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Python-based financial research and analysis system focused on real estate and construction sector analysis in Vietnam. The project specializes in balance sheet modeling, financial projections, and market data analysis using data from various sources including Ministry of Construction (MoC) reports.

## Core Components

### 1. Balance Sheet Manager (`balance_sheet_manager.py`)
- Comprehensive financial modeling for real estate projects
- Handles debt scheduling, construction costs, land payments, presales, and revenue recognition
- Supports multi-year land payment schedules and flexible cash collection schedules
- Generates P&L statements with tax calculations
- Tracks inventory, customer prepayments, and cash flow projections
- Key functions:
  - `generate_balance_sheet_schedules()`: Full balance sheet generation with detailed parameters
  - `generate_simplified_balance_sheet_schedules()`: Simplified version for project pipeline calculations

### 2. MongoDB Data Pipeline (`upload_moc_to_mongodb.py`)
- Uploads Ministry of Construction (MoC) data to MongoDB
- Creates specialized collections:
  - `transaction_volume`: Real estate transaction data by quarter
  - `credit_outstanding`: Credit data by sector (urban, office, industrial, tourism)
  - `inventory`: Real estate inventory tracking (apartments, land, houses)
  - `infrastructure_projects`: Project statistics and scale metrics
- Implements efficient indexing for time-series queries

## Key Dependencies

- **pandas/numpy**: Data manipulation and financial calculations
- **streamlit**: Web application framework for UI
- **pymongo**: MongoDB connectivity for data persistence
- **openai/anthropic**: AI model integration for analysis
- **yfinance**: Financial market data retrieval
- **plotly**: Interactive data visualization
- **PyPDF2/pdf2image/pytesseract**: PDF processing and OCR for financial reports
- **reportlab**: PDF report generation
- **xlsxwriter/openpyxl**: Excel file processing

## Environment Configuration

Required environment variables in `.env`:
- `OPENAI_API_KEY`: OpenAI API access
- `GOOGLE_API_KEY`: Google services integration
- `GOOGLE_SEARCH_ENGINE_ID`: Custom search engine ID
- `PERPLEXITY_API_KEY`: Perplexity AI access
- `MONGODB_CONNECTION_STRING`: MongoDB connection string
- `MONGODB_DATABASE`: Database name for general data
- `MONGODB_COLLECTION`: Collection name for general data

## Data Structure

### Input Data Files
- `data/MoC_Data.csv`: Ministry of Construction quarterly data
- `data/*.parquet`: Processed financial analysis data (FA_processed, FA_A_processed, MktCap_processed)
- `data/Val_processed.csv`: Valuation data
- `data/*.pdf`: Financial reports with OCR extraction support
- `data/Report/`: Company-specific analysis reports

### MongoDB Schema
- Quarterly time-series data with consistent date indexing
- Categorized metrics for efficient querying
- Support for Vietnamese language metric names

## Development Commands

### Installing Dependencies
```bash
pip install -r requirements.txt
```

### Running Data Upload to MongoDB
```bash
python upload_moc_to_mongodb.py
```

### Running Balance Sheet Calculations
```bash
python balance_sheet_manager.py
```

## Architecture Notes

- Financial modeling engine supports complex real estate project scenarios
- Time-series data optimized for quarterly financial analysis
- MongoDB collections designed for efficient aggregation queries
- Supports both historical analysis and forward projections
- Handles Vietnamese and English data seamlessly