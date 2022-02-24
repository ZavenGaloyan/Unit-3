```py
'''
4 properties of OOP programming paradigm
1.Encapsulation
2.Abstraction
3.Inheritance
4.Polymorphism

Componenets of UML diagram for classes.
1. In the first row from the top the class name of the object will be stated
2. The second row will be used to state all the attributes of that classes
3. In the last row will be all the methods of that class
'''

class Scores:
    '''OOP class for scores'''
    def __init__(self, results:list[int])->int:
        '''1 attribute-result'''
        self.results = results

    #methods
    def getAverage(self):
        '''Method to calculate the average amount of the  number in the list'''
        total = 0
        '''Variable to collect the total amount in the list'''
        for i in range(len(self.results)):
            '''Repeat for the range equal to numbers of objects un list'''
            total += self.results[i]
            '''Collect them in total and repeat until end of loop'''
        avg = total/len(self.results)
        '''Divide total by the numbers of objects'''
        return round(avg)

score_1 = Scores([1,2,3,4,5,6,4])
print(score_1.getAverage())#expected 4
score_2 = Scores([102,304,20,10,30,4])
print(score_2.getAverage())#expected 78
```

# Test
<img width="1440" alt="quiz36" src="https://user-images.githubusercontent.com/82266864/155439331-6f3bd2fe-596e-4807-860f-69316c752a02.png">
