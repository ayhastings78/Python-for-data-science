README 

Here’s a sample README file for the provided code and functionality:

Professors and Courses Data Manipulation

This project demonstrates data manipulation tasks using Python and Pandas. The goal is to perform various operations on professors’ and their associated courses’ data, including creating DataFrames, extracting and transforming data, and combining datasets.

Table of Contents

	1.	Project Overview
	2.	Requirements
	3.	Code Features
	4.	How to Run the Code
	5.	Output
	6.	Future Enhancements

Project Overview

This project covers the following:
	1.	Creating two Pandas DataFrames for professors and their respective courses.
	2.	Combining and transforming data using string operations and DataFrame methods.
	3.	Extracting and creating a new column (professor_last_name) containing the last name of each professor.

Requirements

	•	Python 3.8+
	•	Libraries:
	•	Pandas
	•	Any Python IDE or environment (e.g., Jupyter Notebook, VS Code, etc.)

Code Features

1. Creating DataFrames

# Professors' data
data = {
    'professor': ['Ludmila Kuncheva', 'Antonio Torralba', 'Manuel Gonzalez', 'Bastian Leibe'],
    'department': ['Computer Science', 'Computer Vision', 'AI & Robotics', 'Autonomous Systems'],
    'age': [45, 50, 47, 38]
}
df = pd.DataFrame(data)

# Courses data
courses_data = {
    'professor': ['Ludmila Kuncheva', 'Antonio Torralba', 'Manuel Gonzalez', 'Bastian Leibe'],
    'courses': ['Machine Learning', 'Computer Vision', 'AI Programming', 'Self-Driving Cars']
}
df_courses = pd.DataFrame(courses_data)

2. Data Transformation

Extracting Last Names

Using string operations, a new column is created to store the last names of professors:

# Extract the last name of each professor and create a new column
df['professor_last_name'] = df['professor'].apply(lambda x: x.split()[-1])

# Display the updated DataFrame
print("DataFrame with Last Name Column:")
print(df)

Example Output:

professor	department	age	professor_last_name
Ludmila Kuncheva	Computer Science	45	Kuncheva
Antonio Torralba	Computer Vision	50	Torralba
Manuel Gonzalez	AI & Robotics	47	Gonzalez
Bastian Leibe	Autonomous Systems	38	Leibe

How to Run the Code

	1.	Ensure all dependencies are installed (Python and Pandas).
	2.	Copy the provided code into a Python file or Jupyter Notebook.
	3.	Run the script and observe the outputs in the console.

Output

The output includes:
	1.	DataFrames: A DataFrame for professors’ details and another for their courses.
	2.	Last Name Column: A new column, professor_last_name, containing the extracted last names of professors.

Future Enhancements

	•	Combine the professors and courses DataFrames into a single unified dataset.
	•	Perform additional analytics, such as finding professors by department or course.
	•	Visualize the data using tools like Matplotlib or Seaborn.

This README file explains the project’s context and functionality clearly. Let me know if you need adjustments or additions!