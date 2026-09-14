# Project repository 

## Directory Structure

The project is organized sequentially following a standard data science pipeline.

### 1. Data Collection (`data-collection/`)

* **Function**: Acquires data from original sources.
* **Core File**: `main.ipynb`
* **Details**:
  * Fetches grid load and wind generation data from the Bonneville Power Administration (BPA).
  * Fetches meteorological observations from Iowa State University.
  * Stores raw data in CSV / Excel formats for traceability.


### 2. Data Cleaning (`data-cleaning/`)

* **Function**: Transforms raw inputs into an analysis-ready dataset.
* **Core File**: `main.ipynb`
* **Details**:
  * Merges wind power data with meteorological features.
  * Handles missing values using interpolation and filtering rules.
  * Removes physically implausible observations (e.g., negative power output).
  * Applies basic standardization and normalization where appropriate.


### 3. Exploratory Data Analysis (`eda/`)

* **Function**: Examines data structure, distributions, and key relationships.
* **Core File**: `main.ipynb`
* **Details**:
  * Visualizes the characteristic S-curve relationship between wind speed and power output.
  * Defines and labels ramp events based on power change thresholds.
  * Conducts statistical tests (e.g., t-tests, chi-square tests) to compare stable and ramping regimes.


### 4. Unsupervised Learning (`unsupervised-learning/`)

* **Function**: Explores intrinsic structure without labeled outcomes.
* **Core File**: `main.ipynb`
* **Details**:
  * Applies dimensionality reduction techniques such as PCA and t-SNE.
  * Uses clustering algorithms (K-Means, DBSCAN) to investigate whether operational states emerge naturally from the data.


### 5. Supervised Learning (`supervised-learning/`)

* **Function**: Builds predictive models for ramp behavior and power output.
* **Core File**: `main.ipynb`
* **Details**:
  * **Classification**: Predicts the occurrence and direction of ramp events (binary and multi-class).
  * **Regression**: Predicts short-term wind power output under varying meteorological conditions.
  * Evaluates models using metrics such as ROC curves, confusion matrices, RMSE, and related diagnostics.


## Additional Files

* `progress-log.qmd`: A chronological log documenting project development and analytical decisions.
* `llm-usage-log.qmd`: A transparent record of Large Language Model assistance used during the project.


## How to Run

Notebooks are intended to be executed following the logical order of the data pipeline:

1. Run `data-collection/main.ipynb` to acquire raw data.
2. Run `data-cleaning/main.ipynb` to generate the cleaned and merged dataset.
3. Explore results starting with `eda/main.ipynb`, followed by unsupervised and supervised modeling notebooks as needed.
