```py
import sqlite3
import random
connection = sqlite3.connect("quiz39.db")
cursor = connection.cursor()
cursor.execute("""CREATE TABLE if not exists Electric_car (
        id INTEGER  primary key autoincrement ,
        brand VARCHAR (200),
        model VARCHAR(255),
        maker VARCHAR (256),
        battery_size INTEGER
    );
    """)
connection.commit()
for i in range (1000):
    id = random.randint(1,10000)
    battery = random.randint(500,4000)
    cursor.execute(f"""INSERT into Electric_car values({id}, 'Mitsubishi', 'A', 'Mit', {battery})
    ;
     """)
    connection.commit()
```

# Test
<img width="1440" alt="Test39" src="https://user-images.githubusercontent.com/82266864/160978357-fb75e638-f1aa-4e18-a587-472f361bb544.png">
