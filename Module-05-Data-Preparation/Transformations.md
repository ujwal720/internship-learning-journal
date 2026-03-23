# Week 5 – Data Preparation
## Data Transformation Techniques

After cleaning, datasets often need additional processing to make them suitable for analysis.  
Transformation involves creating new variables, reorganizing columns, or summarizing information.

---

# 1. Creating Ratios

Derived metrics help compare related values within a dataset.

Example calculations include:

### Metro Area vs City Area

=G2/D2

### Metro Population vs City Population

Metro Population / City Population

### Population Density

Population / Area

These calculations help evaluate urban growth and spatial distribution.

---

# 2. Using Pivot Tables

Pivot tables summarize large datasets quickly.

Steps:

1. Select the dataset
2. Go to **Insert → Pivot Table**
3. Choose the fields for rows and values

Examples:

- list countries with city counts
- compute population totals
- summarize statistics by region

---

# 3. Detecting Outliers

Charts derived from pivot tables can reveal unusual values.

Examples:

- cities with extremely high populations
- unusually dense metropolitan regions

Visualization helps highlight these anomalies.

---

# 4. Splitting Columns with Text to Columns

Scraped datasets sometimes combine multiple values into a single column.

Excel’s **Text to Columns** tool separates them.

Steps:

1. Select the column
2. Navigate to **Data → Text to Columns**
3. Choose a delimiter

Typical delimiters include parentheses, commas, or hyphens.

---

# 5. Creating Time-Based Variables

Date columns can be transformed to represent time categories.

Examples:

=WEEKNUM(Date)

=TEXT(Date,"mmm-yy")

These formulas allow grouping data by week or month.

---

# 6. Conditional Formatting

Conditional formatting highlights important patterns in numeric data.

Example usage:

- higher values displayed in red
- lower values displayed in green

This visual aid helps detect trends quickly.

---

# 7. Sparklines and Data Bars

Excel provides miniature charts embedded within cells.

Examples:

- sparklines to show time-based trends
- data bars to compare values visually

---

# 8. Accessing Data from APIs

Many datasets can be accessed through web APIs returning JSON.

Example using Python:

import requests

response = requests.get(url)  
data = response.json()

The retrieved data can then be sorted, filtered, or analyzed.

Rate limits may require delays between requests:

time.sleep()

---

# 9. Image Processing with Pillow

Pillow is a Python library used for image manipulation.

Example:

from PIL import Image

img = Image.open("image.jpg")  
img.show()

Capabilities include:

- resizing images
- rotating images
- converting file formats
- applying filters

Batch operations can be performed using loops.

---

# 10. Media Processing with FFmpeg

FFmpeg is a command-line program for working with audio and video files.

Basic command structure:

ffmpeg -i inputfile outputfile

Example:

ffmpeg -i video.avi video.mp4

Other operations include:

- cropping frames
- resizing videos
- modifying audio levels
- applying filters

---

# Summary

Data transformation reshapes cleaned data so it can support analysis, reporting, or machine learning tasks.
