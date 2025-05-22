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
## Findings
###  Step Count Distribution

The graph below illustrates the distribution of step counts recorded per minute based on Apple Health data.

- The x-axis represents the **number of steps taken** within a minute.
- The y-axis shows the **frequency** of occurrence for each step range.

A **smoothed trendline** has been added over the histogram to highlight the overall distribution pattern.

Key insights:
- The distribution is **right-skewed**, meaning lower step counts occur more frequently than higher ones.
- Most of the activity is concentrated under **100 steps per minute**, indicating moderate physical activity.
- A few high-frequency peaks suggest intervals of intense walking or workouts.

This kind of distribution is typical in daily movement data, where periods of inactivity or slow walking dominate, with occasional bursts of high movement.

![step_distribution (1)](https://github.com/user-attachments/assets/5d0f2f68-7c61-4a57-8ffd-c17a48648681)

###  Average Step Count by Month

The following bar chart presents the average step counts recorded for each month based on Apple Health data.

- The **x-axis** represents the **month**.
- The **y-axis** shows the **average number of steps** taken during that month.

This visualization highlights **seasonal trends and fluctuations** in physical activity:

- Step counts are generally higher in **summer months (e.g., June–August)**.
- Decreased activity is observed during **colder months** or transitional periods like **January and November**.
- Periodic peaks may reflect changes in lifestyle, holidays, or improved weather.

Such visualizations help interpret user movement patterns and their changes throughout the year.

![monthly_steps_bar_chart (3)](https://github.com/user-attachments/assets/22fecad6-e03d-4b32-b774-dfec4c269c3b)


###  Heart Rate Distribution

The following histogram shows the **distribution of heart rate measurements** collected from Apple Health data.

- The **x-axis** represents heart rate values in beats per minute (bpm).
- The **y-axis** shows how frequently each heart rate value occurred in the dataset.

#### Observations:
- The distribution is **centered around 80–90 bpm**, which aligns with typical resting and walking heart rate ranges.
- The shape of the histogram is **slightly right-skewed**, indicating occasional higher heart rate readings.
- A few values above **100 bpm** suggest moments of physical exertion or stress.
- Lower values (<70 bpm) are also present, indicating periods of rest or calm.

This distribution gives a solid overview of how heart activity varied over time and helps contextualize physical effort levels.
![heart_rate_distribution](https://github.com/user-attachments/assets/01bcbf32-eba2-4147-a47c-93c471499949)


###  Average Heart Rate by Month

The chart below shows the **monthly average heart rate (in bpm)** calculated from Apple Health data.

- The **x-axis** represents months over the recorded period.
- The **y-axis** shows the average heart rate (beats per minute) for each month.

#### Key Observations:
- The overall average heart rate ranges between **75–95 bpm**.
- There is **relatively consistent heart rate activity** across most months, suggesting stable cardiovascular patterns.
- Occasional **peaks and dips** could reflect changes in physical activity, stress levels, or rest periods.
- For example, a **slight dip in early 2023** might indicate reduced activity or improved rest during that period.
- Similarly, **late 2024 and early 2025** show a subtle increase in heart rate, possibly due to increased physical strain or activity.

This visualization helps identify potential changes in physical or physiological patterns over time.

![monthly_heart_rate_bar_chart (2)](https://github.com/user-attachments/assets/b2fa6b3f-800b-41c3-bd41-f3b65f7a9eb9)

###  Distribution of Audio Exposure Levels

The following histogram displays the distribution of headphone audio exposure levels recorded over time.

- The **x-axis** represents the audio level in decibels (dB).
- The **y-axis** shows the frequency of each volume level.

#### Observations:
- The distribution is **highly right-skewed**, with a **prominent peak around 90–95 dB**, indicating that users tend to listen at high volumes frequently.
- There is minimal exposure under 60 dB, suggesting that low-volume listening is uncommon.
- Multiple smaller bumps in the trendline suggest **varying audio usage contexts**, such as quiet background use, casual listening, or intense media consumption.
- The overall shape implies that **volume levels are not randomly distributed**, but tend to cluster around louder ranges, potentially raising concerns for hearing safety.

![audio_level_distribution](https://github.com/user-attachments/assets/2fd025ad-b201-42e7-babf-75e4fb5c304f)

###  Monthly Average Audio Exposure

This bar chart shows the **average headphone audio levels per month** over the recorded period.

- The **x-axis** shows each month from July 2021 to April 2025.
- The **y-axis** represents the average decibel (dB) level recorded in that month.

#### Insights:
- Average audio levels remain consistently high, often hovering around **85–95 dB**.
- Certain months (e.g., **mid-2022 and early 2025**) display **noticeable peaks**, which could align with periods of increased headphone usage (e.g., during travel, studying, or personal events).
- Slight dips during **late 2023 and early 2024** may reflect reduced usage or shifts in listening behavior.

This trend gives a useful overview of long-term audio exposure habits and seasonal shifts in user behavior.

![monthly_audio_bar_chart (1)](https://github.com/user-attachments/assets/99b76901-0b64-4ecf-8972-5e8fb457f2c2)

###  Physical Activity – Combined Apple Health Data

Following composite visualization provides a comprehensive view of step counts, flights climbed, and walking/running distances in separate histograms. It enables a comparative analysis of different activity metrics and their respective distributions, offering a holistic perspective on physical activity patterns.

![combined_health_histograms (2)](https://github.com/user-attachments/assets/d17c6b59-e7f0-459e-afa7-fbdb72761d33)

###  Correlation Analysis

The heatmap below shows the correlation between **step count**, **heart rate**, and **audio exposure level**.  
Each cell reflects the strength of the linear relationship between the variables, where darker red indicates a stronger correlation and blue represents weaker or no correlation.

#### Observations:
- There is a **moderate positive correlation (0.47)** between **Step Count** and **Heart Rate**, suggesting that heart rate tends to increase with physical activity, as expected.
- The correlation between **Audio Level** and both other variables (**Heart Rate** = 0.11, **Step Count** = 0.00) is **extremely weak**, indicating that listening volume is largely independent of physical exertion.
- These results highlight how **audio behavior, movement, and physiological response** can be decoupled and analyzed separately for richer behavioral insights.

![activity_correlation_heatmap (1)](https://github.com/user-attachments/assets/9e69de1c-4b74-4001-9785-8d5ff306eb7f)

##  Hypothesis Testing

### 1. Headphone Audio Level vs Physical Activity

My hypothesis is that **headphone audio exposure is higher when physical activity is low**, and that it tends to decrease when activity (such as steps) increases.

#### Hypothesis:

- **Null Hypothesis (H₀):**  
  There is no difference in headphone audio levels between high-activity and low-activity periods.

- **Alternative Hypothesis (H₁):**  
  Headphone audio levels are significantly higher during periods of low physical activity.

#### Method:

- A threshold was defined to split the data into:
  - **Low Activity**: Step count below the median
  - **High Activity**: Step count above the median
- A one-sided Mann-Whitney U test was applied to compare the distributions of audio levels.

#### Results:

- **U-Statistic**: 62,873.0  
- **P-Value**: 0.0284  
- **Reject** the null hypothesis at 0.05 significance level, indicating that headphone audio levels tend to be significantly **higher during low activity periods**.

#### Summary Statistics:

| Group         | Mean Audio Level (dB) |
|---------------|-----------------------|
| Low Activity  | 87.31 dB              |
| High Activity | 82.94 dB              |

#### Visualization:

The bar chart below shows the average audio levels during low and high activity periods.

![audio_vs_activity_barchart](https://github.com/user-attachments/assets/89370b1c-062e-4d5a-a263-73dfdac9d753)

### 2. Heart Rate During Low and High Step Activity

This hypothesis examines whether average heart rate is significantly higher during high activity (more steps) compared to low activity periods.

#### Hypothesis:

- **Null Hypothesis (H₀):**  
  The average heart rate is the same during high and low physical activity periods.

- **Alternative Hypothesis (H₁):**  
  The average heart rate is higher during high activity periods.

#### Method:

- Activity levels were categorized into **High** and **Low** groups based on the median step count.
- A one-sided t-test was performed at a significance level of 0.05 to test for differences.

#### Results:

- **T-Statistic**: 2.145  
- **P-Value**: 0.0342  
- **Reject** the null hypothesis, indicating that **heart rate is significantly higher** during high physical activity.

#### Summary Statistics:

| Activity Level | Mean Heart Rate (bpm) |
|----------------|------------------------|
| Low Steps      | 81.23 bpm              |
| High Steps     | 85.67 bpm              |

#### Visualization:

The bar chart below shows the average heart rate during low and high physical activity periods.

![heart_rate_vs_steps](https://github.com/user-attachments/assets/d608e49a-6862-4acc-8765-a2d26e38e96c)

### 3. Audio Exposure Level During Low and High Step Activity

This hypothesis investigates whether the average headphone audio level decreases when physical activity (steps) increases.

#### Hypothesis:

- **Null Hypothesis (H₀):**  
  The average audio level is the same during high and low step activity.

- **Alternative Hypothesis (H₁):**  
  The average audio level is lower during high step activity.

#### Method:

- The dataset was split into **High Steps** and **Low Steps** groups using the median step count.
- A one-sided t-test was conducted to determine if audio levels decrease during high step periods.

#### Results:

- **T-Statistic**: -1.692  
- **P-Value**: 0.0473  
- **Reject** the null hypothesis at 0.05 significance level, suggesting that audio levels are significantly lower during high physical activity.

#### Summary Statistics:

| Activity Level | Mean Audio Level (dB) |
|----------------|------------------------|
| Low Steps      | 88.42 dB               |
| High Steps     | 84.95 dB               |

#### Visualization:

The following bar chart shows the difference in average headphone audio levels across different activity levels.
![audio_level_vs_steps](https://github.com/user-attachments/assets/a7a9a787-7529-4f3c-95db-21c8f3929df8)

###  Conclusion for Hypothesis 1

**Hypothesis:** Headphone volume, heart rate, and step count vary depending on the level of physical activity or user context.

The analysis was conducted to evaluate whether audio exposure (volume), heart rate, and step counts significantly change under varying activity levels. The results of the hypothesis testing are summarized below:

- **Step Count & Heart Rate:**  
   A statistically significant increase in heart rate was observed during high step activity (p-value < 0.05).

- **Step Count & Audio Level:**  
   A statistically significant decrease in average headphone audio level was detected during periods of higher step activity (p-value < 0.05).

- **Heart Rate & Audio Level:**  
   Although a slight positive correlation existed, the relationship between heart rate and audio level was not statistically significant (p-value > 0.05).

---

### 🔬 Hypothesis 1: Headphone Volume vs Heart Rate

**Hypothesis:** Higher headphone volume levels correlate with increased heart rate.

To test this hypothesis:

- Pearson correlation was calculated between **Audio Level (dB)** and **Heart Rate (bpm)**.
- A scatter plot was created to visualize the relationship.

**Results:**

- **Correlation Coefficient:** `0.11`  
- **p-value:** > 0.05  

 **Conclusion:** There is a very weak and statistically insignificant correlation between headphone volume and heart rate. This suggests that increased audio exposure does not necessarily raise heart rate.
![audio_vs_heart](https://github.com/user-attachments/assets/d1f54973-5429-4788-a33a-c65ed7bf8ffb)


###  Hypothesis 2: Physical Activity vs Headphone Volume

**Hypothesis:** Higher physical activity (steps) correlates with increased headphone volume exposure.

To test this hypothesis:

- Pearson correlation was calculated between **Step Count** and **Audio Level (dB)**.
- A scatter plot was used to visualize the relationship.

**Results:**

- **Correlation Coefficient:** `0.00`  
- **p-value:** > 0.05  

 **Conclusion:** No correlation was found between step count and headphone volume. Increased physical activity does not seem to influence audio exposure levels in a statistically meaningful way.

![steps_vs_audio](https://github.com/user-attachments/assets/c95e3025-f51f-4664-acbb-02f03bfe6a07)


###  Confusion Matrix Analysis: Predicted vs Actual Step Counts

The confusion matrix below evaluates the classification accuracy of the regression model by comparing actual and predicted **binned step count** values.

- **Diagonal Dominance**:  
  The majority of predictions fall along the diagonal (e.g., `134` samples correctly classified in the first bin), indicating strong agreement between actual and predicted bins.

- **Mild Misclassifications**:  
  Off-diagonal values such as `40` and `13` represent predictions that slightly overestimated step counts, often by just one or two bins — showing the model’s robustness despite minor variance.

- **Sparse Predictions at Higher Ranges**:  
  Fewer samples in higher bins (e.g., > 400 steps) make the model less accurate in those regions, possibly due to class imbalance or data scarcity.

**Conclusion**:  
The model demonstrates high accuracy for low to moderate step count predictions. While some misclassification exists, especially at higher bins, the results indicate reliable performance and point toward targeted improvements for extreme activity ranges.


##  Limitations and Future Work

###  Limitations

- **Single-Participant Dataset**: This study is based on Apple Health data collected from a single user, which limits the generalizability of findings to broader populations.
- **Limited Scope of Variables**: Only three variables — step count, heart rate, and headphone audio exposure — were available. Other important health or contextual metrics (e.g., sleep quality, stress, location, or activity type) were not included.
- **Data Accuracy Concerns**: Audio exposure levels and heart rate data may contain noise due to environmental conditions or inconsistent device usage (e.g., AirPods not properly inserted, heart rate not continuously monitored).
- **Timestamp Synchronization**: Some data sources were not consistently aligned in time, potentially affecting the accuracy of correlation and regression analyses.
- **Short-Term Time Window**: The data spans a limited time frame, which may not reflect long-term behavior or seasonal patterns.

---

###  Future Work

- **Expand Sample Size**: Incorporate data from multiple individuals to increase representativeness and enable broader behavioral trends to be identified.
- **Include Additional Variables**: Integrate other Apple Health metrics such as sleep patterns, workout types, respiratory rate, and mood tracking to uncover deeper relationships between physical activity and physiological/behavioral responses.
- **Improve Audio Data Granularity**: Use app-specific audio exposure breakdowns (e.g., music vs podcast vs video calls) to understand the context of headphone usage more clearly.
- **Longitudinal Analysis**: Extend the study duration to observe trends across months and seasons, providing a better understanding of habitual patterns and lifestyle shifts.
- **Real-Time Analysis Potential**: Develop systems that provide feedback or alerts when unhealthy volume or heart rate patterns are detected.
- **Model Optimization**: Explore more advanced machine learning models and feature engineering to improve predictive performance and personalization.

# Machine learning

## Confusion Matrix for Binned Night Heart Rate

The confusion matrix below compares the predicted Night Heart Rate (HR) values to the actual values, after binning them into defined ranges.

The model used for prediction is a Random Forest Regressor trained on `Morning_HR`, `Afternoon_HR`, and `Evening_HR`.

### Binning Intervals:

- 40–60 bpm  
- 60–70 bpm  
- 70–80 bpm  
- 80–90 bpm  
- 90–100 bpm  
- 100–110 bpm  
- 110–130 bpm

### Interpretation:

- Most predictions are concentrated in the 70–100 bpm range, which reflects the overall distribution of the data.
- The diagonal values indicate correct bin predictions; off-diagonal values indicate misclassifications.
- The highest accuracy is observed in the 70–80 and 80–90 bpm bins, where the predicted values closely align with the actual HR.
- Very few or no samples are seen in extreme low or high HR bins (e.g., 40–60 or 110–130), indicating class imbalance or limited edge cases in the dataset.
  
![confusion_matrix_night_hr (1)](https://github.com/user-attachments/assets/a3d5c554-e5e6-4bfc-94f0-e96cbbb12733)

## Classification: Night Heart Rate Level (Low / Normal / High)

This section summarizes the classification results for predicting Night Heart Rate (HR) levels based on Morning, Afternoon, and Evening HR data using a Random Forest Classifier.

### Classes:
- **Low**: Night_HR < 70 bpm  
- **Normal**: 70 ≤ Night_HR < 90 bpm  
- **High**: Night_HR ≥ 90 bpm

### Results:
- The model achieved an overall accuracy of **44%**, meaning less than half of the predictions matched the actual class.
- The majority of correctly predicted instances fall into the **"Normal"** class, which likely corresponds to the most frequent class in the dataset.
- **Low** and **High** heart rate levels show a higher rate of misclassification, often being predicted as "Normal".

This indicates that while the model can capture average HR trends, it struggles to differentiate between borderline or extreme heart rate levels.

### Confusion Matrix Visualization:

![hr_classification_confusion_matrix](https://github.com/user-attachments/assets/1047bc2e-652a-444a-9ac7-229cb5354c8b)
