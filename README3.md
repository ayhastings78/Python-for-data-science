Student Registration and GPA Management System

This Python program allows you to manage a list of students, courses, their enrollment status, and assigned grades. It also calculates the GPA of each student based on the courses they are enrolled in and the grades they have received.

Features

	•	Add Students and Courses: Add students and courses to the system.
	•	Enroll Students in Courses: Enroll students in courses and track their enrollment.
	•	Assign Grades: Assign grades to students for specific courses.
	•	Drop Students from Courses: Remove students from enrolled courses.
	•	Display Enrolled Courses and Grades: Show all courses a student is registered for along with their grades.
	•	Calculate GPA: Automatically calculate and display the GPA for a student based on their grades.

Classes and Methods

Student Class

	•	__init__(self, name, student_id, address=None): Initializes a student with a name, student ID, and an optional address.
	•	enroll(self, course): Enrolls the student in a specified course.
	•	drop_course(self, course): Drops the student from a specified course.
	•	assign_grade(self, course, grade): Assigns a grade to the student for a specified course.
	•	show_registered(self): Displays the list of courses the student is enrolled in and their grades.
	•	calculate_gpa(self): Calculates and returns the student’s GPA based on their grades.

Course Class

	•	__init__(self, course_name, course_type, students=None): Initializes a course with a name, type, and an optional list of students.
	•	add_student(self, student): Adds a student to the course.
	•	remove_student(self, student): Removes a student from the course.
	•	show_students(self): Displays the list of students enrolled in the course.

Registration Class

	•	__init__(self): Initializes the registration system with a list of students and courses.
	•	add_student(self, student): Adds a student to the system.
	•	add_course(self, course): Adds a course to the system.
	•	enroll_student_in_course(self, student_name, course_name): Enrolls a student in a specified course.
	•	drop_student_from_course(self, student_name, course_name): Drops a student from a specified course.
	•	assign_grade_to_student(self, student_name, course_name, grade): Assigns a grade to a student for a specific course.
	•	show_all_enrolled_courses(self, student_name): Displays all the courses a student is enrolled in along with their grades.
	•	calculate_student_gpa(self, student_name): Calculates and displays the GPA for a specific student.


Example Usage

# Create students
student1 = Student("Alice", "S001")
student2 = Student("Bob", "S002")

# Create courses
course1 = Course("Mathematics", "Core")
course2 = Course("History", "Elective")

# Create registration system
registration = Registration()

# Add students to the registration system
registration.add_student(student1)
registration.add_student(student2)

# Add courses to the registration system
registration.add_course(course1)
registration.add_course(course2)

# Enroll students in courses
registration.enroll_student_in_course("Alice", "Mathematics")
registration.enroll_student_in_course("Bob", "History")

# Assign grades to students
registration.assign_grade_to_student("Alice", "Mathematics", 90)
registration.assign_grade_to_student("Bob", "History", 85)

# Show enrolled courses and grades for a student
registration.show_all_enrolled_courses("Alice")

# Calculate GPA
registration.calculate_student_gpa("Alice")
registration.calculate_student_gpa("Bob")

Output Example:

Student Alice has been added.
Student Bob has been added.
Course Mathematics has been added.
Course History has been added.
Alice has enrolled in Mathematics.
Bob has enrolled in History.
Assigned grade 90 to Alice for Mathematics.
Assigned grade 85 to Bob for History.
Alice is enrolled in the following courses and grades:
- Mathematics: 90
Alice's GPA is: 90.0
Bob's GPA is: 85.0