# Criteria A : Planning

### Problem Definition (Client identification)
My client is a grade 11 student, Anju Yasu who is studying the IB diploma program at UWC ISAK Japan. One of her IB subjects is English B and the class is having a semester-long individual project called “Happiness Project”. In this project, every student has to complete a few tasks, and one of the tasks is called a Happiness journal –student has to write down what makes them happy in the form of a journal or diary. As an English B student, Anju wanted to record her journal on her laptop, so she wanted an application that she can type in her experience of that day, the date, diary/journal name, and who wrote it. In addition, since the diary may contain the personal information of the author, the client wants this application to have a register and login function to prevent other people to access her diary. 

### Success Criteria

1. The application has a register function to register a user’s email, username, and password and stored them in the database.

2. The application has a login function for users to log in to their diary with email and password which if the inputted information is correct the user will be able to access their diary and edit them.

3. Users can write the title, content and date added(in case the user wants to record the diary for other days and not that day) and click the save button to save the information in the database.

4. The application can automatically save the date and time last updated for each diary into the database.

5. The user can input their name to be saved as the author of the diary or if the user doesn’t input anything, the application will automatically use the username as the author.

### Rationale for the Proposed Solution
In this project, I will use kivymd to create the application interface, SQLAlchemy to create and manage the database, and python 3.9 to create the function of the application. Firstly, I use kivymd to create the interface as kivymd is a simple framework that can allow the user to create the application interface like the login screen, home screen, and every interface needed in this project. Kivymd also provided their user with a detailed description, easy-to-follow example, and “how to use” for each command. In addition, Kivymd can also work with Python to create applications with good functionality. Secondly, SQLAlchemy is the main library that will be used in this project to create and organize the database that will collect the data inputted by users in the form of an online library. SQLAlchemy is being used in this project because it allows the client to easily see and understand all the information inputted in the table and allows them to sort the data as well. Moreover, SQLAlchemy allows me to use it along with normal python and kivymd and all of them can perfectly work together to create an application that can meet all the success criteria. Lastly, the main programming language that will be used in this project is Python because Python is a simple coding language that allows me to meet all the client’s requirements and it also allows me to create applications interface and manage the database by cooperating with Kivymd and SQLAlchemy mentioned before.

# Criteria B : Solution overview

## Flowchart

Need 1 flowchart

## System Diagram

![Untitled drawing](https://user-images.githubusercontent.com/82266864/162608536-7fdc7879-91ec-4d8e-be76-fb12a54cab90.jpg)

## Wireframe Diagram

![IMG_637E054BF57E-1](https://user-images.githubusercontent.com/82266864/162605632-614d364a-6117-4b82-8307-4943742db26b.jpeg)


![IMG_5DE50A8C9968-1](https://user-images.githubusercontent.com/82266864/163747867-8c6ead17-654e-4621-bcad-1c7d5481acba.jpeg)

## ER Diagram

<img width="945" alt="ER" src="https://user-images.githubusercontent.com/82266864/162608765-a0b36bc7-26cd-43ff-b878-5bf7d23ad543.png">

## UML Diagram

1 Diagram

## Record of Task 
Paste when complete

## Test Plan

1 table -- 3 tests

# Criteria C : Development

## List of techniques used
- OOP paradigm
- KivyMD Library
- Relational Databases
- ORM - SQLAlchemy
- Random
- Datetime
- Pbkd2f


### 1. Developing GUI for application
KivyMD Library has been chosen to be used to create the application interface as it is one of the client's requirements. The app interface is created in the separate file (login.kv file) which is linked to the main file by import different functions(**figure 1**) from the library and using the class call app (name of .kv) and use the build function from imported MDApp to show the interface when run the file(**figure 2**) . 


```py
import random
#import random to use random.randing
from datetime import datetime
#import datetime to get today date
from kivy.lang import Builder
#import Builder to create GUI
from kivymd.app import MDApp
#MDApp to connect to class app to connect with kivy file
from kivymd.uix.datatables import MDDataTable
#MDDataTable to create datatable
from kivymd.uix.screen import MDScreen
#Use MDScreen to connect each class to the respective interface screen
#import from the SQLAlchemy the function to connect to a db
from sqlalchemy import create_engine, insert, select
#also the function to create a session and different tables from database_model.py
from sqlalchemy.orm import sessionmaker
from database_model import Base, user, diary
from passlib.context import CryptContext
#import cryptcontext to use sha256 to create hash of user's password
```

**Figure 1**: Setting up random, datetime,KivyMD, SQLAlchemy and Pbkdf2 by importing necessary functions from each library.

```py
class app(MDApp):
    '''class with the same name as .kv file'''
    def build(self):
        return

k = app()
#define the variable which belong to class app to activate run method from MDApp class imported
k.run()
```
**Figure 2**: Create app class which has the same name as the kivy file to link 2 files together and to run and show the GUI a variable has to be created and degine as class app to use run method inherited from MDApp.


After that, different screens are created and defined in the ScreenManager in the kivy file. Then, different elements can be added to that screen below <Screenname> as shown in **figure 3**.

```py
ScreenManager:
    id: scr_manager

    LoginScreen:
        id: loginscr
        name: "LoginScreen"
    WelcomeScreen:
        id: welcomescr
        name: "WelcomeScreen"
    RegisterScreen:
        id: registerscr
        name: "RegisterScreen"
    TableScreen:
        name: "TableScreen"
        id: TableScreen
    NewItemScreen:
        name: "NewItemScreen"
        id: NewItemScreen
    OpenScreen:
        name: "OpenScreen"
        id: OpenScreen
#define each screen and give id to them

 
<LoginScreen>:
# to develop the LoginScreen defined before
    BoxLayout:
    # Basic layout to set orientation
        orientation: 'vertical'
        size: 1000,700
        FitImage:
            source:"diary.jpeg"
    MDCard:
        size_hint: None, None
        size: 1000,900
        elevation: 10
        pos_hint: {"center_x":.5, "center_y":.5}
        orientation: "vertical"
        # for colors, red, green, blue, alpha(transparency)
        md_bg_color: 242/255,220/255,177/255,0.75

        MDBoxLayout:
            id: on_content
            orientation: "vertical"

            MDLabel:
                id: login_label
                text: "MYARY"
                halign: "center"
                valign: "top"
                pos_hint: { "center_y":.5}
                font_style: "H1"
                font_name: 'Free.ttf'
                bold: True



            MDLabel:
                id: label
                theme_text_color: "Custom"
                text_color: 0, 0, 0, 1
                text: 'Keep your memory,                                 Keep your diary.'
                font_style: "H3"
                font_size: '35sp'
                halign: "center"
                font_name: "Conquest.ttf"
                bold: True

                halign: "center"

                pos_hint: {"center_y":.55}

                font_style: "H6"
            MDLabel:
                size_hint: 1,.08


            MDTextField:
                id: email
                size_hint_x: .5
                hint_text: "email"
                pos_hint: {"center_x":.5}
            MDTextField:
                id:password
                hint_text:"password"
                password:True
                size_hint_x: .5
                halign: "center"
                pos_hint: {"center_x":.5}
            MDRaisedButton:
                size_hint_x: 0.5
                size_hint_y: 0.2


                pos_hint: {"center_x": 0.5}
                text: "Log in"
                hint_text: "email"
                on_release:
                    #to activate function login from the python file
                    root.try_login()

            MDBoxLayout:
                size_hint_y: 0.05
            MDRaisedButton:

                size_hint_x: 0.5
                size_hint_y: 0.2
                pos_hint: {"center_x": 0.5}

                text: "Register"
                on_release:
                    #switch to register screen
                    root.parent.current = "RegisterScreen"
            MDBoxLayout:
                id: message
                size_hint_y: 0.2
                text: ""
                text_color:255/255, 59/255, 59/255

```
**Figure 3**: Showing the kivy file with screenmanager which define names and id of each screen in the project. Followed by the LoginScreen part which allow me to develop the login screen with different components.
  
As you can see from **figure 3**, this is the organization of the LoginScreen with different components such as BoxLayout (for background and orientation), MDCard to add  other elements like MDLabels (text), MDTextFields(input information) and MDRaisedButton. RaiseButton is one of the most frequently used components as it can activate a functions defined in the python file using command "on_release" **figure 3** which in this case it can change the screen like the register button or activate function like login button. 

```py
 class LoginScreen(MDScreen):
    #class that links to the login screen to create function that will be activated when some actions
    #are done like button is released.
    def try_login(self):
        #first function to login
        email = self.ids.email.text
        password =self.ids.password.text
        email_result = session.query(user).filter(user.email == email).first()
        #starting with define the inputted email and password using ids
        #Then query user table with id


        if not email_result:
            #if the user is not in the database text below will shows
                self.ids.label.text = "User doesn't exist. Please register."
                self.ids.label.text_color = 1,0,0,1
                self.ids.label.font_name = "default.ttf"


        else:
            #if user exists the database will be query by email to check password using check_pass function
            pwd = session.query(user.password).filter(user.email == email)
            for row in pwd:
                pwd = row[0]
            checkpass = check_password(password, pwd)
            if checkpass:
                #if the password is correct then the welcome screen will be opened
                self.parent.current = "WelcomeScreen"
            else:
                #if password is wrong the below message will be shown at the bottom of screen
                self.ids.label.text = "Wrong password"
                self.ids.label.text_color = 1, 0, 0, 1
                self.ids.label.font_name = "default.ttf"
 
```
**Figure 4**: the login class in python file that is connected to the login screen in the kivy file which allows functions to be created to be activated when button is released. There is 1 function in this class which is used for logging in which is try_login.
  
  These screens are also being defined in the main python file using a class which will inherit attributes and some methods from the MDScreen class, imported earlier. After defining and inheriting the class, the screen will be linked to the python file ,so different functions can be created in each class and used with the raise button through on_release command in the kivy file (see **figure 4**). Screen can be switched using self.parent.current as shown in **figure 5 and 6**. Each element in the kivy file can be given an id like self.ids.label.text in **figure 4** to get information or make some changes to it. 

```py
  self.parent.current = "WelcomeScreen"
```
  **Figure 5**: Changing screen to welcome screen in python file
  
  ```kv
  root.parent.current = "RegisterScreen"
  ```
  **Figure 6**: Changing screen to register screen in kivy file

### 2. Database
	Databases are being used to store user's information. To use relational databases, I will use sqlalchemy library. Starting with setting up the library,table and database by import sessionmaker, tables (which would be defined in the different python file) and different functions **figure below**. Starting with a separate python file which will be created to set up tables by importing different functions and create a variable for the declarative base function which is used to define classes mapped to relational data tables. 

After that, class for the table as shown in  **fig above** can be created and define the name of the table, column name, information type and other details about the column. After that the function create engine can be used to create the database as shown in fig below. 

After finishing working with seperate file, in the main file, create_engine function will be used to bind the file with the created database as shown in fig above.

2.1 Registration(adding information into database)
	

Example of adding information into the database is in the registration process which uses session.query with filter to query the database whether the inputted email and username have been used or not to prevent existing users from registering again. Then, the password has to be verified to check whether the confirmed password matches with the inputted password or not using the id from the kivy to get the value. After that, a random unique id will be generated for each user using the random.randint(a,b). After that, the information can be added in the database using session.add(new) which is the variable that is used to define the information that will be added in each column as shown in fig above. Then, it will add all the information into the user table after being committed. The same process also applies to adding the information to the diary table which uses datetime.today() (shown in fig below) to get the date for the date_added column.



2.2 Query 
Query databases by using session.query act as select which can select specific value by using filter command. Query can be used in many cases. For example, creating datatable (explain in 2.3) query to check if the information is correct or not in verifying password, query to get the string in content column of diary table to calculate average word count, query to get row remove a row using query().delete() in delete function or use to query each value of the selected row to update in edit function. 

2.3 Creating Table

	To show the diary that the user wrote, the MDDatatable will be used. This table can be created with the use of KivyMD to create the show datatable and ORM to insert data from database to datatable. Firstly, query the database with the email of the user to only get the diary that belongs to the specific user. After that the list will be created for each column of every row to be added before defining the variable  for the table that will be created and assigning different elements to it (figure). After that function row_press and on_check_press to detect when the checkbox is pressed will be bound to the table.The table can then be added to the screen using self.add_widget(self.data_tables).






 Password
	To secure the password in the database, it will be encrypted using Password Based Key Derivation Function(Pbkdf2) which will create a hash (unique code) using cryptographic function called sha256. In order to do this, CryptContext function which is imported from passlib.context will be used to hash the password 30,000 times with the scheme sha256 **figure below**. 

Firstly, the variable will be defined to activate the function of hashing the password. After that, 2 functions can be created  encrypt_password(to encrypt inputted password) and check_password(to verify inputted password with the one in database) shown in **figure below**. Then, use this with the register function in RegisterScreen to encrypt the password that user inputted **figure below**. After the hashed password is saved into the database, the check_password function defined earlier will be used in the login process to verify the inputted password **figure below**. 

### Update
  To develop software after the release to satisfy the user based on their feedback. The application will be automatically updated quarterly which mostly will be the corrective update which user doesn't have to install the update. However, the application will also provided new features at least once a year which this type of update will be functional updaate which the user will have to download the update from the developer's website. Moreover, if there is a bug that can cause the lost in user's information an immediate correction update will be provided for user to download to fix those bugs.
# Criteria D : Functionality and Extensibility of Product

VDO
  
  # Citation
  https://www.ibm.com/docs/en/zos/2.4.0?topic=task-types-software-updates
  
# Appendix
  ## Whole Code
# Python file
  ```py
  import random
#import random to use random.randing
from datetime import datetime
#import datetime to get today date
from kivy.lang import Builder
#import Builder to create GUI
from kivymd.app import MDApp
#MDApp to connect to class app to connect with kivy file
from kivymd.uix.datatables import MDDataTable
#MDDataTable to create datatable
from kivymd.uix.screen import MDScreen
#Use MDScreen to connect each class to the respective interface screen
#import from the SQLAlchemy the function to connect to a db
from sqlalchemy import create_engine, insert, select
#also the function to create a session and different tables from database_model.py
from sqlalchemy.orm import sessionmaker
from database_model import Base, user, diary
from passlib.context import CryptContext
#import cryptcontext to use sha256 to create hash of user's password

pwd_context = CryptContext(
    schemes = ["pbkdf2_sha256"],
    default ="pbkdf2_sha256",
    pbkdf2_sha256__default_rounds = 30000
)
def encrypt_password(password):
    return pwd_context.encrypt(password)

def check_password(password,hashed):
    return pwd_context.verify(password,hashed)
db_engine = create_engine("sqlite:///application_database.db")
Base.metadata.bind = db_engine
db_session = sessionmaker(bind = db_engine)
session = db_session()
def encrypt_password(password):
    return pwd_context.encrypt(password)

def check_password(password,hashed):
    return pwd_context.verify(password,hashed)

class LoginScreen(MDScreen):
    #class that links to the login screen to create function that will be activated when some actions
    #are done like button is released.
    def try_login(self):
        #first function to login
        email = self.ids.email.text
        password =self.ids.password.text
        email_result = session.query(user).filter(user.email == email).first()
        #starting with define the inputted email and password using ids
        #Then query user table with id


        if not email_result:
            #if the user is not in the database text below will shows
                self.ids.label.text = "User doesn't exist. Please register."
                self.ids.label.text_color = 1,0,0,1
                self.ids.label.font_name = "default.ttf"


        else:
            #if user exists the database will be query by email to check password using check_pass function
            pwd = session.query(user.password).filter(user.email == email)
            for row in pwd:
                pwd = row[0]
            checkpass = check_password(password, pwd)
            if checkpass:
                #if the password is correct then the welcome screen will be opened
                self.parent.current = "WelcomeScreen"
            else:
                #if password is wrong the below message will be shown at the bottom of screen
                self.ids.label.text = "Wrong password"
                self.ids.label.text_color = 1, 0, 0, 1
                self.ids.label.font_name = "default.ttf"



class RegisterScreen(MDScreen):
    def on_pre_enter(self, *args):
        self.ids.remail.text = ""
        self.ids.confirm.text = ""
        self.ids.user.text = ""
        self.ids.rpassword.text = ""
    def register(self):
        password = self.ids.rpassword.text
        confirm = self.ids.confirm.text
        email =  self.ids.remail.text
        username = self.ids.user.text
        check_user = session.query(user).filter(user.email == email,user.username == username).all()
        if password != "" and confirm != "":
            if password == confirm and not check_user:
                iden = random.randint(1, 100000)
                check_id = session.query(user).filter(user.id == iden).all()
                while iden == check_id:
                    iden = random.randint(1, 100000)
                password = encrypt_password(password)
                new = user(id=iden,
                            email=email,
                            username=username,
                            password=password
                        )
                session.add(new)
                session.commit()
                self.parent.current = "WelcomeScreen"

            elif password == confirm and check_user:
                self.ids.msg.text = "User existed"
            else:
                self.ids.msg.text = "password doesn't match"
        else:
            self.ids.msg.text = "password needed"
            self.ids.msg.text_color = 1, 0, 0,1

class WelcomeScreen(MDScreen):

    def on_pre_enter(self, *args):

        username = session.query(user.username).where(user.email ==  self.parent.ids.loginscr.ids.email.text)
        for row in username:
            username = row[0]
        username = username[0].upper() +username[1:]
        self.ids.welcome.text = f"Welcome " + username
        self.ids.welcome.font_name =  "Vintage.ttf"

    def logout(self):
        self.parent.ids.loginscr.ids.email.text = ""
        self.parent.ids.loginscr.ids.password.text = ""
        self.parent.current = "LoginScreen"
        self.parent.ids.loginscr.ids.label.text_color = 0, 0, 0, 1
        self.parent.ids.loginscr.ids.label.text = 'Keep your memory,                                 Keep your diary.'
        self.parent.ids.loginscr.ids.label.font_name= "Conquest.ttf"


class NewItemScreen(MDScreen):
    def on_pre_enter(self, *args):
        self.ids.title.text = ""
        self.ids.author.text = ""
        self.ids.content.text = ""
    def save(self):
        email = self.parent.ids.loginscr.ids.email.text
        title = self.ids.title.text
        author = self.ids.author.text
        content = self.ids.content.text
        if author == "":
            username = session.query(user.username).filter(user.email == self.parent.ids.loginscr.ids.email.text)
            for row in username:
                username = row[0]
            author = str(username)
        id = random.randint(1, 100000)
        day = datetime.today().strftime('%Y-%m-%d')
        diary_id = session.query(diary).filter(diary.id == id).all()
        while id == diary_id:
          id = random.randint(1, 100000)
        new_diary = diary(id = id,
                   email=email,
                   title=title,
                   date_added = day,
                   last_update = day,
                   author=author,
                   content=content
                   )
        session.add(new_diary)
        session.commit()
        self.parent.current = "WelcomeScreen"


class TableScreen(MDScreen):
    data_tables = None


    def on_pre_enter(self, *args):
        """Get the data from the database"""
        query = session.query(diary).filter(diary.email == self.parent.ids.loginscr.ids.email.text).all()
        print(query)
        result = []
        for q in query:
            result.append([q.id,q.title,q.date_added,q.last_update,q.author,q.content])
        print(result)
        self.data_tables = MDDataTable(
            size_hint =(1,0.6),
            pos_hint = {"center_x":0.5, "center_y":0.5},
            check = True,
            column_data = [("ID",50),("Title",100),("Date added",40),("Last update",40),("Author", 40), ("Content", 100)],
            use_pagination=True,
            row_data = result,
        )
        self.data_tables.bind(on_row_press = self.on_row_press)
        self.data_tables.bind(on_check_press=self.on_check_press)
        self.add_widget(self.data_tables)

        number_of_row = 0
        total = 0
        for q in query:
            list = q.content.split()
            total += len(list)
            number_of_row += 1
        if number_of_row > 0:
            self.ids.avg.text = f"Average word count of your diary is {total // number_of_row} words"
        else:
            self.ids.avg.text = f"Average word count of your diary is 0 words"




    def on_row_press(self,table, row):

        print(f"Item was clicked", row.text)

    def on_check_press(self,table,current_row):
        id,title,date_added,last_update,author,content = current_row
        print(title,date_added,last_update,author,content)
        self.parent.ids.OpenScreen.ids.label.text = id
        self.parent.ids.OpenScreen.ids.title.text = title
        self.parent.ids.OpenScreen.ids.author.text = author
        self.parent.ids.OpenScreen.ids.content.text = content
    def open(self):
        id = self.parent.ids.OpenScreen.ids.label.text
        result = session.query(diary).where(diary.id == id)
        if result:
            self.parent.current = "OpenScreen"
        else:
            pass
    def delete(self):
        id = self.parent.ids.OpenScreen.ids.label.text
        print(int(id))
        dele = session.query(diary).filter(diary.id == id).delete()
        session.commit()
        print(dele)
        query = session.query(diary).filter(diary.email == self.parent.ids.loginscr.ids.email.text).all()
        print(query)
        number_of_row = 0
        total = 0
        result = []
        for q in query:
            list = q.content.split()
            total += len(list)
            number_of_row += 1
            result.append([q.id, q.title, q.date_added, q.last_update, q.author, q.content])
        print(result)
        if number_of_row>0:
            self.ids.avg.text = f"Average word count of your diary is {total // number_of_row} words"
        else:
            self.ids.avg.text =  f"Average word count of your diary is 0 words"
        self.data_tables.update_row_data(
            None, result
        )



class OpenScreen(MDScreen):


    def edit(self):
        id = self.parent.ids.OpenScreen.ids.label.text
        title = self.ids.title.text
        date = datetime.today().strftime('%Y-%m-%d')
        author = self.ids.author.text
        content = self.ids.content.text
        upd = session.query(diary).filter(id == id).first()
        upd.title = title
        upd.last_update = date
        upd.author = author
        upd.content = content
        print(upd)
        self.parent.current = "TableScreen"











class app(MDApp):
    '''class with the same name as .kv file'''
    def build(self):
        return

k = app()
#define the variable which belong to class app to activate run method from MDApp class imported
k.run()
  ```
 # Python File For Database
  ```py
  #database_models
from datetime import datetime

from sqlalchemy import Column, Integer, String, create_engine
from sqlalchemy.orm import declarative_base

Base = declarative_base()

class user(Base):
    __tablename__ = "user"
    id = Column(Integer, primary_key=True)
    username = Column(String(250))
    email = Column(String(250), nullable=False)
    password = Column(String(256), nullable=False)


class diary(Base):
    __tablename__ = "diary"
    id = Column(Integer, primary_key=True)
    email = Column(String(250))
    title = Column(String(250))
    date_added = Column(String(250))
    last_update = Column(String(250))
    author = Column(String(250))
    content = Column(String(2500))



db_engine = create_engine("sqlite:///application_database.db")
Base.metadata.create_all(db_engine)
  ```
 # Kivy File
  ```kv
  

#######
#define the screen manager. All apps need one
ScreenManager:
    id: scr_manager

    LoginScreen:
        id: loginscr
        name: "LoginScreen"
    WelcomeScreen:
        id: welcomescr
        name: "WelcomeScreen"
    RegisterScreen:
        id: registerscr
        name: "RegisterScreen"
    TableScreen:
        name: "TableScreen"
        id: TableScreen
    NewItemScreen:
        name: "NewItemScreen"
        id: NewItemScreen
    OpenScreen:
        name: "OpenScreen"
        id: OpenScreen
#define each screen and give id to them

<LoginScreen>:
# to develop the LoginScreen defined before
    BoxLayout:
    # Basic layout to set orientation
        orientation: 'vertical'
        size: 1000,700
        FitImage:
            source:"diary.jpeg"
    MDCard:
        size_hint: None, None
        size: 1000,900
        elevation: 10
        pos_hint: {"center_x":.5, "center_y":.5}
        orientation: "vertical"
        # for colors, red, green, blue, alpha(transparency)
        md_bg_color: 242/255,220/255,177/255,0.75

        MDBoxLayout:
            id: on_content
            orientation: "vertical"

            MDLabel:
                id: login_label
                text: "MYARY"
                halign: "center"
                valign: "top"
                pos_hint: { "center_y":.5}
                font_style: "H1"
                font_name: 'Free.ttf'
                bold: True



            MDLabel:
                id: label
                theme_text_color: "Custom"
                text_color: 0, 0, 0, 1
                text: 'Keep your memory,                                 Keep your diary.'
                font_style: "H3"
                font_size: '35sp'
                halign: "center"
                font_name: "Conquest.ttf"
                bold: True

                halign: "center"

                pos_hint: {"center_y":.55}

                font_style: "H6"
            MDLabel:
                size_hint: 1,.08


            MDTextField:
                id: email
                size_hint_x: .5
                hint_text: "email"
                pos_hint: {"center_x":.5}
            MDTextField:
                id:password
                hint_text:"password"
                password:True
                size_hint_x: .5
                halign: "center"
                pos_hint: {"center_x":.5}
            MDRaisedButton:
                size_hint_x: 0.5
                size_hint_y: 0.2


                pos_hint: {"center_x": 0.5}
                text: "Log in"
                hint_text: "email"
                on_release:
                    #to activate function login from the python file
                    root.try_login()

            MDBoxLayout:
                size_hint_y: 0.05
            MDRaisedButton:

                size_hint_x: 0.5
                size_hint_y: 0.2
                pos_hint: {"center_x": 0.5}

                text: "Register"
                on_release:
                    #switch to register screen
                    root.parent.current = "RegisterScreen"
            MDBoxLayout:
                id: message
                size_hint_y: 0.2
                text: ""
                text_color:255/255, 59/255, 59/255


<WelcomeScreen>

    FitImage:
        source: "library.jpeg"
    MDBoxLayout
        pos_hint: {"center_y": 0.78,"center_x":.5}
        size_hint: 0.5,0.2
        md_bg_color: 0,0,0,.7
    MDLabel:
        id: welcome
        text: "Welcome"
        font_name: "Vintage.ttf"
        font_style:"H2"
        theme_text_color: "Custom"
        text_color: 1,1,1,1
        pos_hint: {"center_y": 0.8}
        halign: "center"
    MDRaisedButton:
        text: "New"
        font_style: "H5"
        md_bg_color: 92/255, 219/255, 92/255,1
        width: root.width*0.3
        pos_hint:{"center_x":.5, "center_y":0.6}
        size_hint: None,None
        height: root.height*0.1
        on_release:
            root.parent.current = "NewItemScreen"
    MDRaisedButton:
        font_style: "H5"
        text: "List"
        md_bg_color: 36/255, 116/255, 244/255,1
        width: root.width*0.3
        pos_hint:{"center_x":0.5, "center_y":0.45}
        size_hint: None,None
        height: root.height*0.1
        on_release:
            root.parent.current = "TableScreen"
    MDRaisedButton:
        text: "Log out"
        font_style: "H5"
        height: root.height*0.1
        width: root.width*0.3
        pos_hint:{"center_x":0.5, "center_y":0.3}
        md_bg_color: 1,0,33/255,1
        size_hint: None,None
        on_release:
            root.logout()
<TableScreen>
    MDLabel:
        text: "Your Diary"
        font_style: "H2"
        pos_hint: {"center_x":.5,"center_y":.9}
        valign: "top"
        halign: "center"

    MDLabel:
        text: "Average Word Count"
        id: avg
        font_style: "H6"
        pos_hint: {"center_x":.5,"center_y":.17}
        valign: "bottom"
        halign: "center"


    MDRaisedButton:
        text: "Back"
        size_hint: .15,.05
        md_bg_color:0,0,0,1
        on_release:
            root.parent.current = "WelcomeScreen"
    MDRaisedButton:
        text: "open/edit"
        size_hint: .2,.06
        pos_hint:{"center_x":.7, "center_y":.1}
        md_bg_color:0,0,1,1
        on_release:
            root.open()
    MDRaisedButton:
        id: delete
        text: "Delete Diary"
        md_bg_color: 1,0,0,1
        size_hint: 0.25,0.05
        pos_hint: {"center_x":.3, "center_y":.1}
        on_release:
            root.delete()

<RegisterScreen>
    BoxLayout:
        orientation: 'vertical'
        size: 1000,700
        FitImage:
            source: "1.jpeg"
    MDCard:
        size_hint: None, None
        size: 700,900
        elevation: 10
        pos_hint: {"center_x":.5, "center_y":.5}
        orientation: "vertical"
        # for colors, red, green, blue, alpha(transparency)
        md_bg_color: 240/255, 211/255, 161/255,0.75
        MDBoxLayout:
            id: on_content
            orientation: "vertical"
            MDLabel:
                id: register_label
                text: "Register"
                halign: "center"
                pos_hint: { "center_y":.5}
                font_style: "H2"
            MDTextField:
                id: user
                hint_text: "username"
            MDTextField:
                id: remail
                hint_text: "email"
            MDTextField:
                id: rpassword
                hint_text:"password"
                password:True
            MDTextField:
                id:confirm
                hint_text:"confirm password"
                password:True
            MDRaisedButton:
                size_hint_x: 0.5
                size_hint_y: 0.2
                pos_hint: {"center_x": 0.5}
                text: "Register"
                on_release:
                    root.register()
            MDBoxLayout:
                size_hint_y: 0.2
                MDLabel
                    id: msg
                    halign: "center"
                    theme_text_color: "Custom"
                    text_color: 1, 0, 0, 1
                    text: ""

    MDRaisedButton:
        size_hint_x: 0.2
        md_bg_color: 0, 0, 0, 1
        text: "Go back to login screen"
        on_release:
            root.parent.current ="LoginScreen"

<NewItemScreen>
    MDLabel:
        text: "New Diary"
        pos_hint: {"center_x":.5, "center_y":.98}
        font_style:"H5"
    MDTextField:
        id: title
        mode: "rectangle"
        hint_text: "Title"
        size_hint: 0.8,0.08
        pos_hint: {"center_x":.5, "center_y":.9}
    MDRaisedButton:
        size_hint: 1,0.02
    MDTextField:
        id: author
        mode: "rectangle"
        hint_text: "author"
        size_hint: 0.8,0.08
        text: ""
        pos_hint: {"center_x":.5, "center_y":.82}
    MDRaisedButton:
        size_hint: 1,0.02
    MDTextField:
        id: content
        mode: "rectangle"
        hint_text: "Content"
        size_hint: 0.8,0.6
        pos_hint: {"center_x":.5, "center_y":.48}
        multiline: True
    MDRaisedButton:
        id: save
        text: "Save"
        md_bg_color:69/255, 209/255, 109/255,1
        size_hint: 0.3,0.05
        pos_hint: {"center_x":.7, "center_y":.1}
        on_release:
            root.save()
    MDRaisedButton:
        text: "cancel"
        size_hint: 0.3,0.05
        md_bg_color:1,0,0,1
        pos_hint: {"center_x":.3, "center_y":.1}
        on_release:
            root.parent.current = "WelcomeScreen"


<OpenScreen>
    MDLabel:
        id : label
        text: ""
        pos_hint: {"center_x":.5, "center_y":.98}
        font_style:"H5"
    MDTextField:
        id: title
        mode: "rectangle"
        hint_text: "Title"
        text: ""
        size_hint: 0.8,0.08
        pos_hint: {"center_x":.5, "center_y":.9}
    MDRaisedButton:
        size_hint: 1,0.02
    MDTextField:
        id: author
        mode: "rectangle"
        hint_text: "author"
        text:""
        size_hint: 0.8,0.08
        text: ""
        pos_hint: {"center_x":.5, "center_y":.82}
    MDRaisedButton:
        size_hint: 1,0.02
    MDTextField:
        id: content
        mode: "rectangle"
        hint_text: "Content"
        size_hint: 0.8,0.6
        text: ""
        pos_hint: {"center_x":.5, "center_y":.48}
        multiline: True
    MDRaisedButton:
        id: save
        text: "Save Change"
        size_hint: 0.25,0.05
        md_bg_color:69/255, 209/255, 109/255,1
        pos_hint: {"center_x":.7, "center_y":.1}
        on_release:
            root.edit()

    MDRaisedButton:
        text: "Back"
        md_bg_color:1,0,0,1
        size_hint: 0.25,0.05
        pos_hint: {"center_x":.3, "center_y":.1}
        on_release:
            root.parent.current = "TableScreen"
  ```
