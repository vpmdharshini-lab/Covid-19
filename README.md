COVID-19 Country-Wise Data Analysis using Python
Project Overview

This project analyzes a COVID-19 country-wise dataset using Python. The analysis includes data cleaning, statistical summaries, and visualizations to understand the distribution of confirmed cases, deaths, recoveries, and active cases across different countries.

The project is implemented in Google Colab using Pandas, NumPy, Matplotlib, and Seaborn.

Objectives
Load and preprocess COVID-19 data.
Perform exploratory data analysis (EDA).
Calculate global COVID-19 statistics.
Visualize affected countries and case distributions.
Examine relationships between confirmed cases, deaths, recoveries, and active cases.
Technologies Used
Python
Google Colab
Pandas
NumPy
Matplotlib
Seaborn
Dataset

File Name: country_wise_latest.csv

Dataset Attributes
Country/Region
Confirmed
Deaths
Recovered
Active
New cases
New deaths
New recovered
Deaths / 100 Cases
Recovered / 100 Cases
Deaths / 100 Recovered
Confirmed last week
1 week change
1 week % increase
WHO Region
Project Workflow
1. Import Required Libraries

The project imports:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
2. Upload Dataset

The dataset is uploaded using Google Colab:

from google.colab import files
uploaded = files.upload()
3. Load Dataset

The CSV file is loaded into a DataFrame:

data = pd.read_csv("country_wise_latest.csv")
4. Data Preprocessing
Rename columns.
Select required columns.
Convert date columns (if available).
Remove missing values.
Remove duplicate records.
data = data.rename(columns={
    "Country/Region": "Country",
    "ObservationDate": "Date"
})
5. Data Exploration

Display:

First 5 rows
Column names
Dataset information
Statistical summary
data.head()
data.info()
data.describe()
Analysis Performed
Global COVID-19 Statistics

The project calculates:

Total Confirmed Cases
Total Deaths
Total Recovered Cases
Results
Metric	Value
Total Confirmed Cases	16,480,485
Total Deaths	654,036
Total Recovered	9,468,087
Visualizations
1. Top 10 Affected Countries
<img width="736" height="671" alt="Screenshot 2026-06-04 205110" src="https://github.com/user-attachments/assets/24b87cc8-f175-48ef-a49a-96e8edb1f0c5" />


A bar chart showing countries with the highest number of confirmed cases.

top_countries.plot(kind="bar")
2. COVID-19 Case Distribution
<img width="486" height="526" alt="Screenshot 2026-06-04 205121" src="https://github.com/user-attachments/assets/82c2bc9c-b29b-4df7-ad92-31ada31cca5f" />


Pie chart displaying proportions of:

Confirmed Cases
Deaths
Recovered Cases
totals.plot(kind="pie")
3. Confirmed Cases vs Deaths
<img width="734" height="578" alt="Screenshot 2026-06-04 205131" src="https://github.com/user-attachments/assets/7b7545f1-cfbc-4d01-be1a-a25641d75d27" />


Scatter plot showing the relationship between confirmed cases and deaths.

sns.scatterplot(x="Confirmed", y="Deaths")
4. Correlation Heatmap
<img width="691" height="576" alt="Screenshot 2026-06-04 205143" src="https://github.com/user-attachments/assets/234dc9ba-0749-4eab-b9c1-4dd9e3265132" />

Displays correlations among:

Confirmed
Deaths
Recovered
Active
sns.heatmap(corr, annot=True)
5. COVID-19 Trend Analysis
<img width="789" height="578" alt="Screenshot 2026-06-04 205153" src="https://github.com/user-attachments/assets/db74d0ee-232d-4618-a76e-e9270842dd17" />


Plots confirmed cases over time if a Date column exists.

trend = data.groupby("Date")["Confirmed"].sum()
Key Findings
The dataset contains information from 187 countries/regions.
Total confirmed cases exceeded 16 million.
Total recoveries were approximately 9.4 million.
Deaths accounted for a smaller proportion compared to recoveries.
Strong positive correlations exist between confirmed cases and deaths.
Some countries experienced significantly higher case counts than others.
Output

The program generates:

Dataset overview
Summary statistics
Bar Chart
Pie Chart
Scatter Plot
Correlation Heatmap
Trend Analysis Graph (if date data is available)

At the end of execution:

Analysis Completed Successfully!
Limitations
The dataset does not contain an actual Date column, so the trend analysis graph may not display meaningful results.
Data represents a snapshot of COVID-19 statistics rather than daily historical records.
Future Enhancements
Add time-series COVID-19 datasets.
Create interactive dashboards using Plotly or Streamlit.
Predict future cases using Machine Learning models.
Analyze COVID-19 trends by WHO Region.
Compare recovery and mortality rates among countries.
Conclusion

This project demonstrates how Python can be used for COVID-19 data analysis through data cleaning, statistical exploration, and visualization. The generated insights help understand the global impact of COVID-19 and identify the most affected countries.
