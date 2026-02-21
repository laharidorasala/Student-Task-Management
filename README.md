students = []

# Function to add a student
def add_student():
    name = input("Enter the name: ")
    rollnumber = input("Enter the roll number: ")
    marks1 = int(input("Enter marks 1: "))
    marks2 = int(input("Enter marks 2: "))
    
    total = marks1 + marks2
    average = total / 2
    
    student = (name, rollnumber, total, average)
    students.append(student)
    print(f"\nStudent {name} added successfully!\n")

# Function to view all students
def view_students():
    if not students:
        print("\nNo students found.\n")
        return
    print("\nAll Students:")
    for student in students:
        print(f"Name: {student[0]}, Roll No: {student[1]}, Total: {student[2]}, Average: {student[3]}")
    print()

# Function to search a student by roll number
def search_student():
    roll = input("Enter roll number to search: ")
    for student in students:
        if student[1] == roll:
            print(f"\nStudent Found: Name: {student[0]}, Roll No: {student[1]}, Total: {student[2]}, Average: {student[3]}\n")
            return
    print("\nStudent not found!\n")

# Function to delete a student by name
def delete_student():
    name = input("Enter name of student to delete: ")
    for student in students:
        if student[0] == name:
            students.remove(student)
            print(f"\nStudent {name} deleted successfully!\n")
            return
    print("\nStudent not found!\n")

# Function to update student marks by roll number
def update_student():
    roll = input("Enter roll number to update marks: ")
    for i, student in enumerate(students):
        if student[1] == roll:
            marks1 = int(input("Enter new marks 1: "))
            marks2 = int(input("Enter new marks 2: "))
            total = marks1 + marks2
            average = total / 2
            students[i] = (student[0], roll, total, average)
            print(f"\nMarks updated successfully for {student[0]}!\n")
            return
    print("\nStudent not found!\n")

# Menu system
while True:
    print("===== Student Management System =====")
    print("1. Add Student")
    print("2. View All Students")
    print("3. Search Student by Roll Number")
    print("4. Delete Student by Name")
    print("5. Update Student Marks")
    print("6. Exit")

    choice = input("Enter your choice (1-6): ")

    if choice == "1":
        add_student()
    elif choice == "2":
        view_students()
    elif choice == "3":
        search_student()
    elif choice == "4":
        delete_student()
    elif choice == "5":
        update_student()
    elif choice == "6":
        print("Exiting program. Goodbye!")
        break
    else:
        print("Invalid choice! Please enter a number between 1-6.\n")

