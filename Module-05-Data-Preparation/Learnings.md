# Week 5 – Data Preparation
## Key Learnings

This week focused on preparing raw datasets so they can be analyzed reliably.  
Multiple tools and techniques were explored for cleaning, organizing, and transforming data.

---

# 1. Importance of Cleaning Data

Raw datasets frequently contain problems such as:

- duplicate records
- inconsistent spellings
- missing values
- formatting issues

Cleaning ensures that analysis results are trustworthy.

---

# 2. Spreadsheet-Based Preparation

Excel offers many tools for preparing structured datasets.

Important techniques include:

- Find and Replace for correcting text
- TRIM for removing unnecessary spaces
- removing duplicates
- pivot tables for summarization

These tools are especially effective for moderate-sized datasets.

---

# 3. Automated Data Profiling

Libraries such as pandas-profiling provide quick insights into datasets.

The generated report identifies:

- missing values
- variable distributions
- extreme values
- correlations

This allows potential problems to be detected early.

---

# 4. Specialized Data Cleaning Tools

OpenRefine is designed to detect inconsistencies across datasets.

Its clustering feature helps group similar values and merge them into a standardized form.

---

# 5. Command Line Data Processing

Unix utilities provide fast methods for working with large text datasets.

Examples include:

- downloading files using curl
- decompressing files with gzip
- counting records using wc
- searching patterns with grep
- sorting and aggregating data using sort and uniq

These commands are commonly used when analyzing logs.

---

# 6. Accessing Data Through APIs

Web APIs provide programmatic access to structured datasets.

Using Python scripts, JSON responses can be retrieved, parsed, and analyzed.

---

# 7. Image and Media Processing

Tools like Pillow and FFmpeg enable manipulation of image and video files.

Examples include resizing images, converting formats, or adjusting audio/video properties.

---

# 8. Using Text Editors for Quick Cleaning

Editors such as Visual Studio Code support quick data modifications through features like:

- multi-cursor editing
- global search and replace
- sorting lines
- removing duplicates

---

# Key Takeaways

Major insights from this module include:

- cleaning is essential before performing analysis
- multiple tools exist depending on dataset size
- automated profiling can reveal hidden issues
- command-line tools handle large datasets efficiently
- transformation methods convert raw data into meaningful insights
