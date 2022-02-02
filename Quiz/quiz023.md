```py

def letter(n:int):
    #make the n =1 become a
    if n<= 26 and n>0:
        n += 96
        #convert to character
        result = chr(n)
    else:
        result = "Input error"
    return result


print(letter(20))
print(letter(2))
print(letter(10))
print(letter(30))
```

# Output
<img width="110" alt="23 oyt" src="https://user-images.githubusercontent.com/82266864/152160326-aafe3e24-8b64-4604-bc6d-fb11b97ea1ca.png">
