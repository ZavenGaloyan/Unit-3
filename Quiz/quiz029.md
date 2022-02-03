# Code
<img width="583" alt="Quiz29" src="https://user-images.githubusercontent.com/82266864/152158626-499626e4-31a4-4ba5-9ccf-38d2859b6c25.png">

# Output

<img width="253" alt="Result" src="https://user-images.githubusercontent.com/82266864/152158673-a9f0f326-f9ba-4238-9875-f0273312a4a6.png">

# OOP
```py
class quiz_29:
    #attributes
    def __init__(self, number:int):
        self.number = number
    #methods
    def solve(self):
        solution = 0
        for i in range (1, self.number+1):
            if self.number %i == 0 and i %2 ==0:
                solution +=1
        return solution

test_case_1 = quiz_29(number = 8)
print(test_case_1.solve())  # should produce 3
```

# Output
<img width="1143" alt="OOP q29" src="https://user-images.githubusercontent.com/82266864/152270011-f002f91b-b160-42c9-89c0-903c5049ce49.png">
