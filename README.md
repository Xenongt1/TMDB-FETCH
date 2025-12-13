# TMDB Movie Data Pipeline

## Overview
This project processes TMDB movie data using a modular Python pipeline. It demonstrates a complete ETL (Extraction, Transformation, Load/Analysis) workflow, calculating key performance indicators (KPIs) and generating visualizations for movie revenue, ROI, and franchise performance.

## Features
- **Modular Architecture**: Code is organized into `extraction`, `transformation`, `analysis`, and `visualization` packages.
- **Robust API Fetching**: Handles retries and error checking when fetching data from TMDB.
- **In-Memory Processing**: Data is processed purely as Pandas DataFrames in memory.
- **Rich Outputs**:
    - **Data**: Saved as **HTML Tables** for easy inspection (`outputs/data/`).
    - **Plots**: Saved as high-quality PNG images (`outputs/plots/`).
- **Live Notebook**: A Jupyter Notebook (`final_report.ipynb`) that runs the pipeline live and displays interactive tables and plots.

## Project Structure
```
.
├── extraction/         # API Request Logic
│   └── api.py
├── transformation/     # Data Cleaning & Parsing
│   └── cleaning.py
├── analysis/           # KPIs, Rankings, & Comparisons
│   └── analysis.py
├── visualization/      # Plotting Functions
│   └── plots.py
├── pipeline/           # Orchestration
│   └── runner.py
├── config/             # Settings & Keys
│   └── settings.py
├── notebooks/          # Presentation Layer
│   └── final_report.ipynb
├── outputs/            # Generated Results
│   ├── data/
│   └── plots/
├── .env                # API Keys (GitIgnored)
└── requirements.txt    # Dependencies
```

## Setup & Installation

1.  **Clone the Repository**:
    ```bash
    git clone https://github.com/Xenongt1/TMDB-FETCH.git
    cd TMDB-FETCH
    ```

2.  **Install Dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3.  **Configure API Key**:
    - Create a `.env` file in the root directory (copy `.env.example`).
    - Add your TMDB API Key:
      ```
      TMDB_API_KEY=your_api_key_here
      ```

## Usage

### Option 1: Run the Pipeline (Command Line)
To execute the full ETL process, generate HTML tables, and save plots:
```bash
python3 -m pipeline.runner
```
*Results will be saved to `outputs/`.*

### Option 2: Run the Notebook (Interactive)
To view the analysis dynamically with styled tables and inline plots:
1. Open `notebooks/final_report.ipynb` in Jupyter Lab or VS Code.
2. Run all cells.

## Outputs
- **`outputs/data/cleaned_movies.html`**: The fully processed dataset.
- **`outputs/plots/`**:
    - `revenue_vs_budget.png`
    - `roi_by_genre.png`
    - `popularity_vs_rating.png`
    - `yearly_trends.png`
    - `franchise_comparison.png`
