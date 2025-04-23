# Headphone Exposure, Steps & Heart Rate Analysis

## Project Proposal
I am a student from Sabancı University, Emre Törehan Törer, and this is my DSA210 term project. This project aims to analyze and correlate headphone volume levels with step counts and heart rate using Apple Health data. The core idea is to explore whether physical activity and physiological response relate to changes in headphone volume exposure.

## Hypotheses
Two hypotheses will be tested:

1. **First Hypothesis**: Higher headphone volume levels correlate with increased heart rate.
2. **Second Hypothesis**: Higher physical activity (steps) correlates with increased headphone volume exposure.

## Motivation
Understanding the interaction between headphone usage and physiological signals like heart rate and steps can provide insights into health, behavior, and user context. By studying data acquired from Apple Health, this project aims to:

- Examine if increased volume coincides with increased physical activity or elevated heart rate.
- Provide a foundation for potential feedback systems that promote healthier audio habits.
- Demonstrate how everyday personal data can be used to gain insights into individual behavior.

## Data Sources and Preprocessing
To ensure privacy, raw data will not be shared in the repository. Instead, all analysis scripts and processed, anonymized data will be provided. A `.gitignore` file will be used to exclude sensitive or unnecessary files.

### 1. Apple Health Data
Exported data includes:
- **Headphone Audio Exposure**: Sound level in dB.
- **Step Count**: Number of steps recorded.
- **Heart Rate**: Heartbeat rate in BPM.
- **Timestamps**: Time when each data point was recorded.

The Apple Health data is exported in `.xml` format, then converted into structured `.csv` files using Python. The data is grouped by minute intervals to ensure proper temporal alignment.

## Data Analysis
### 1. Data Preprocessing
- Extract `HeadphoneAudioExposure`, `StepCount`, and `HeartRate` from `export.xml`
- Convert to `pandas` DataFrames and align on 1-minute intervals
- Clean and normalize timestamp formats

### 2. Exploratory Data Analysis (EDA)
- Plotting trends in volume, heart rate, and steps over time
- Identifying peak usage periods and activity

### 3. Correlation Analysis
- Measuring correlation between volume and heart rate
- Measuring correlation between volume and steps

### 4. Visualization
- Using line plots and scatter plots to show relationships
- Annotated graphs for peak patterns or outliers

## Expected Outcomes
- A combined CSV file with minute-level aggregation of volume, steps, and heart rate
- Insights into behavioral or physiological patterns associated with audio volume exposure
- Potential directions for health-focused feedback systems or research
