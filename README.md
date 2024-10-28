# Python-final-Project
students = {}
courses = {}
faculty = {}

# 1. Student Management with Interactive Input
def add_student_interactive():
    student_id = int(input("Enter Student ID: "))
    name = input("Enter Student Name: ")
    course = input("Enter Course: ")
    academic_performance = input("Enter Academic Performance: ")
    students[student_id] = {
        'Name': name,
        'Course': course,
        'Academic Performance': academic_performance
    }
    print(f"Student {name} added successfully.")

def view_students():
    if not students:
        print("No students found.")
    else:
        for student_id, details in students.items():
            print(f"ID: {student_id}, Name: {details['Name']}, Course: {details['Course']}, Performance: {details['Academic Performance']}")

def update_student_interactive():
    student_id = int(input("Enter Student ID to update: "))
    if student_id in students:
        print("Current details:", students[student_id])
        new_name = input("Enter new name (or press Enter to keep current): ")
        new_course = input("Enter new course (or press Enter to keep current): ")
        new_performance = input("Enter new performance (or press Enter to keep current): ")
        if new_name:
            students[student_id]['Name'] = new_name
        if new_course:
            students[student_id]['Course'] = new_course
        if new_performance:
            students[student_id]['Academic Performance'] = new_performance
        print(f"Student {student_id} updated successfully.")
    else:
        print(f"Student ID {student_id} not found.")

# 2. Course Management with Interactive Input
def add_course_interactive():
    course_id = int(input("Enter Course ID: "))
    course_name = input("Enter Course Name: ")
    faculty_assigned = input("Enter Faculty Assigned: ")
    courses[course_id] = {
        'Course Name': course_name,
        'Faculty Assigned': faculty_assigned
    }
    print(f"Course {course_name} added successfully.")

def view_courses():
    if not courses:
        print("No courses found.")
    else:
        for course_id, details in courses.items():
            print(f"ID: {course_id}, Name: {details['Course Name']}, Faculty: {details['Faculty Assigned']}")

# 3. Faculty Management with Interactive Input
def add_faculty_interactive():
    faculty_id = int(input("Enter Faculty ID: "))
    faculty_name = input("Enter Faculty Name: ")
    subject = input("Enter Subject: ")
    faculty[faculty_id] = {
        'Name': faculty_name,
        'Subject': subject
    }
    print(f"Faculty {faculty_name} added successfully.")

def view_faculty():
    if not faculty:
        print("No faculty members found.")
    else:
        for faculty_id, details in faculty.items():
            print(f"ID: {faculty_id}, Name: {details['Name']}, Subject: {details['Subject']}")

# Interactive Menu
def university_management_system():
    print("---- University Management System ----")
    while True:
        print("\n1. Add Student\n2. View Students\n3. Update Student\n4. Add Course\n5. View Courses\n6. Add Faculty\n7. View Faculty\n8. Exit")
        choice = input("Enter your choice: ")

        if choice == '1':
            add_student_interactive()
        elif choice == '2':
            view_students()
        elif choice == '3':
            update_student_interactive()
        elif choice == '4':
            add_course_interactive()
        elif choice == '5':
            view_courses()
        elif choice == '6':
            add_faculty_interactive()
        elif choice == '7':
            view_faculty()
        elif choice == '8':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please try again.")

# Run the University Management System
university_management_system()
