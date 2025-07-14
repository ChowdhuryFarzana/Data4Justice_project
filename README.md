# Data4Justice_project
This project is part of Data4Justice course.

# NYC Construction Projects — Data Cleaning & Validation

This project contains a cleaned and validated version of the **Active Projects Under Construction** dataset from [NYC Open Data](https://data.cityofnewyork.us/).

## Dataset

- **File**: `cleaned_nyc_construction.csv`  
- **Rows**: 1000  
- **Columns**: 25 (after renaming and cleaning)

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

## License

This dataset originates from [NYC Open Data](https://opendata.cityofnewyork.us/) and is provided under their open data license.
