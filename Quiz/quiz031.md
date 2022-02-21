```py
class abundant:
    '''OOP class to calculate number of abundant between a and b
    define 2 attributes a as minimum(min) and b as maximum(max)'''
    def __init__(self,a:int, b:int)->int:
        self.min = a
        self.max = b

    #methods
    def abun(self):
        '''Method used to calculate numbers of abundant'''
        number_of_abundant = 0
        '''Set variable for original number of abundants to 0'''
        for i in range(self.min,self.max+1):
            '''Create loop from the minimum (a) to maximum (b)+1 to get the maximum number itself'''
            total = 0
            '''Set variable for the sum of all divisor'''
            for k in range (1,i):
                '''Create another loop to find the divisor of each number '''
                if i%k == 0:
                    '''If the number can be devided by k which starts from 1 to the number -1
                    , k will be added into the total'''
                    total += k
            if total>i:
                ''''When the sum of divisors are more than the number itself
                that number can be called abundance ,so the number of abundant variable will be added 1'''
                number_of_abundant+= 1
        return number_of_abundant
        '''When all the numbers have been through this method will return the numbers of abundant number
        between the a and b'''


set_1 = abundant(10,40)
set_2 = abundant(10,86)
set_3 = abundant(13,78)
print(set_1.abun())
print(set_2.abun())
print(set_3.abun())
```

# Test

<img width="741" alt="Quiz31" src="https://user-images.githubusercontent.com/82266864/154964616-c7723d63-efcb-4c91-b43c-810dd4868cff.png">
