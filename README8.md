README 


README: Professors and Courses Data Manipulation Project

This project involves data manipulation tasks using Python’s Pandas library. It demonstrates how to work with two datasets: one containing professors’ details and another with their associated courses. The code performs various operations, including data creation, transformation, merging, and analysis.

Table of Contents

	1.	Project Overview
	2.	Technologies Used
	3.	Features
	4.	How to Use
	5.	Detailed Explanation of Code
	6.	Sample Output
	7.	Future Scope

Project Overview

This project demonstrates:
	•	Data Creation: Creating two Pandas DataFrames: one for professors’ details and another for their courses.
	•	Data Transformation: Adding a new column to extract professors’ last names using string operations.
	•	Data Combination: Merging the two datasets based on the professor column.
	•	String Operations: Creating initials for professors and manipulating text data.

Technologies Used

	•	Python: Version 3.8 or higher.
	•	Pandas: Data manipulation and analysis.
	•	Matplotlib (optional): For data visualization.

Features

	1.	Create DataFrames:
	•	One DataFrame contains details about professors, their departments, and ages.
	•	Another DataFrame contains professors and the courses they teach.
	2.	Combine DataFrames: Merging the professors’ details with the courses data.
	3.	String Operations:
	•	Extracting professors’ last names.
	•	Creating a column for professors’ initials (first name and last name initials).
	4.	Data Analysis: Simple operations like finding and displaying results for extracted and merged data.

How to Use

	1.	Clone this repository or copy the provided code into your Python environment.
	2.	Ensure the required Python libraries (pandas) are installed.
	3.	Run the code to generate and manipulate the datasets.
	4.	Review the outputs displayed in the console.

Detailed Explanation of Code

Step 1: Create Professors DataFrame

data = {
    'professor': ['Ludmila Kuncheva', 'Antonio Torralba', 'Manuel Gonzalez', 'Bastian Leibe'],
    'department': ['Computer Science', 'Computer Vision', 'AI & Robotics', 'Autonomous Systems'],
    'age': [45, 50, 47, 38]
}
df = pd.DataFrame(data)

Step 2: Create Courses DataFrame

courses_data = {
    'professor': ['Ludmila Kuncheva', 'Antonio Torralba', 'Manuel Gonzalez', 'Bastian Leibe'],
    'courses': ['Machine Learning', 'Computer Vision', 'AI Programming', 'Self-Driving Cars']
}
df_courses = pd.DataFrame(courses_data)

Step 3: Combine DataFrames

df_combined = pd.merge(df, df_courses, on='professor')
print("Combined DataFrame:")
print(df_combined)

Step 4: Extract Last Names

df['professor_last_name'] = df['professor'].apply(lambda x: x.split()[-1])
print("DataFrame with Last Name Column:")
print(df)

Step 5: Create Professors’ Initials

df['professor_initials'] = df['professor'].apply(lambda x: f"{x.split()[0][0]}.{x.split()[-1][0]}.")
print("DataFrame with Professors' Initials:")
print(df)

Sample Output

Original Professors DataFrame

professor	department	age
Ludmila Kuncheva	Computer Science	45
Antonio Torralba	Computer Vision	50
Manuel Gonzalez	AI & Robotics	47
Bastian Leibe	Autonomous Systems	38

Combined DataFrame

professor	department	age	courses
Ludmila Kuncheva	Computer Science	45	Machine Learning
Antonio Torralba	Computer Vision	50	Computer Vision
Manuel Gonzalez	AI & Robotics	47	AI Programming
Bastian Leibe	Autonomous Systems	38	Self-Driving Cars

DataFrame with Extracted Last Names

professor	department	age	professor_last_name
Ludmila Kuncheva	Computer Science	45	Kuncheva
Antonio Torralba	Computer Vision	50	Torralba
Manuel Gonzalez	AI & Robotics	47	Gonzalez
Bastian Leibe	Autonomous Systems	38	Leibe

DataFrame with Professors’ Initials

professor	department	age	professor_initials
Ludmila Kuncheva	Computer Science	45	L.K.
Antonio Torralba	Computer Vision	50	A.T.
Manuel Gonzalez	AI & Robotics	47	M.G.
Bastian Leibe	Autonomous Systems	38	B.L.

Future Scope

	1.	Data Visualization: Use libraries like Matplotlib or Seaborn to visualize data trends.
	2.	Additional Data: Add more fields like research areas, publications, or awards for further analysis.
	3.	Advanced Analysis: Use machine learning techniques to analyze professors’ profiles and course popularity.

This project is a great starting point for learning how to manipulate and analyze relational datasets using Python. Feel free to modify and extend the code as needed!