# Module_8_Exercise_Inheritance
You are given two classes, Person and Student, where Person is the base class and Student is the derived class. Completed code for Person and a declaration for Student are provided for you in the editor. Observe that Student inherits all the properties of Person.

Complete the Student class by writing the following:
A Student class constructor, which has 4 parameters:
- A string, firstName
- A string, lastName
- An integer, id
An integer array (or vector) of test scores, scores

A char calculate() method that calculates a Student object's average and returns the grade character representative of their calculated average:
A | 90-100
B | 80-89
C | 70-79
D | 60-69
F | <60

Solution
class Person:
	def __init__(self, firstName, lastName, idNumber):
		self.firstName = firstName
		self.lastName = lastName
		self.idNumber = idNumber
	def printPerson(self):
		print("Name:", self.lastName + ",", self.firstName)
		print("ID:", self.idNumber)

class Student(Person):

    def __init__(self, firstName, lastName, idNum, scores):
        Person.__init__(self, firstName, lastName, idNum)
        self.scores = scores

    def calculate(self):
        a = sum(scores) / len(scores)
        if 90 <= a <= 100:
            return "A"
        elif 80 <= a < 89:
            return "B"
        elif 70 <= a < 79:
            return "C"
        elif 60 <= a < 69:
            return "D"
        elif < 60:
            return "F"

line = input().split()
firstName = line[0]
lastName = line[1]
idNum = line[2]
numScores = int(input()) # not needed for Python
scores = list( map(int, input().split()) )
s = Student(firstName, lastName, idNum, scores)
s.printPerson()
print("Grade:", s.calculate())
