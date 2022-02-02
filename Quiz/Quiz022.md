```py

# Function to count the number of characters between first and last character of a word which will start everytime there is space
def BlackBox(wrd):
    #define the variable for final product and count the number of character and put the first letter in the final result
    result = wrd[0]
    counter = 0
    for i in range (1,len(wrd)-1):
        # When next letter is space it put the counter and the last letter of that word and reset the counter
        if wrd[i+1]==" ":
            if counter != 0:
                result +=str(counter)
            result += wrd[i]
            counter = 0
        #put space when letter is space
        if wrd[i] == " ":
            result += wrd[i]
        #Put the first letter after the space
        if wrd[i-1] ==" " and wrd[i+1] != " ":
            result += wrd[i]
        # add amount of character into the counter
        else:
            counter+=1
    #add the counter and last letter
    if counter != 0:
        result += str(counter)
    result += wrd[-1]
    return result

print(BlackBox("Hello World !"))
print(BlackBox("Internationalization"))
print(BlackBox("(codin) + (game) = (codingame)"))
print(BlackBox("localization"))
print(BlackBox("98 99 100 101 1062"))

```

# Outcome
<img width="831" alt="Q22" src="https://user-images.githubusercontent.com/82266864/146287694-de69e59d-f41e-4866-b3ca-abb0c0d9ecfc.png">


# Flowchart
<img width="442" alt="Quiz 22(1" src="https://user-images.githubusercontent.com/82266864/148736769-56f21758-8f0c-4fb2-a685-93f240a97769.png">
<img width="495" alt="Quiz 22(2" src="https://user-images.githubusercontent.com/82266864/148736775-9d125847-6031-4655-94ed-6d9c5f9cf5e3.png">

