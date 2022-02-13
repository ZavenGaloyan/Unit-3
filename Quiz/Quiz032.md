# CODE
```py

class count:
    '''
    Parent class
    '''
    #define attributes for text and letter inside
    def __init__(self,text:str, letter:str)->int:
        self.letter = letter
        self.text = text
    #method
    def counter(self):
        #method to count numbers of letter in the given text
        counter = 0
        for i in range(len(self.text)):
            #check that the each letter in the text match or not
            if self.text[i] == self.letter:
                #if it matches then the counter will increase
                counter +=1
        return counter

class countletter(count):
    '''
    child class inherit from the class count
    '''


letter = countletter("The world is vast, vast", "a")
print(letter.counter())

```

# Output

<img width="915" alt="QUIZ32" src="https://user-images.githubusercontent.com/82266864/153739537-a3ec8133-5dc4-4e52-9329-1b46f0f9fb2c.png">
