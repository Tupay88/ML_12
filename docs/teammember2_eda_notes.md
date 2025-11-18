# EDA Findings – Team Member 2 (Aman Kaushik)

## Charts Created (saved in `/reports/charts/eda/`):
- incidents_by_hour.png
- delays_by_dayofweek.png
- top12_incident_type.png
- route_time_heatmap.png


## CSV Files Produced:
- Cleaned_TTC_Streetcar_Delays_2014_2025.csv
- TTC_Feature_Engineered_2014_2025.csv


## Key Insights from My EDA:
- Incident frequency peaks during **5–7 AM** and **2–4 PM**, confirming strong rush-hour effects.
- Routes **501**, **504**, and **506** show consistently higher incident volumes.
- Majority of incidents fall under **Mechanical**, **Investigation**, **Held By**, and **General Delay** categories.
- Weekends have fewer total incidents but show a **higher proportion of long delays**.
- **September, October, and February** show the highest monthly incident frequencies.


## Feature Engineering Completed:
- Extracted time-based variables: **year**, **month**, **dayofweek**, **hour**.
- Created binary features: **is_weekend**, **is_morning_rush**, **is_evening_rush**.
- Created **delay_bin** (Low / Medium / High / Severe).
- Encoded categorical columns: **route**, **station**, **bound**, **vehicle**.
- Created interaction feature: **route_time_combo**.

## Additional Contribution:
- Presented the final group PowerPoint presentation during the project delivery session.
- Explained key EDA insights, engineered features, and how they informed the modeling and evaluation stages.
- Assisted with aligning the storyline and visuals used in the final project presentation.


## Implications for Modeling Step:
- Cleaned and feature-engineered dataset handed off for Antonio (Member 3) to begin model training and optimization.
