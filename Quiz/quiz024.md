```py
def email(mail :str):
    #Seperate address part and name part
    address = mail.split("@")[1]
    #Get year, fist and last name from name part
    name = mail.split("@")[0]
    last_name = name.split(".")[-1]
    first_name = name.split(".")[-2]
    year = mail.split(".")[0]
    # For students which has email starting with number 2xxx(year)
    if year[0] == "2":
        result = f"Welcome to UWC ISAK {first_name.capitalize()} {last_name.capitalize()}, you are a student graduating in {year}"
    #For other people that doesn't have ISAK email
    elif address != "uwcisak.jp":
        result = "Email is not valid"
    #For those with ISAK email
    else:
        result = f"Welcome to UWC ISAK {first_name.capitalize()} {last_name.capitalize()}"
    return result

print(email("watchapol.areephongsa@uwcisak.jp"))
 ```
 
 # Output
 <img width="339" alt="24 oyt" src="https://user-images.githubusercontent.com/82266864/152160024-7d3b0b0a-3034-40c4-b472-7e1d7145c125.png">
