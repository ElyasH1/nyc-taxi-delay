# # NYC Yellow Taxi Delay Analysis
Machine learning and geospatial analysis project predicting high-delay-risk NYC Yellow Taxi trips using Python, pandas, scikit-learn, and GeoPandas.
## Project Question

Can we predict whether a NYC taxi trip will run significantly longer than expected, and what factors drive delay risk?

## Key Results

- Random Forest reduced average delay prediction error from 4.48 minutes to 3.21 minutes.
- The classifier identified around 75% of high-delay-risk trips.
- Random Forest achieved a ROC-AUC score of 0.849.
- Trip distance and pickup hour were the most important predictors.
- Penn Station/Madison Square West was a key delay hotspot because it had both high trip volume and high delay risk.

## Visual Example

![Trip Volume by Pickup Zone](images/trip_volume_by_pickup_zone.png)

## Methods Used

- Data cleaning and outlier handling
- Exploratory data analysis
- Leakage-safe train/test split
- Regression modelling
- Classification modelling
- Feature importance analysis
- Geospatial mapping with NYC taxi zones

## Model Performance

| Model | Task | Result |
|---|---|---|
| Naive baseline | Regression | MAE = 4.48 minutes |
| Random Forest | Regression | MAE = 3.21 minutes |
| Majority baseline | Classification | Failed to identify high-delay-risk trips |
| Random Forest | Classification | Recall = 75%, F1 = 0.64, ROC-AUC = 0.849 |

## Business Insights

The model can be used as an early warning tool for trips that may take longer than expected.

Trip distance is the strongest predictor of delay risk. Pickup time also matters, showing that delay risk changes throughout the day.

The geospatial analysis showed that delay is not only concentrated in the busiest areas. Some lower-volume zones had high average delays, while Penn Station/Madison Square West stood out because it had both high trip volume and high delay risk.

## Limitations

- Only January 2023 data was used.
- Weather, road closures, events, and live traffic data were not included.
- The model used a 100,000-row sample rather than the full dataset.
- High delay risk was defined relative to the training data, not by an official taxi delay standard.

## Future Improvements

- Add weather and event data.
- Train on several months of taxi data.
- Add pickup and dropoff borough features.
- Test XGBoost or LightGBM.
- Build a Tableau dashboard.
- Recreate key summaries using SQL.

## Files

- `notebooks/nyc_taxi_delay_analysis.ipynb` — main analysis notebook
- `images/` — exported project visuals
- `data/README.md` — data source information
