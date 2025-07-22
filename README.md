# Data4Justice_project
This project is part of Data4Justice course.

# NYC Construction Projects — Data Cleaning & Validation

This project contains a cleaned and validated version of the **Active Projects Under Construction** dataset from [NYC Open Data](https://data.cityofnewyork.us/).

## Dataset

- **File**: `cleaned_nyc_construction.csv`  
- **Rows**: 1000  
- **Columns**: 25 (after renaming and cleaning)

Module : 4
## Cleaning Steps

The dataset was processed in R following best practices in data cleaning and validation. Key steps:

1. **Loaded JSON data** from NYC Open Data using `jsonlite`
2. **Converted data types**: `award`, `latitude`, `longitude` to numeric
3. **Removed duplicates** to ensure unique rows
4. **Cleaned messy text fields** (trimmed whitespace, corrected casing)
5. **Renamed confusing variables** for clarity (e.g., `projdesc` → `project_description`)
6. **Handled missing values** in `zip_code`, `borough`, and ID fields
7. **Validated data** by:
   - Filtering out projects with unrealistic award values
   - Ensuring latitude and longitude fall within NYC bounds
8. **Saved cleaned output** as a CSV file

## Tools & Libraries Used

- **R** (v4.0+)
- **Packages**:
  - `dplyr`
  - `tidyr`
  - `jsonlite`
  - `stringr`
  - `janitor`
  - `ggplot2` (optional for visualization)

## Notes

- Column `project_description` was intentionally left unprocessed for future qualitative analysis.
- Columns like `location_1`, `computed_region_*` were renamed for readability.
- Final dataset is ready for analysis, mapping, or integration into dashboards.

Module 5:
## Questions Explored

1. **What is the average award amount for each borough?**  
2. **What is the total award amount for each borough?**  
3. **What is the total number of projects for each borough?**


## 📈 Key Findings

- Boroughs differ widely in both the **number of projects** and **total award amounts**.
- Some boroughs (like Manhattan) may receive **larger average awards** despite fewer projects.
- Construction types vary, with **CIP** being the most common across all boroughs.

## 📊 Visualizations

This section presents visual summaries of key insights from the NYC construction project data. The plots below help visualize disparities in funding, project distribution, and award size across boroughs.

### 1. Total Award Amount by Borough  
This bar plot shows the **total dollar amount awarded** for active construction projects in each NYC borough.

![Total Award Amount](images/total_award_by_borough.png)

---

### 2. Average Award Amount by Borough  
This chart highlights the **average project award** per borough. Some boroughs with fewer projects still receive disproportionately high average funding.

![Average Award Amount](images/average_award_by_borough.png)

---

### 3. Total Number of Projects by Borough  
This plot displays the **total count of construction projects** currently active in each borough.

![Project Count](images/total_projects_by_borough.png)

---

### 4. Award Distribution Histogram  
This histogram visualizes the distribution of award amounts across all projects. It reveals how many small vs. large-scale projects are present in the dataset.

![Award Distribution](images/award_distribution_histogram.png)

---

### 5. Top 10 Most Expensive Projects  
A snapshot of the ten most expensive construction projects currently underway in NYC, showing where major capital investments are being directed.

![Top Projects](images/top_10_expensive_projects.png)

---

*To regenerate these plots, see the R Markdown notebook in this repository.*




## License

This dataset originates from [NYC Open Data](https://opendata.cityofnewyork.us/) and is provided under their open data license.
