# Module 4 – Data Sourcing
## APIs and Tools Used

This document describes the main APIs, libraries, and utilities used to gather and process data from different sources.

---

# 1. GitHub Actions

GitHub Actions is a built-in automation system available in GitHub repositories.  
It allows developers to run scripts automatically based on events or schedules.

## Creating a Scheduled Workflow

Workflow configuration files are placed inside:

.github/workflows/main.yml

Example configuration:

```yaml
name: Scheduled Task

on:
  schedule:
    - cron: "0 12 * * 6,0"

jobs:
  execute-script:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      - name: Run Python Script
        run: python script.py
```

## CRON Expressions

Scheduling is controlled using CRON syntax.

Example:

```
0 12 * * 6,0
```

This means the workflow runs at **12:00 UTC every Saturday and Sunday**.

Important details:

- Scheduled workflows use **UTC timezone**
- Execution may be slightly delayed depending on system load
- Exact timing is not always guaranteed

Typical applications:

- automated security scans
- scheduled data collection
- background maintenance tasks
- automatic deployments

---

# 2. Nominatim Geocoding API

Nominatim is a geocoding service built on top of OpenStreetMap data.  
It converts human-readable locations into geographic coordinates.

## Installation

```
pip install geopy
```

## Python Example

```python
from geopy.geocoders import Nominatim

geocoder = Nominatim(user_agent="geo_application")

result = geocoder.geocode("IIT Madras")

print(result.latitude)
print(result.longitude)
print(result.address)
```

The API response can include:

- geographic coordinates
- complete postal address
- bounding box
- type of place
- classification of location

---

# 3. Gemini AI Studio

Gemini AI Studio is a platform that can analyze images or videos using AI models.

## Screen Recording Data Extraction

Instead of conventional scraping, visual content can be processed using AI.

General workflow:

1. record a webpage while scrolling
2. capture frames from the recording
3. upload frames to Gemini AI
4. retrieve structured results such as JSON

Advantages:

- very low operational cost
- suitable for visually structured pages
- minimal scraping code required

For example, analyzing **1000 images costs only a few cents**.

---

# 4. LLM-Based Data Extraction (OpenAI)

Large Language Models can also assist with extracting structured data from webpages.

Instead of writing detailed parsing rules, the HTML content can be interpreted by an AI model.

Typical workflow:

1. retrieve webpage HTML
2. send the content to an LLM
3. request extraction of specific fields
4. receive structured output such as JSON

Conceptual example:

```python
import openai

response = openai.ChatCompletion.create(
    model="gpt-4",
    messages=[
        {"role":"user","content":"Identify the article title and body text"}
    ]
)
```

Benefits:

- handles messy or inconsistent HTML
- simplifies complex extraction logic
- produces structured information quickly

---

# 5. Markdown

Markdown is a simple text formatting language commonly used for documentation.

It is widely used for:

- GitHub documentation
- README files
- knowledge bases
- preparing text datasets

Example syntax:

```
# Main Title
## Section Title
- list item
```

Markdown is easy to write and easy for machines to parse.

---

# 6. MarkItDown

MarkItDown is an open-source tool developed by Microsoft that converts many document types into Markdown.

Supported formats include:

- PDF documents
- Microsoft Word files
- PowerPoint presentations
- Excel spreadsheets
- images with OCR
- HTML and XML
- CSV and JSON
- audio files

## Installation

```
pip install markitdown
```

Example usage:

```python
from markitdown import MarkItDown

converter = MarkItDown()
result = converter.convert("document.pdf")

print(result.text)
```

This tool helps transform diverse documents into a format suitable for AI pipelines.

---

# 7. Web Scraping Libraries

## HTTPX

HTTPX is a modern HTTP client library for Python.

Advantages:

- asynchronous request support
- efficient network communication
- improved connection management

---

## BeautifulSoup

BeautifulSoup is used to analyze and navigate HTML documents.

Example import:

```python
from bs4 import BeautifulSoup
```

Common uses:

- retrieving page titles
- extracting article text
- collecting hyperlinks
- locating specific tags

---

## lxml and XPath

lxml is a library for parsing structured documents.

XPath is a query language used to select elements from HTML or XML.

Together they allow precise extraction of webpage elements.

---

# 8. Tabula

Tabula is a tool designed to extract tables from PDF documents.

Example:

```python
import tabula

data = tabula.read_pdf("report.pdf", pages=18)
```

Extracted tables can then be exported into CSV or other structured formats.
