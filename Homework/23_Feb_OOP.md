# Code

```py
#1-Two classes that are related Parent-child
#2-One more class
#3-One of the classes in #1 uses the class in #2
#4- Minumum 5 attributes on each class
#5- Minumum 6 methods per class
#6-Minimum 4 objects per class(tests)
#[HL] UML diagram
#Deadline 23 Feb th
#Upload to github

class student:
    '''class for normal studetns'''
    def __init__(self, name:str, age:int,grade:int, school:str):
        self.name = name
        self.score = scores()
        '''Set score attribute use value from the other class(scores)'''
        self.age = age
        self.grade = grade
        self.school = school
    #methods
    def __repr__(self):
        '''Repr method to show name, age, grade and school'''
        return f"{self.name} is {self.age} years old and is a grade {self.grade} student at {self.school}."
    def get_score(self):
        '''Show the score and grade of the person'''
        return f"{self.name} got {self.score} for their {self.grade}  final score."
    def change_score(self,new_score):
        '''change score with the new score or from the value of "scores" class'''
        self.score = new_score
    def graduate(self,new_school):
        '''method to change school when the person is grade 6/9/12'''
        if self.grade != 6 and self.grade != 9 and self.grade!=12:
            return "You cannot graduate yet"
        else:
            old_school = self.school
            self.school = new_school
            return f"{self.name} graduated from {old_school} and is going to go to {new_school}."


    def final_exam(self):
        '''method to increase grade when the status from class scores is not fail or fail == False'''
        if self.score.fail == False:
            self.grade+=1
            return f"{self.name} passed the final exam and will be a grade {self.grade} in the next academic year."
        else:
            return  f"{self.name} failed the final exam and will continue be a grade {self.grade} student."
class ib_student (student):
    '''Child class inherited from parent class student which inherit attribute name age school and score which has to input as IB score for this'''
    def __init__(self, name, age, school:str, IB_score:int,grade, hl_subject:list, sl_subject:list):
        super().__init__(name, age, school, IB_score)
        self.grade =grade
        self.score = IB_score
        self.hl = hl_subject
        self.sl = sl_subject
    def get_subject(self):
        '''Method to get hl and sl subjects'''
        return f"{self.name}'s SL subjects are {', '.join(self.sl)} and HL subjects are {', '.join(self.hl)}. "
    def final_exam(self):
        '''method to show the score of each subject for grade 12'''
        import random
        if self.grade == 11:
            '''when grade is not 12, student cannot take final exam'''
            return f"{self.name} has to be grade 12 to take it."
        if self.grade == 12:
            '''total score set initially as 0'''
            total= 0
            while total != self.score:
                '''The "ranint" will continuously generate score for each subjects and tok in the list and will add in total which while the total is not equal to the inputted score
                it will repeat the program again'''
                sub_score = []
                total = 0
                for i in range (6):
                    mark = random.randint(1,7)
                    sub_score.append(mark)
                    total += mark
                TOK_EE = random.randint(0,3)
                total += TOK_EE
                sub_score.append(TOK_EE)
            print ( f"{self.name} took IB exam.")
            for i in range (3):
                print(f"{self.name} got {sub_score[i]} for {self.sl[i]}.")
            for i in range (3):
                print(f"{self.name} got {sub_score[i+3]} for {self.hl[i]}.")
            print(f"{self.name} got {TOK_EE} for TOK and EE." )
            return f"{self.name}'s final score is {self.score}."
    def change_level(self, new_sl, new_hl):
        '''Switch sl subject and hl subject'''
        if new_sl in self.hl and new_hl in self.sl:
            '''put new hl subject in hl which will switch with old hl. Old hl will go replace the new hl place in sl list'''
            hl = self.hl.index(new_sl)
            sl = self.sl.index(new_hl)
            self.hl[hl] = new_hl
            self.sl[sl]= new_sl
        else:
            print (f"{self.name} doesn't take one or both of the subjects ,so you cannot change.")
    def change_subject(self, old_subject, new_subject):
        '''Switch new inputted subject with old subject'''
        subject = self.sl+self.hl
        if old_subject not in subject and new_subject in subject:
            return "Subjects cannot be change"
        else:
            if old_subject in self.sl:
                self.sl[self.sl.index(old_subject)] = new_subject
            else:
                self.hl[self.hl.index(old_subject)] =  new_subject
    def __repr__(self):
        return f"{self.name} is {self.age} years old and is a grade {self.grade} IB student at {self.school}."
class scores:
    '''New class which will be used with the "student" class'''
    def __init__(self,full:int = 100, total:int=100, fail:bool = False, average:float = 50,comment:str = "good" ):
        '''Set initial value for each attribute'''
        self.full = full
        self.total = total
        self.fail = fail
        self.average = average
        self.comment = comment
    #methods
    def __repr__(self):

        return f"Your score is {self.total} out of {self.full} which is {self.comment}."
    def set_score(self, new_scores):
        '''Set total score to new_scores'''
        self.total= new_scores
    def get_percentage(self):
        '''Get percentage of score by divide the total score with full score and time 100'''
        return  f"{(self.total / self.full)*100} %"
    def compare(self):
        '''Compare your total score with the average'''
        if self.total>self.average:
            return f"Your score is {self.total-self.average} points higher than class's average."
        if self.total<self.average:
            return f"Your score is {self.total - self.average} points lower than class's average."
        elif self.total==self.average:
            return "Your score is the same as the class's average."
    def status(self):
        '''Check status that pass or fail'''
        if self.fail == True:
            return "fail"
        else:
            return "pass"

A = ib_student(name="A", IB_score=38, age=17, school="UWC ISAK Japan",hl_subject=["Biology", "CS", "Econ"], sl_subject=["Self-Taught", "English", "Math"], grade = 11 )
B = ib_student(name="B",age=18,school="Japan International school",IB_score= 45, hl_subject= ["Biology", "Chemistry"," English A"], sl_subject=["Japanese A", "Math AA", "GP"], grade=12)
C = ib_student(name="C",age= 16, school="ABC IB school", IB_score= 25, grade=12, hl_subject=["English A", "Japanese B","Math AA"], sl_subject=["Physics", "Geography", "Psychology"])
D = ib_student(name="D", age=18,school="IB", IB_score=39, grade=12, hl_subject=["Math AA", "Japanese A","Chemistry"], sl_subject=["English B", "Computer Science", "History"])
a = student(name="a", age=12,grade=6, school="Karuizawa school")
b = student(name="b", age = 18, grade=12, school="Nihon High")
c = student(name="c", age=9, grade= 3, school="KK primary")
d = student(name="d", age=6, grade= 1, school="Home School")
A_score = scores()
B_score = scores(full=200, total=50,fail=True,average=189, comment="worst in class")
C_score = scores(full=10,total=7, fail=False,average=7, comment="average")
D_score = scores(total=50,fail=False,average=49,comment="pass")

print(d.get_score())
d.change_score(70)
print(d.get_score())
print(b.final_exam())
print(b)
b.score.set_score(49)
print(b.final_exam())
print(b)
print(a.graduate("University of Karuizawa"))
print(c.graduate("MIT"))

print(A)
print(B.get_subject())
B.change_level("Biology", "Math AA")
print(B.get_subject())
print(C.get_subject())
C.change_subject("Japanese B", "Spanish B")
print(C.get_subject())
print(D.final_exam())

print(A_score)
A_score.set_score(99)
print(A_score)
print(B_score.status())
print(C_score.compare())
print(D_score.get_percentage())
```

# Test
<img width="1440" alt="23 Feb" src="https://user-images.githubusercontent.com/82266864/155056001-dffc1f21-8ed5-4c92-b110-e4399d7966f8.png">

# UML(HL)
<img width="1440" alt="UML feb 23" src="https://user-images.githubusercontent.com/82266864/155055990-0e665a6f-f1df-412b-ab08-420ab1e1e335.png">
