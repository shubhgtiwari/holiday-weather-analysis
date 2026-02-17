# Holiday Weather Analysis — Delhi 2014

Exploratory data analysis of **365 days** of Delhi weather data (2014) from Weather Underground to identify the **optimal two-week holiday window** based on historical temperature, precipitation, humidity, and cloud cover patterns.

## Dataset

| Feature | Details |
|---------|---------|
| Source | Weather Underground (DEL airport station) |
| Period | January 1 – December 31, 2014 |
| Records | 365 daily observations |
| Features | 23 columns |

### Key Columns

| Column | Type | Description |
|--------|------|-------------|
| Max/Mean/Min TemperatureC | int | Daily temperature range (°C) |
| Max/Mean/Min Humidity | int | Humidity percentages |
| Precipitationmm | float | Daily precipitation (mm) |
| CloudCover | float | Cloud cover scale (0–8) |
| Max/Mean Wind SpeedKm/h | int | Wind speed measurements |
| Events | str | Weather events (Rain, Snow, Fog, etc.) |
| Max/Mean/Min VisibilityKm | int | Visibility range |

## Analysis Pipeline

1. **Data Loading:** `read_csv()` with `skipinitialspace=True` to handle malformed column names
2. **Data Cleaning:**
   - Remove HTML artifacts (`<br />`) from WindDirDegrees column
   - Rename malformed column headers
   - Handle missing values (NaN in Events, CloudCover, Max Gust Speed)
3. **Exploratory Analysis:**
   - Temperature trends across months
   - Precipitation patterns and rainy day frequency
   - Cloud cover and visibility correlation
   - Best weather weeks identification based on composite scoring
4. **Holiday Prediction:** Rank weeks by favorable weather composite (high temp + low rain + low cloud cover)

## Tech Stack

- **Language:** Python (Jupyter Notebook)
- **Libraries:** pandas, datetime
- **Data Source:** Weather Underground historical records

## Skills Demonstrated

- **Data Cleaning:** HTML artifact removal, column renaming, missing value handling
- **Exploratory Data Analysis:** Time series weather pattern analysis
- **Data-Driven Decision Making:** Composite scoring for optimal period selection
