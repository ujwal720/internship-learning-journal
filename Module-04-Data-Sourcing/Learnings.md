# Module 4 – Data Sourcing
## Learnings

This module introduced various methods for collecting, organizing, and preparing data from different digital sources.

---

# 1. Semantic Search Prototype

A demonstration project involved building a semantic search system using articles from Insider Intelligence.

Dataset characteristics:

- 369 archive pages
- approximately 7000 articles

Traditional search systems such as **ElasticSearch** rely mainly on matching keywords.

Semantic search goes further by interpreting the **meaning and context of queries**.

The prototype returned articles ranked by relevance using similarity scores.

---

# 2. Collecting Data Through Web Scraping

Since direct access to the dataset was unavailable, the information was collected through scraping.

The process included:

1. retrieving article links from archive pages
2. downloading each article page
3. extracting titles and main text
4. storing the information in a structured format

Libraries used:

- HTTPX
- BeautifulSoup
- lxml
- XPath

---

# 3. Using Caching During Scraping

Caching refers to storing downloaded webpages locally.

Benefits include:

- reducing repeated downloads
- lowering server load
- allowing interrupted scraping processes to resume

This significantly speeds up development.

---

# 4. Structuring Extracted Data

After extraction, the information was saved in JSON format.

Example structure:

```
{
"title": "Article Title",
"content": "Main article text"
}
```

Structured data simplifies later analysis and search indexing.

---

# 5. Extracting Web Data with Excel

Data can also be imported directly into Excel from websites.

General process:

1. open Excel
2. navigate to the Data tab
3. choose Get Data
4. select From Web
5. paste the webpage URL
6. select the required table
7. transform the data using Power Query

The connection remains active and can be refreshed to update the data.

---

# 6. Extracting Tables from PDFs

Tables contained in PDF files can be converted into structured datasets.

Steps involved:

1. identify PDF links from a webpage
2. download the PDF files
3. extract tables using Tabula
4. save the extracted data as CSV files

Example:

```
tabula.read_pdf("document.pdf", pages=18)
```

Some complex layouts may require specifying extraction coordinates.

---

# 7. Debugging Strategies

Several debugging approaches were discussed.

Print Statements  
Used to inspect intermediate variables.

Breakpoints  
Allow developers to pause execution and inspect the program state.

Rubber Duck Debugging  
Explaining a problem aloud often clarifies logical mistakes.

AI tools such as ChatGPT can also assist in debugging and learning.

---

# 8. Experimental Side Projects

Informal experiments, sometimes called "Friday night experiments," encourage creative exploration.

Even if experiments fail, they contribute valuable learning experiences.

---

# Data Pipeline Diagram

```
Data Sources
   │
   ▼
Websites / APIs / PDFs
   │
   ▼
Data Collection
(HTTPX, BeautifulSoup, Excel Web Connector)
   │
   ▼
Data Extraction
(XPath, lxml, Tabula, LLM extraction)
   │
   ▼
Data Processing
(Python scripts, Power Query)
   │
   ▼
Structured Storage
(JSON / CSV / Markdown)
   │
   ▼
AI Applications
(Semantic Search, LLM analysis)
```

---

# Key Takeaways

Skills developed in this module include:

- acquiring data from multiple sources
- extracting structured information
- applying web scraping techniques
- using APIs for geolocation
- converting documents into machine-readable formats
- debugging code efficiently
- preparing datasets for AI applications
