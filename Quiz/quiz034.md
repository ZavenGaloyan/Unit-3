# Code
```py
class Polygon:
    '''Parent class call polygons'''
    def __init__(self,no_of_sides):
        self.n = no_of_sides
        '''numbers of sides that polygons have'''
        self.sides = []
        '''list to record the length of each sides'''
    #methods
    def inputSides(self):
        '''method to input the length of each side of that specific polygon.'''
        for i in range(self.n):
            self.sides.append(int(input(f"Enter side{i+1}")))
    def showSides(self):
        '''method to show the length of each side of that polygon.'''
        for i in range(self.n):
            print(f"Side {i+1} is {self.sides[i]}")
class Triangle(Polygon):
    '''Child class of polygon which is inherited from it for Triangle'''
    def __init__(self, side_a, side_b, side_c, no_of_sides = 3,):
        '''This will have attribute as the length of each side ,so user doesn't have to input the side later.'''
        super().__init__(no_of_sides)
        '''Inherit attribute no_of_sides from polygon but will be setted initially to 3 as triangle has 3 sides.'''
        self.a = side_a
        self.b = side_b
        self.c = side_c
        '''new attributes only in this child class.'''
        self.sides = [self.a, self.b, self.c]
    #methods
    def area(self):
        '''method to find the total area of triangle and to check whether it is real triangle or not.'''
        S = (self.a+ self.b+self.c)/2
        area = (S*(S-self.a)*(S-self.b)*(S-self.c))**(1/2)
        if S<= self.a  or S<= self.b or S<= self.c:
            '''if the semi perimeter is less than on of the side the triangle is not real ,so return not a real triangle'''
            return "not a real triangle"
        #return area of triangle
        return f"area of triangle is {area}"
'''Test area method with triangle 3,4,5'''
a = Triangle(3,4,5)
print(a.area())

class Hexagon(Polygon):
    '''Another child class that inherit from the class polygon'''
    def __init__(self,  side_length, no_of_sides= 6):
        '''inherit no_of_side but will be set at 6 from the beginning'''
        super().__init__(no_of_sides)
        self.length = side_length
        self.sides = [self.length in range (6)]
    #methods
    def area(self):
        '''method to calculate the area of perfect hexagon with every side equal'''
        area = ((3*(3**1/2))/2)*(self.length**2)
        return f"area of the perfect hexagon with side length = {self.length} is {area} unit square."

hex = Hexagon (7)
print(hex.area())

```

# Output
<img width="945" alt="uiz34" src="https://user-images.githubusercontent.com/82266864/154262344-7a13a06b-4015-4b12-870e-a007976f8bd4.png">
