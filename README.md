[README (1).md](https://github.com/user-attachments/files/33994249/README.1.md)
# Fundamentals of Data Science — Case Studies

**Author:** Bhukya Anil  
**Course:** Fundamentals of Data Science (FDS)  
**Department:** Computer Science and Engineering, Chaitanya Bharathi Institute of Technology (CBIT), Hyderabad

This repository contains two data-science case studies completed using Python. The projects follow a typical workflow: data loading, cleaning and preprocessing, exploratory data analysis (EDA), modelling, evaluation, visualisation, and interpretation of results.

## Case Studies

### 1. EastWest Airlines — Customer Clustering Analysis

**Objective:** Segment airline customers into groups with similar travel, loyalty, and reward-programme characteristics.

**Dataset:** `EastWestAirlines.xlsx` (the notebook reads the `data` worksheet). The customer ID column is excluded from modelling so that clustering is based on customer attributes rather than identifiers.

**Methods and workflow:**
- Explore customer attributes using summary statistics, histograms, box plots, and a correlation heatmap.
- Handle missing numeric values where necessary and standardise the features before clustering.
- Use the elbow method to explore possible cluster counts.
- Apply K-Means clustering with four clusters.
- Compare hierarchical agglomerative clustering with Ward, complete, and average linkage methods.
- Experiment with DBSCAN using different `eps` and `min_samples` values, identifying noise points where applicable.
- Compare clustering results using silhouette scores and visualise the cluster patterns with Principal Component Analysis (PCA).

**Purpose:** Customer segments can help an airline understand different loyalty and travel behaviours and design more targeted engagement or rewards strategies. The cluster labels are analytical groups, not predefined customer categories.

### 2. Wine Quality — Assessment Using Physicochemical Properties

**Objective:** Explore how wine physicochemical properties relate to quality scores and assess whether those properties can be used to estimate a wine's quality.

**Dataset:** Red and white wine quality data. The files are typically named `winequality-red.csv` and `winequality-white.csv` and use semicolon-separated values. The supplied archive is `wine+quality.zip`.

**Methods and workflow:**
- Inspect dataset shape, data types, missing values, duplicate rows, and summary statistics.
- Compare distributions of properties such as alcohol, volatile acidity, and residual sugar.
- Explore relationships between physicochemical properties and the quality score using correlation analysis and visualisations.
- Train multiple linear regression models using an 80/20 train-test split with `random_state=42`.
- Evaluate predictions using Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and the coefficient of determination (R²).
- Inspect model coefficients and possible multicollinearity to understand which features are associated with predicted quality.

**Results from the current notebook run:**

| Metric | Red wine | White wine |
|---|---:|---:|
| MAE | 0.5035 | 0.5863 |
| MSE | 0.3900 | 0.5690 |
| RMSE | 0.6245 | 0.7543 |
| R² | 0.4032 | 0.2653 |

In this run, the red-wine regression model achieved better test-set performance than the white-wine model. Alcohol had a positive association with quality in both datasets, while volatile acidity was negatively associated with quality. These are statistical relationships, not proof of causation; the models are best treated as analytical support rather than replacements for sensory assessment.

## Repository Contents

The repository includes the analysis notebooks, datasets, visualisation images, and the final report files. Main project files include:

- `clusteringanalysis.ipynb` — EastWest Airlines clustering workflow.
- `EastWestAirlines.xlsx` — airline customer dataset.
- `winequality.ipynb` — red and white wine quality analysis.
- `wine+quality.zip` — wine quality dataset archive.
- `cluster analysis*.png` and `wine quality*.png` — plots generated or used during analysis.
- The PDF and Word report files — formatted report for both case studies, if included in the repository.

## Tools and Libraries

- Python
- Jupyter Notebook
- pandas and NumPy
- Matplotlib and Seaborn
- scikit-learn
- openpyxl (for reading Excel workbooks)

## How to Run

1. Clone or download this repository.
2. Install Python 3 and Jupyter Notebook, or open the notebooks in a compatible notebook environment.
3. Install the required libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn openpyxl jupyter
   ```

4. Open `clusteringanalysis.ipynb` and run the cells from top to bottom. Keep `EastWestAirlines.xlsx` in the same working directory as the notebook, or update the file path in the loading cell.
5. Extract `wine+quality.zip` and make sure the red and white CSV files are available. In `winequality.ipynb`, update the CSV paths in the loading cells to match where the extracted files are stored. The CSV files are semicolon-separated, so use `sep=';'` when reading them.
6. Run the notebook cells from top to bottom to reproduce the analysis and figures. Some clustering metrics may depend on the data, preprocessing, and selected DBSCAN parameters; rerun the notebook to obtain the results for your environment.

## Notes and Limitations

- Clustering results depend on feature scaling, algorithm settings, and the number of clusters selected. PCA plots are two-dimensional summaries and do not preserve every aspect of the original feature space.
- In the wine analysis, duplicate rows were identified and retained in the current analysis. A separate sensitivity analysis with duplicates removed would help check their influence.
- The wine-quality models explain only part of the variation in quality scores, so predictions should not be treated as exact or definitive quality judgements.
- The conclusions are based on the supplied datasets and the notebook configuration; they may not generalise to all airline customers or all wines.

## References

- Cortez, P., Cerdeira, A., Almeida, F., Matos, T., and Reis, J. (2009). *Modeling wine preferences by data mining from physicochemical properties*. Decision Support Systems, 47(4), 547–553. [Dataset information at the UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/186/wine+quality).
- EastWest Airlines customer data: `EastWestAirlines.xlsx`, included in this project repository.
- scikit-learn documentation: https://scikit-learn.org/stable/

---

*Fundamentals of Data Science — academic project repository.*
