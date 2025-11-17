# Data Folder – ML_12 TTC Streetcar Delays Classification Project

## Overview

The `data/` directory contains all datasets used in the **ML_12 TTC Streetcar Delays Classification Project** (2014–2025).

- `raw/` holds the original TTC datasets downloaded from the City of Toronto’s Open Data Portal.  
- `processed/` contains cleaned and standardized data ready for EDA.  
- `TTC_Feature_Engineered_2014_2025.csv` is the feature-engineered dataset used for modeling.

---

## Folder Structure

```text
data/
│
├── raw/                                  # Original TTC data (downloaded from Open Toronto)
│   ├── TTC_Streetcar_Delays_2014_2025.csv
│   └── *.xlsx, *.csv   (yearly / monthly source files)
│
├── processed/                            # Cleaned and standardized datasets
│   └── TTC_Streetcar_Delays_Cleaned_2014_2025.csv
│
├── TTC_Feature_Engineered_2014_2025.csv  # Final dataset used for modeling
│
|__ model.ipynb # notebook containing code that performed the data consolidation
|
└── README.md                             # Documentation for this data folder
Data Source & Collection
Source: Toronto Open Data Portal

Dataset: TTC Streetcar Delay Data (2014–2025)

URL: https://open.toronto.ca/dataset/ttc-streetcar-delay-data/

Publisher: Toronto Transit Commission (TTC)

License: Open Government License – Toronto

Free for public and academic use, subject to attribution and license terms.

All raw files in data/raw/ were downloaded directly from the Open Data Portal and then consolidated and cleaned as part of this project.

Dataset Description
Each row in the TTC Streetcar Delay dataset represents a service delay or incident recorded by TTC operations.

Typical fields include:

Date & Time – when the delay occurred

Route Number / Line – streetcar route involved

Location / Intersection – where the incident occurred

Incident Type – root cause (e.g., Mechanical, Collision, Overhead, General Delay)

Delay Duration (min) – number of minutes delayed

Direction (bound) – EB / WB / NB / SB

Vehicle Number – identifier for the streetcar involved

These data are the foundation for:

Exploratory Data Analysis (EDA)

Feature engineering

Training the incident-type classification models

How to Load the Final Dataset
python
Copy code
import pandas as pd

# Load the feature-engineered dataset used for modeling
df = pd.read_csv("data/TTC_Feature_Engineered_2014_2025.csv")

print(df.shape)   # number of rows and columns
df.head()         # preview the first few rows
