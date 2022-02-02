```py
#import random for random integer function
import random
#Create random number and put in variable
number = random.randint(0,100)
#set variable for the guess number
n = -1
#number of tries
tries = 0
#Loop when the guess is not correct
while n != number:
    #increase number of tries
    tries +=1
    print("I have a secret number. Can you guess it")
    #Input player's guess
    n = int(input("Enter your guess:"))
    #3 different conditions when the guessed number is lower/higher than or equal to the secret number
    if n>number:
        print(f"Lower, tries = {tries}")
    if n==number:
        print(f"Correct guess, tries = {tries}")
    if n <number:
        print(f"Higher, tries = {tries}")
```

# Output
<img width="374" alt="Quiz26out" src="https://user-images.githubusercontent.com/82266864/152159439-c32bee81-2d27-4c8b-9804-9ae43f32ad2f.png">
