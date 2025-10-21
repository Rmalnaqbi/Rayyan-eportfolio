# Academic Research Online Agent

## Overview
The Academic Research Online Agent is a simple web application that helps collect, summarize, and organize online information.  
It automatically crawls a web page, extracts the text, generates a short summary, identifies important keywords, and saves the results in a database.  
Users can interact with the system through REST API endpoints or export saved data to a CSV file.

This project was developed as a freelance-style academic project to demonstrate backend development, text processing, and database integration.

---

## Features
- Web Crawling – fetches content from any given web page.
- Text Summarization – creates short summaries using TF-IDF.
- Keyword Extraction – finds the most relevant terms in the content.
- Data Storage – saves results in a SQLite database.
- REST API – endpoints to process, list, and retrieve documents.
- Export to CSV – download all stored documents as a CSV file.
- Automated Testing – unit tests included to ensure functionality.

---

## Getting Started

### 1. Setup Environment

# Create and activate a virtual environment
python -m venv venv
source venv/Scripts/activate   # On Windows
# or
source venv/bin/activate       # On macOS/Linux

# Install dependencies
pip install -r requirements.txt

## Run Tests
pytest -q

## Start the API
export FLASK_APP=app.api   # On macOS/Linux
set FLASK_APP=app.api      # On Windows PowerShell
flask run --port=5000

## Usage Examples

# Add a New Document
curl -X POST -H "Content-Type: application/json" \
-d '{"url":"https://example.com"}' \
http://127.0.0.1:5000/process

# List All Documents
curl http://127.0.0.1:5000/documents

# Get a Document by ID
curl http://127.0.0.1:5000/documents/1

# Export to CSV
python export_to_csv.py

## Project Structure
research_agent/
├─ requirements.txt
├─ README.md
├─ export_to_csv.py
├─ app/
│  ├─ __init__.py
│  ├─ crawler.py
│  ├─ processor.py
│  ├─ storage.py
│  ├─ api.py
│  └─ models.py
├─ tests/
│  ├─ test_crawler.py
│  ├─ test_processor.py
│  └─ test_storage.py
└─ research_agent.db   # created after running
