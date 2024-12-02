README 

for Data Analysis Scripts

Description

This repository contains Python scripts to analyze data from the Netflix dataset and the Titanic dataset. The scripts leverage the pandas library to process data and extract meaningful insights.

Files

	1.	Netflix Data Analysis Script
	2.	Titanic Data Analysis Script

Prerequisites

	•	Python 3.6+
	•	Pandas library installed (pip install pandas)
	•	Dataset files:
	•	Netflix: netflix_titles.csv
	•	Titanic: Provide your Titanic dataset with appropriate columns.

Netflix Data Analysis

Overview

This script analyzes the Netflix dataset to extract key metrics such as:
	1.	The count of missing ratings.
	2.	Number of films released in 2021 corresponding to a specific country (default: United States).
	3.	Count of movies in 2020 with complete information (no missing data).
	4.	The year with the most titles.
	5.	Average number of releases from 2010 onwards.

Usage

	1.	Place your Netflix dataset (netflix_titles.csv) in the same directory as the script or update the file path in the netflix_file_path variable.
	2.	Run the script to generate insights.

Code Snippet

import pandas as pd

# Load the Netflix dataset
netflix_file_path = 'netflix_titles.csv'
netflix_data = pd.read_csv(netflix_file_path)

# Key Analysis
missing_ratings = netflix_data['rating'].isnull().sum()
films_2021_user_country = netflix_data[(netflix_data['release_year'] == 2021) & (netflix_data['country'] == 'United States')].shape[0]
movies_2020_full_info = netflix_data[(netflix_data['release_year'] == 2020) & (netflix_data.notnull().all(axis=1))].shape[0]
year_with_most_titles = netflix_data['release_year'].value_counts().idxmax()
average_releases_from_2010 = netflix_data[netflix_data['release_year'] >= 2010]['release_year'].value_counts().mean()

# Results
print("Netflix Data Analysis Results:")
print(f"1. Missing Ratings: {missing_ratings}")
print(f"2. Films in 2021 (United States): {films_2021_user_country}")
print(f"3. Movies in 2020 with Full Information: {movies_2020_full_info}")
print(f"4. Year with Most Titles: {year_with_most_titles}")
print(f"5. Average Releases (2010 onward): {average_releases_from_2010:.2f}")

Titanic Data Analysis

Overview

This script analyzes the Titanic dataset to calculate:
	1.	Gender-based survival percentages.
	2.	Survival percentages grouped by gender and passenger class.

Usage

	1.	Place your Titanic dataset in the same directory as the script or provide its file path.
	2.	Ensure the dataset contains the following columns:
	•	Sex (gender)
	•	Pclass (passenger class)
	•	Survived (0 = did not survive, 1 = survived)
	3.	Run the script to compute and display the results.

Code Snippet

import pandas as pd

# Load the Titanic dataset
# df = pd.read_csv('path_to_titanic_dataset.csv')

# Calculate gender-based survival percentages
gender_survival = df.groupby('Sex')['Survived'].mean() * 100
print("Gender-Based Survival Percentage:")
print(gender_survival)

# Calculate survival percentage grouped by gender and class
gender_class_survival = df.groupby(['Sex', 'Pclass'])['Survived'].mean() * 100
print("\nSurvival Percentage Grouped by Gender and Class:")
print(gender_class_survival)

# Optional: Display results in tabular format
gender_class_survival_df = gender_class_survival.reset_index(name='Survival Percentage')
print("\nTabular Format:")
print(gender_class_survival_df)

Results Interpretation

Netflix Analysis

	•	Missing Ratings: Total rows with missing values in the rating column.
	•	Films in 2021 by Country: How many films were released in the specified country in 2021.
	•	Complete Movies in 2020: Count of movies in 2020 with no missing data.
	•	Most Titles Year: The year with the highest number of titles in the dataset.
	•	Average Releases Post-2010: Average annual release count from 2010 onward.

Titanic Analysis

	•	Gender Survival Percentage: Proportion of survivors by gender.
	•	Gender-Class Survival Percentage: Proportion of survivors based on gender and passenger class.

How to Run

	1.	Install Python and pandas if not already installed.
	2.	Place the datasets in the appropriate directory or specify their paths in the scripts.
	3.	Run the scripts using a Python IDE or terminal.

License

This project is open-source and can be freely used and modified. Attribution is appreciated! 😊