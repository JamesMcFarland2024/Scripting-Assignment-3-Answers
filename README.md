# Scripting-Assignment-3-Answers

# Question 1
class Car:
def __init__(self,year,model,make):
    self.__year=year
    self.__model=model
    self.__make =make
    self.__speed =0
def Accelerate(self):
    self.__speed +=5
def Brake(self):
    self.__speed -=5

def get_speed(self):
    return self.__speed

def main():
  c=Car(2015,"Ford","X5")
  print("Accelerate")
  c.Accelerate()
  print("Accelerate")
  c.Accelerate()
  print("Accelerate")
  c.Accelerate()
  print(f"Current speed is {c.get_speed()}")
  print("Brake")
  c.Brake()
  print(f"Current speed is {c.get_speed()}")
main()

# Question 2
#create a class named Employee
class Employee:

#initialize the attributes
def __init__(self, name, id, department, title):
    self.__name = name
    self.__id = id
    self.__department = department
    self.__title = title
    
#set the attributes
def set_name(self, name):
    self.__name = name
def set_id(self, id):
    self.__id = id
def set_department(self, department):
    self.__department = department
def set_title(self, title):
    self.__title = title
    
#return the attributes
def get_name(self):
    return self.__name
def get_id(self):
    return self.__id
def get_department(self):
    return self.__department
def get_title(self):
    return self.__title
    
#return the objects state as a string
def __str__(self):
    return 'Name: ' + self.__name + \
           '\nID number: ' + self.__id + \
           '\nDepartment: ' + self.__department + \
           '\nTitle: ' + self.__title

import emp

def main():
    #Create three employee objects
    emp1 = emp.Employee('name', 'id', 'department', 'title')
    emp2 = emp.Employee('name', 'id', 'department', 'title')
    emp3 = emp.Employee('name', 'id', 'department', 'title')

    #create three Employee objects for each attribute
    emp1.set_name('Susan Meyers')
    emp1.set_id('47899')
    emp1.set_department('Accounting')
    emp1.set_title('Vice President')

    emp2.set_name('Mark Jones')
    emp2.set_id('39119')
    emp2.set_department('IT')
    emp2.set_title('Programmer')

    emp3.set_name('Joy Rogersr')
    emp3.set_id('81774')
    emp3.set_department('Manufacturing')
    emp3.set_title('Engineer')

    print()
    print(emp1)
    print()
    print(emp2)
    print()
    print(emp3)
    main()
    
  # Question 3
  class Employee:
     def __init__(self, firstname, lastname):
         self.firstname = firstname
         self.lastname = lastname
         #Complete the code!
         self.fullname = firstname + " " + lastname
         self.email = firstname.lower() + "." + lastname.lower() + "@company.com"

# Question 4

print("*****This Program Contains Student Information*****")

D = dict()

n = int(input('How many student records you want to store? '))

#Add student information to the dictionary
for i in range(0,n):
  x, y = input("Enter the complete name (First and last name) of student: ").split()
  z = input("Enter contact number: ")
  m = input('Enter Marks: ')
  D[x, y] = (z, m)

#define a function for shorting names based on first name
def sort():
      ls = list()
      #fetch key and value using items() method
      for sname,details in D.items():
          #store key parts as an tuple
          tup = (sname[0],sname[1])
          
          #add tuple to the list
          ls.append(tup)
    
    #sort the final list of tuples
    ls = sorted(ls)
    for i in ls:

            #print first name and second name
            print(i[0],i[1])
    return
    
#define a function for finding the minimum marks in stored data
def minmarks():
    ls = list()
    #fetch key and value using items() methods
    for sname,details in D.items():
        #add details second element
        #(marks) to the list
        ls.append(details[1])
    #sort the list elemnts
    ls = sorted(ls)
    print("Minimum marks: ", min(ls))

    return
#define a function for searching student contact number
def searchdetail(fname):
    ls = list()
    
    for sname,details in D.items():
        tup=(sname,details)
        ls.append(tup)

    for i in ls:
        if i[0][0] == fname:
           print(i[1][0])
    return
    
#define a function for asking the options
def option():
    choice = int(input('Enter the operation detail: \n \
    1: Sorting using first name \n \
    2: Finding Minimum marks \n \
    3: Search contact number using first name: \n \
    4: Exit\n \
    Option: '))

    if choice == 1:
       #function call
       sort()
       print('Want to perform some other operation? Y or N: ')
       inp = input()
       if inp == 'Y':
          option()
       #exit function call
       exit()

  elif choice == 2:
       minmarks()
       print('Want to perform some other operation? Y or N: ')
       inp = input()
       if inp == 'Y':
          option()
       exit()

  elif choice == 3:
       first = input('Enter first name of student: ')
       searchdetail(first)
        
       print('Want to perform some other operation? Y or N: ')
       inp = input()
       if inp == 'Y':
          option()
       exit()

  else:
    print('Thank you! Goodbye!')
    exit()
option()
