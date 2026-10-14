# K-means Clustering of World Development Data

K-means implemented **from scratch** and applied to the World Bank's World Development Indicators to find natural groupings of countries.

## Results
- Cleaned and reshaped raw World Bank data into **13,176 country-year records × 380 indicators**, covering all 265 countries and regions
- **K-means++** gave more consistent results across 20 runs than random initialisation, which produced occasional very poor clusterings
- Elbow analysis pointed to **k = 3**; PCA made the clusters clearly separable
- The three clusters map onto recognisable development stages:
  - Developing nations with young, rural populations (e.g. Chad, Uganda, Kenya)
  - Mixed-development economies (e.g. Qatar, Argentina, Bahrain)
  - Advanced economies with high life expectancy (e.g. France, Sweden, Denmark)

## What I built
- Data pipeline: wide-to-long reshaping, missing-data filtering, median imputation, normalisation
- K-means from scratch (assignment step, centroid update, WCSS loss) with random and k-means++ initialisation
- Comparison of stopping criteria (max iterations, centroid movement, loss change)
- Elbow method with automatic elbow detection
- PCA and t-SNE visualisation, outlier analysis and a DBSCAN comparison

## Run it
1. Download `WDICSV.csv` from the [World Bank WDI](https://datacatalog.worldbank.org/search/dataset/0037712) and place it in this folder.
2. `pip install -r requirements.txt`
3. Open `kmeans_world_development.ipynb` and run all cells.

*Built for CSC2042S Machine Learning, University of Cape Town (2025).*
