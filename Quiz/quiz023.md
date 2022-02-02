```py
def odd_number(A,B):
    if A>B:
        return "error"
    #set first number to odd
    if A%2!=1:
        A+=1
    #Set variable for solution
    result = ""
    #Add odd number to result with comma
    while A<B-1:
        result += f"{str(A)},"
        A+=2
    #Add last odd number
    result +=str(A)
    return result

print(odd_number(3,10))
print(odd_number(0,5))
print(odd_number(19,1))
```

# Outcome

<img width="83" alt="Out23" src="https://user-images.githubusercontent.com/82266864/152163143-e552df79-0c31-477f-bd63-266159950c44.png">
