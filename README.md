# Movie Ratings Analysis

A Jupyter notebook project that combines multiple genre CSV files, cleans the data, and explores movie rating patterns with summary tables and visualizations.

## Project Structure

- `data/` - Source CSV files split by genre
- `notebook/` - Jupyter notebook with the analysis workflow
- `image/` - Saved plots generated from the analysis
- `report/` - Reserved for written reports or final findings

## Requirements

Install the Python packages below before running the notebook, or use the dependency file in the project root:

```bash
pip install -r requirements.txt
```

## What the Notebook Does

- Loads all CSV files from `data/`
- Combines them into one dataframe
- Reviews dataset info, summary statistics, and missing values
- Fills missing values and removes duplicates
- Creates visualizations for rating distribution, top genres, highest rated genres, top rated movies, and votes vs rating

## How to Run

1. Open `notebook/Movie_Ratings_Analysis.ipynb` in Jupyter or VS Code.
2. Run the cells from top to bottom.
3. Review the generated plots in `image/` and the dataframe outputs in the notebook.

## Notes

- The notebook expects the CSV files to remain in `data/`.
- Generated plot images can be kept in `image/` for reporting or presentation.
