# TDS Data Analyst 2 Project

## Overview
This project is a robust, extensible data analysis and web scraping platform built with FastAPI. It enables users to upload files, scrape data from the web, extract and process data from various sources (CSV, Excel, PDF, SQL, web pages, and archives), and interact with multiple AI/LLM APIs for advanced data analysis and code generation.

## Features
- **Web API**: Built with FastAPI for high-performance async data processing and file handling.
- **File Upload & Extraction**: Supports CSV, Excel, PDF, JSON, SQL, ZIP, TAR, and image files. Archives are extracted and categorized automatically.
- **Web Scraping**: Uses Playwright, BeautifulSoup, and custom logic to extract tables and data from web pages, with fallback and error handling.
- **AI/LLM Integration**: Connects to OpenAI, Gemini, Claude, and Horizon APIs for code generation, data extraction, and analysis.
- **Prompt Engineering**: Uses prompt templates for code generation and task breakdown (see `prompts/`).
- **Data Cleaning**: Automated numeric field detection and cleaning using LLMs and heuristics.
- **CORS Enabled**: Ready for integration with web frontends.

## File Structure
- `app.py` — Main FastAPI app, API endpoints, file handling, LLM integration, and orchestration logic.
- `data_scrape.py` — Advanced web scraping, numeric data cleaning, and Playwright-based extraction utilities.
- `requirements.txt` — All required Python packages.
- `prompts/` — Prompt templates for LLM code generation and task breakdown.

## Setup
1. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
2. **Set environment variables** (for API keys):
   - Create a `.env` file in the project root with your API keys:
     ```env
     API_KEY=your_openai_key
     gemini_api=your_gemini_key
     gemini_api_2=your_gemini_key_2
     horizon_api=your_horizon_key
     CLAUDE_API_KEY=your_claude_key
     OCR_API_KEY=your_ocr_key
     OPENAI_GPT5_API_KEY=your_gpt5_key
     ```
3. **Run the API server**:
   ```bash
   uvicorn app:app --reload
   ```

## Usage
- Access the API endpoints to upload files, trigger web scraping, or request code/data analysis.
- Integrate with a frontend or use tools like Postman/curl for testing.
- Prompts for code generation and task breakdown are in the `prompts/` folder.

## Requirements
See `requirements.txt` for all dependencies. Major packages include:
- fastapi, uvicorn, httpx, python-dotenv, pandas, numpy, matplotlib, playwright, playwright-stealth, beautifulsoup4, openpyxl, pdfplumber, tabula-py, duckdb, and more.

## Prompts
- `prompts/unified_code_instructions.txt`: LLM prompt for generating Python code to analyze data.
- `prompts/task_breaker.txt`: LLM prompt for breaking down analysis tasks into steps.

## License
See `LICENSE` file.

## Credits
Developed for advanced data analysis and automation tasks, supporting extensible AI and data workflows.
