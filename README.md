# Australian Postcode Economic and Financial Territorial analysis
This project focuses on clustering and classifying Australian postcodes based on their economic and financial situations. Data has been sourced from official entities, namely the ABS (Australian Bureau of Statistics) and ATO (Australian Taxation Office). The datasets contain aggregated information presented in both average and median formats.

Data source:<br>
ABS: https://www.abs.gov.au/census <br>
ATO: https://www.ato.gov.au/About-ATO/Research-and-statistics/In-detail/Taxation-statistics/Taxation-statistics-2020-21/?anchor=IndividualsStatistics

## Repository Structure
* code: Contains all the Jupyter notebooks, scripts, and source code.
* data: Contains raw and processed data files.
* figures: maps with clustering results.

## Workflow
**1. Data Preprocessing (preprocess_data.ipynb)**
* **Data Loading:** Importing aggregated financial and economic datasets for Australian postcodes.
* **Data Cleaning:** Addressing potential inconsistencies, anomalies, and missing values. Noteworthy:
  * Outliers in the financial data are expected due to right skew distributions.
  * Replacement strategy: Unusual values are replaced by NaN and then imputed if they make up less than 10% of the dataset.
* **Feature Engineering:** Enhancing the dataset's depth by creating or adjusting features to better capture underlying patterns.

Note: Data scaling will be performed in the model notebook since two scaling methods will be experimented with.

**2. Data Clustering (clustering_model.ipynb)**
The primary goals are:

* **Hard Clustering:** Each postcode is exclusively allocated to one cluster.
* **Soft Clustering:** Ascertain the probabilities of each postcode's affiliation to every cluster. These are based on distances between postcodes and cluster centroids.

For each postcode, the output will be:
* **Cluster:** Assignation, represented as an integer between 1 and 3.
* **cluster1_proba:** Probability of belonging to cluster 1 (range: 0-1).
* **cluster2_proba:** Probability of belonging to cluster 2 (range: 0-1).
* **cluster3_proba:** Probability of belonging to cluster 3 (range: 0-1).

Clusters Description:
* **Cluster 1:** Represents upper class in SES (Socio Economic Status) terms.
* **Cluster 2:** Represents middle class in SES terms.
* **Cluster 3:** Represents lower class in SES terms.
