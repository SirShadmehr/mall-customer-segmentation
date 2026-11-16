# Mall Customer Segmentation

A reproducible customer segmentation project using **K-Means clustering** and the Mall Customers dataset.

## Objective

Segment mall customers based on two behavioral/business features:

- Annual Income (k$)
- Spending Score (1-100)

The project demonstrates an end-to-end unsupervised machine learning workflow: data inspection, exploratory data analysis, feature scaling, cluster selection, model training, evaluation, interpretation, and report export.

## Repository Structure

```text
mall-customer-segmentation/
├── data/
│   ├── raw/
│   │   ├── .gitkeep
│   │   └── Mall_Customers.csv   # Add locally; not committed
│   └── README.md
├── notebooks/
│   └── mall_customer_segmentation.ipynb
├── reports/
│   └── figures/
├── src/
├── requirements.txt
├── .gitignore
└── README.md
```

## Dataset

Download the **Mall Customers** dataset from Kaggle:

https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial

After downloading, place the CSV here:

```text
data/raw/Mall_Customers.csv
```

The dataset is intentionally not included in this repository. Check the dataset's license and terms on its source page before reuse or redistribution.

## Setup

Python 3.9 or newer is recommended.

```bash
# Clone the repository
git clone https://github.com/<your-username>/mall-customer-segmentation.git
cd mall-customer-segmentation

# Create and activate a virtual environment
python -m venv .venv

# Windows
.venv\Scripts\activate

# macOS / Linux
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

## Run the Notebook

```bash
jupyter notebook
```

Open:

```text
notebooks/mall_customer_segmentation.ipynb
```

Run the cells from top to bottom after placing the dataset in `data/raw/`.

## Methodology

1. Load the CSV and validate expected columns.
2. Inspect data types, summary statistics, missing values, and duplicates.
3. Explore customer age, income, and spending distributions.
4. Select annual income and spending score as clustering features.
5. Standardize features using `StandardScaler`.
6. Explore candidate values of `k` with the Elbow Method and Silhouette Score.
7. Fit K-Means with `k=5` for the main analysis.
8. Interpret cluster centers and compare segment statistics.
9. Export customer-level segment assignments and cluster summaries.

## Evaluation

The notebook reports the Silhouette Score for the selected model and compares scores across candidate cluster counts. A higher Silhouette Score generally indicates better separation, but the final choice of `k` should also consider the Elbow plot, visualizations, interpretability, and business context.

## Outputs

After running the notebook, the following files are generated:

- `reports/customer_segments.csv`
- `reports/cluster_summary.csv`

## Limitations

- The analysis uses only two features; adding other relevant features may change the segmentation.
- K-Means is sensitive to feature scaling, outliers, initialization, and the selected number of clusters.
- Cluster IDs are arbitrary. Descriptive segment names are generated from cluster centers relative to the dataset medians.
- These segments are exploratory and should be validated before being used for real marketing decisions.

## Technologies

- Python
- pandas, NumPy
- Matplotlib, Seaborn
- scikit-learn
- Jupyter Notebook

## License

Add a repository license before publishing if you intend to define reuse permissions for your code. Dataset licensing is separate and remains governed by its original source.
