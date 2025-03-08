# AirPods Volume Analysis Across Applications

## Project Proposal
I am a student from Sabancı University, Emre Törehan Törer, and this is my DSA210 term project. This project aims to analyze and correlate AirPods volume levels across different applications. The primary hypothesis being tested is whether the volume of AirPods changes when switching between applications.

## Hypotheses
Two hypotheses will be tested:

1. **First Hypothesis**: AirPods volume decreases when switching to certain applications(instagram, snapchat).
2. **Second Hypothesis**: AirPods volume increases when switching to other application(spotify).

## Motivation
Understanding how application switching influences AirPods volume levels can provide insights i"nto user behavior and audio preferences. By studying data acquired from Apple Health, this project aims to:

- Determine if volume levels change significantly when switching between applications.
- Identify patterns in volume adjustments across various app categories.
- Provide insights into optimizing user experience with audio settings.

## Data Sources and Preprocessing
To ensure privacy, raw data will not be shared in the repository. Instead, all analysis scripts and processed, anonymized data will be provided. A `.gitignore` file will be used to exclude sensitive or unnecessary files.

### 1. Apple Health Data
Exported data includes:
- **Application Usage**: Names of applications where audio levels were recorded.
- **Volume Levels**: Measured volume levels for each application.
- **Timestamps**: Time when volume data was recorded.

The Apple Health data is exported in `.xml` format, then converted into structured `.csv` files containing:
- Application names and corresponding volume levels.
- Timestamped volume changes across applications.

## Data Analysis
### 1. Data Preprocessing
This involves:
- Cleaning and structuring datasets from Apple Health.
- Merging datasets by timestamp to align volume levels with application usage.

### 2. Exploratory Data Analysis (EDA)
- Analyzing distributions of volume levels across different applications.
- Identifying trends in volume changes when switching between applications.

### 3. Correlation Analysis
- Investigating if certain applications correlate with increased or decreased AirPods volume.
- Examining statistical relationships between app categories and volume levels.

### 4. Visualization
- Using histograms, boxplots, heatmaps, bar charts, and line charts to represent volume trends and correlations.
- Findings will be included in the **Data Visualization** section of the repository.

## Expected Outcomes
- Insights into whether application switching influences AirPods volume.
- Trends in volume adjustment behaviors across different app categories.
- Potential recommendations for optimizing user experience based on findings.


