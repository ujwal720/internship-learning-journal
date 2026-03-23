# Week 5 – Data Preparation and Cleaning
## Techniques for Cleaning Data

Data cleaning refers to correcting errors, removing inconsistencies, and preparing raw datasets so they can be analyzed effectively.  
This section describes different ways to clean data using spreadsheets, command-line tools, programming libraries, and specialized software.

---

# 1. Data Cleaning with Excel

Microsoft Excel provides many built-in functions that help fix issues in small or medium datasets.

## Find and Replace

The Find and Replace tool allows users to quickly modify repeated text values across a dataset.

Shortcut:

Ctrl + H

Example use case:

Removing unwanted words that appear repeatedly within a column of country names.

---

## Converting Data Types

Sometimes numeric columns are mistakenly stored as text.  
Before calculations can be performed, the column format must be converted to a numeric type.

Steps:

1. Highlight the column
2. Change the format to **Number**
3. Verify that formulas can operate correctly

Common fields requiring this fix include population, area, and density.

---

## Removing Extra Whitespace

Data copied from websites often contains unnecessary spaces.  
Excel’s **TRIM** function removes extra spaces within text values.

Example:

=TRIM(D2)

This ensures consistent formatting for text entries.

---

## Eliminating Empty Rows

Datasets sometimes include blank rows that interrupt analysis.

Procedure:

1. Select the dataset
2. Open **Find & Select**
3. Choose **Go To Special**
4. Select **Blanks**
5. Remove the highlighted rows

---

## Removing Duplicate Records

Duplicate entries can distort results.  
Excel provides a simple tool to retain only unique values.

Steps:

1. Select the relevant column
2. Click **Data → Remove Duplicates**

---

# 2. Data Cleaning Using OpenRefine

OpenRefine is a free application designed specifically for handling messy data.  
Although it runs locally, it is accessed through a browser interface.

---

## Entity Resolution

Data collected from different sources may represent the same entity in slightly different ways.

Example:

xyz limited  
xyz ltd  
xyz ltd.

Even though these refer to the same organization, a computer treats them as separate entries.

---

## Faceting

OpenRefine allows users to create **text facets**, which display counts of unique values in a column.

This helps identify:

- spelling variations
- inconsistent formatting
- duplicate entities

---

## Clustering

The clustering feature groups entries that appear similar.

These similarities may arise due to:

- punctuation differences
- extra spaces
- abbreviations

Users can review suggested clusters and merge them into standardized values.

---

# 3. Data Profiling with pandas-profiling

The **pandas-profiling** library automatically generates a detailed report about a dataset.

Example usage:

from pandas_profiling import ProfileReport

profile = ProfileReport(df)  
profile.to_file("dataset_report.html")

The report highlights:

- dataset size
- missing values
- variable distributions
- correlations
- warnings about potential data issues

This helps identify cleaning tasks before building models.

---

# 4. Cleaning JSON Data with Visual Studio Code

Text editors such as Visual Studio Code can assist in cleaning structured text data like JSON files.

---

## Formatting JSON

Raw JSON files may appear difficult to read.  
Using the **Format Document** command restructures the file.

Command:

Ctrl + Shift + P → Format Document

---

## Multi-Cursor Editing

Multiple values can be edited at the same time using multi-cursor selection.

Shortcut:

Ctrl + D

---

## Selecting All Matches

All occurrences of a value can be selected simultaneously.

Steps:

Ctrl + F → Alt + Enter

---

## Sorting and Removing Duplicate Lines

VS Code also provides commands to:

Sort lines alphabetically  
Remove repeated lines

These features help standardize inconsistent entries such as city names.

---

# 5. Cleaning Data Using Unix Commands

Command-line utilities are extremely useful for handling large files such as server logs.

---

## Downloading Files

curl can retrieve files from the web.

Example:

curl --location URL --output logs.gz

---

## Decompressing Files

Compressed data can be expanded using gzip.

Example:

gzip --decompress logs.gz

---

## Viewing File Contents

Commands for previewing files include:

head -n 5 logs.txt  
tail -n 5 logs.txt

---

## Counting Records

wc counts lines or words in a file.

Example:

wc -l logs.txt

---

## Extracting Columns

cut extracts specific fields from text data.

Example:

cut -d " " -f 1 logs.txt

---

## Identifying Unique Entries

Sorting and counting can reveal frequent values.

Example:

sort logs.txt | uniq --count

---

## Pattern Searching

grep searches text using patterns.

Example:

grep "bot" logs.txt

---

## Editing Text

sed performs automated substitutions and formatting operations.

---

# Summary

Cleaning improves data reliability by correcting formatting errors, removing duplicates, and standardizing entries across the dataset.
