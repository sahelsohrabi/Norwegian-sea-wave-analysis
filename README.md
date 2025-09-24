# Norwegian Sea Wave Analysis

This repository contains an exploratory data analysis (EDA) and machine learning study on wave and oceanographic variables collected from the Norwegian Sea.

## Dataset

The dataset includes the following variables:

- `time`: Timestamp of observation
- `wave_height_m`: Total wave height (m)
- `wind_wave_height_m`: Wind-generated wave height (m)
- `swell_wave_height_m`: Swell-generated wave height (m)
- `sea_surface_temperature_C`: Sea surface temperature (°C)
- `ocean_current_velocity_m_s`: Ocean current velocity (m/s)
- `wind_speed_m_s`: Wind speed (m/s)
- `wind_direction_deg`: Wind direction (degrees)
- `wind_height_m`: Wind wave height (m)
- `wave_direction_deg`: Wave direction (degrees)
- `wave_period_s`: Wave period (s)
- Additional features: `month`, `day`, `season`, lagged features (`wind_wave_height_lag1`, `wind_speed_lag1`)

> **Note:** The original dataset is not included due to size and privacy considerations. A small example dataset can be created to run the code.

## Exploratory Data Analysis (EDA)

The EDA includes:

- Daily and monthly averages of wave height, sea surface temperature, wave period, and ocean current velocity.
- Correlation heatmaps among numeric variables.
- Wind rose and wave rose plots for visualizing wind and wave directions and magnitudes.
- Comparison between wind waves and swell waves, including their monthly contribution and correlation with wind speed.
- Scatterplots showing relationships such as Wave Height vs Wave Period.

## Machine Learning

A Random Forest Regressor was used to predict wind wave height from:

- `wind_speed_m_s`
- `ocean_current_velocity_m_s`
- `wave_period_s`

### Results

- R²: -0.086  
- RMSE: 1.030  

**Feature Importances:**

| Feature                     | Importance |
|-------------------------------|-----------|
| ocean_current_velocity_m_s    | 0.336     |
| wind_speed_m_s                | 0.335     |
| wave_period_s                 | 0.329     |

> The low R² indicates that these features alone are insufficient to predict wind wave height accurately, which aligns with the physical understanding that total wave height depends on both wind and swell contributions.

## Clustering Analysis

- KMeans clustering (3 clusters) was applied to wind wave height, swell wave height, wind speed, ocean current velocity, and wave period.
- Cluster analysis revealed distinct regimes of wave and ocean conditions.

## Visualizations

- Line plots for daily and monthly averages
- Bar plots for feature importances
- Correlation heatmaps
- Wind rose and wave rose plots
- Horizontal stacked bar plots for monthly wind vs swell contributions

## Notes

- Code is documented with comments explaining each step.
- Plots are saved in the `figures/` directory.
- The dataset is not included; users can create a sample dataset to run the scripts.

## Requirements

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn
- windrose
