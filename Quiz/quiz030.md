```py
class broken_quiz:
    '''This is oop class used to arrange the word'''
    def __init__(self, code:str, seq:str):
        self.code = code
        '''This class has 2 main attributes the code for the word and sequence which is 
        either S to send the letter in that syntax in the front or E to send in the back '''
        self.seq = seq
        print("object created")

    #methods
    def solve(self):
        '''Method to shuffle the word(code)'''
        n = len(self.code)
        '''Get the number of character(length) of the word in attribute code'''
        if n!= len(self.seq):
            '''If the number of characters inputted in self.seq is not the same as self.code
            the method will return -1 shows that the sequence and code doesn't match each other'''
            return -1

        indx = 0
        '''indx to send in front(0) for S and indx_E to send in the back(-1) for E '''
        indx_E = -1
        solution = ["" for _ in range(n)]
        '''Create list to put letter after shuffled in the list'''
        for i in range(len(self.code)-1,-1,-1):
            '''Create loop that start from the last letter or index length of that word -1
            and it will run backward to index 0 which is inputted -1 because it doesn't take the last index.'''
            curr_seq = self.seq[i]
            curr_cod = self.code[i]
            '''Create 2 more variables represent the code and sequence at that position'''
            if 'S' in curr_seq:
                '''When the seq is S the letter will be added to the list solution in front and index will increase to put
                the next letter at the next position.'''
                solution[indx] = curr_cod
                indx += 1
            else:
                '''if the sequence is E instead the letter will be put at the back and the index of d from -1 will be -2
                and continue -1 as the condition is met'''
                solution[indx_E] = curr_cod
                indx_E-=1
        return "".join(solution)
        '''Lastly the list will be joined and return as a solution'''

test_case = broken_quiz(code=" oworllledH!", seq="ESEEEESSSESE")
print(test_case.solve())
```

# Test

<img width="901" alt="Quiz30" src="https://user-images.githubusercontent.com/82266864/154968995-524c91a3-9867-478f-bf68-5fe9d7a6c37a.png">
