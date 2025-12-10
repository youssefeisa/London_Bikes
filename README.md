# 🚴 London Bike Rides Analysis

## 📊 Project Overview

This project analyzes bike-sharing usage patterns in London from January 4, 2015 to January 3, 2017, examining how weather conditions, seasons, and temporal factors influence bike rental demand. The dataset contains 17,414 hourly observations paired with meteorological and calendar data.

## 📈 Dataset

**Size:** 17,414 records × 10 features  
**Time Period:** 2 years (Jan 2015 - Jan 2017)

### Variables

| Variable | Description | Type |
|----------|-------------|------|
| count | Number of bikes rented (hourly) | Integer |
| temp_real_C | Real temperature in Celsius | Float |
| temp_feels_like_C | Perceived "feels like" temperature | Float |
| humidity_percent | Humidity as a percentage (0-1 scale) | Float |
| wind_speed_kph | Wind speed in kilometers per hour | Float |
| weather | Weather conditions | Categorical |
| is_holiday | Public holiday indicator (0/1) | Float |
| is_weekend | Weekend day indicator (0/1) | Float |
| season | Season classification | Categorical |

## 🧹 Data Cleaning

The raw dataset (`london_merged.csv`) underwent the following transformations:

1. **Column Renaming**: Improved readability
   - `timestamp` → `time`
   - `cnt` → `count`
   - `t1` → `temp_real_C`, `t2` → `temp_feels_like_C`
   - `hum` → `humidity_percent`
   - `weather_code` → `weather`

2. **Normalization**: Converted humidity from 0-100 scale to 0-1 decimal format

3. **Categorical Mapping**:
   - **Seasons**: 0→spring, 1→summer, 2→autumn, 3→winter
   - **Weather**: 1→Clear, 2→Scattered clouds, 3→Broken clouds, 4→Cloudy, 7→Rain, 10→Rain with thunderstorm, 26→Snowfall

**Output:** `london_bikes_cleaned.csv`

## 💡 Key Findings

- 🎯 **Total rides (Oct-Dec 2015)**: 1,904,786 bikes
- 🌡️ **Optimal conditions**: 9.8-12.2°C with 13.7-17.2 km/h wind produces 80K-135K rides
- ❄️ **Seasonal impact**: Winter shows 50%+ demand reduction compared to other seasons
- ⏰ **Peak hours**: 8am (commute) and 5-6pm (evening commute)
- ☁️ **Weather preference**: Scattered/broken clouds outperform clear days (52K-43K vs 15K rides)
- 🥶 **Cold weather barrier**: Below 2.4°C, demand drops dramatically (96-844 rides)

## 🛠️ Technologies

- Python 3.13.5 (Pandas, NumPy, Matplotlib, Seaborn)
- Jupyter Notebook
- Tableau

## 📁 Files

- `London_Bikes.ipynb` - Data cleaning notebook
- `london_merged.csv` - Raw dataset
- `london_bikes_cleaned.csv` - Cleaned dataset