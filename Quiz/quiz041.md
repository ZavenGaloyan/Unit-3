# ER Diagram

![IMG_DB833AAE91DE-1](https://user-images.githubusercontent.com/82266864/163990952-c449951f-5119-4dd0-b6c5-dde2544af1df.jpeg)

# Code - SQL

```sql
CREATE TABLE if not exists client_information(
    contact_name VARCHAR(256),
    address VARCHAR (256),
    phone_no INTEGER,
    email VARCHAR(256),
    company_name VARCHAR (256)
);

CREATE TABLE if not exists order_of_paper(
    date DATETIME,
    paper_type VARCHAR (256),
    quantity INTEGER,
    price INTEGER,
    delivery_date DATETIME
);

```


# Test

<img width="1440" alt="Test41" src="https://user-images.githubusercontent.com/82266864/163991222-fd9e7fb9-a234-4080-93cf-f08041100cd3.png">
