```py
def ScientifiNot(number:int) -> str:
    #Change that number to the scientific notation form.
    num = str(number)
    a = 1
    #for number less than 1000
    if len(num)>=3:
        result = f"{num[0]}.{num[1]}{num[2]} * 1e{len(num)-1}"
    #For number more than 1000
    else:
       while len(num)!=3:
            num += "0"
            #a or the exponent of 10 will be 1 less than the number of digit
            a +=1
       result = f"{num[0]}.{num[1]}{num[2]} * 1e{len(num) - a}"
    return result

output = ScientifiNot(12000)
print(output)
```

# Output

<img width="93" alt="Samp" src="https://user-images.githubusercontent.com/82266864/152163485-3edb1f44-dfd9-443c-a602-8244e83ac9a8.png">

