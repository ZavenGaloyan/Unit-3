```py
import math
#import math for to use round up
class Lily:
    '''class lily that has 2 attributes the length of forest in meters and the speed that Lily walk in meter per second'''
    def __init__(self, length:int, speed:int,)->int:
        self.l = length
        self.s = speed
    #methods
    def matches(self):
        '''
        This method is used to calculate how many matches Lily will use to walk through the l meters with s meter/second
        if the match burn completely in 5 seconds.
        '''
        time = (self.l *100)/self.s
        match = time/5
        return f"{math.ceil(match)} matches"

    def __add__(self, other):
        '''method overriding to add the matches need in 2 different forests with different length and speed'''
        match = round(int(self.matches()[0:-8]) + int(other.matches()[0:-8]))
        return f"{math.ceil(match)} matches"


a = Lily(100, 100)
b = Lily(250,110)
print(a.matches())
print(b.matches())
print(a+b)
```

# Test
<img width="1422" alt="Quiz35" src="https://user-images.githubusercontent.com/82266864/154958559-4a61c240-d70e-42e5-98a0-16444bef3a7b.png">

