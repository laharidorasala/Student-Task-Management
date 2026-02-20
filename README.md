students = []

#Enter the details of the student
def student_task():
        name=input("enter the name:")
        rollnumber=input("enter the roll number:")
        marks1 = int(input("enter the marks 1:")) 
        marks2 =int(input( "enter the marks 2:")) 
        #total marks 
        total=marks1+marks2
        #average of two subjects
        average=total/2
    
        print("name", name)
        print("rollnumber", rollnumber)
        print("marks1,marks2 =", total)
        print("average",average)
    
        return name, rollnumber, total,average
        
#add the students to the list
while True:
    students.append(student_task())
    choice=input("do you want to add student:(yes/no)")
    if choice != "yes":
       break
    

#print all the students
print("all the students:",students)

