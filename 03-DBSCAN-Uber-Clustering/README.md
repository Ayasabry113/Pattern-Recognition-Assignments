# DBSCAN Clustering on Uber Pickup Locations

A Pattern Recognition project implementing DBSCAN from scratch on Uber pickup latitude/longitude data.

## What this project demonstrates
- Data loading and coordinate cleaning.
- Standardization of latitude and longitude.
- Euclidean distance and epsilon-region queries.
- A custom DBSCAN implementation (without using scikit-learn's DBSCAN).
- Identification of core, border, and noise points.
- Experiments with different `eps` and `min_samples` values.
- Geographic scatter plots and a parameter comparison table.

## Dataset setup

The notebook expects a CSV named `uber-raw-data-apr14.csv` in the same directory as the notebook. The dataset is not included in this repository.

Download the **Uber Pickups in New York City** dataset and use its April 2014 file, `uber-raw-data-apr14.csv`. Keep the original CSV filename or update `DATA_FILE` in the notebook.

Expected columns:
- `Lat`
- `Lon`

## Project structure
```text
03-DBSCAN-Uber-Clustering/
├── DBSCAN_Uber_Pickup_Clustering.ipynb
├── README.md
└── requirements.txt
```

Place the downloaded CSV beside the notebook when running locally. If you choose to upload the dataset to GitHub, check the file size and GitHub's current file limits first; it is not required to commit the dataset.

## Run locally
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate

pip install -r requirements.txt
jupyter notebook
```
Open `DBSCAN_Uber_Pickup_Clustering.ipynb` and run the cells from top to bottom.

## Implementation notes
- The DBSCAN algorithm is implemented with NumPy.
- Neighborhood results are cached during each run to avoid repeated distance calculations.
- The default experiment uses the first 5,000 valid coordinate rows. Set `MAX_SAMPLES = None` to use all valid rows.
- Clustering uses standardized coordinates and Euclidean distance. The plotted points use original latitude and longitude for readability.
- This is a coursework demonstration; standardized Euclidean distance is not a geodesic distance in kilometers.

## Technologies
Python, NumPy, Pandas, Matplotlib, Jupyter.
