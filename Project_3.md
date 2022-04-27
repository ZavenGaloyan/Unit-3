# Table of Content
1. [Criteria A](#criteria-a-planning)

2. [Criteria B](#criteria-b-solution-overview)

3. [Criteria C](#criteria-c-development)

4. [Criteria D](#criteria-d-functionality-and-extensibility-of-product)

5. [Citation](#citation)

6. [Appendix](#appendix)

6.1  [Meeting Note](#client-meeting-note)



# Criteria A-Planning

### Problem Definition (Client identification)
My client is a grade 11 student,the client is studying the IB diploma program at UWC ISAK Japan. One of her IB subjects is English B and the class is having a semester-long individual project called “Happiness Project”. In this project, every student has to complete a few tasks, and one of the tasks is called a Happiness journal –student has to write down what makes them happy in the form of a journal or diary. As an English B student, Anju wanted to record her journal on her laptop, so she wanted an application that she can type in her experience of that day, the date, diary/journal name, and who wrote it. In addition, since the diary may contain the personal information of the author, the client wants this application to have a register and login function to prevent other people to access her diary. The client need an online diary instead of the old school paper diary as the online diary allow the client to make different diaries and it is a more sustainable way of taking note as the old school way need to waste a lot of paper to make a diary. Moreover, online diary is a better choice as the client can easily carry many different diaries in the form of device around and can create/edit/remove diary anytime and anywhere they want.

### Success Criteria

1. The application has the registration screen which allow the user to input the username, email and password which will be save in the database for login.

2. The password that user inputted need to be encrypted to secure it in the database.

3. The user can login with email and password used for register

4. The user can create new diary which can input title, author and content and the application will automatically set the date added and date last updated of each diary and put them in the new table in the database.

5. The user can see their diary using list button to see the auto generated id, title, author, date added, date last updated and content of each diary owned by them.

6. The user can use remove button to delete the diary in the checked row and use open/edit button to edit the content which will also update table and database and it will automatically change date last updated of that diary.

7. If user didn't input author name, the application will automatically take ther username inputted during the registration as the author name of that diary.

8. The application can show the average word count of the total content of every the diary at the below the diary table in the list screen.

### Client meeting record (success criteria)



https://user-images.githubusercontent.com/82266864/164173174-45c04aa5-f41b-47c6-92eb-332b3ebea65d.mp4



### Rationale for the Proposed Solution
In this project, the application will have login system as the client may have some sensitive information, so login in system is needed to secure the client. And it will be in application form as it is easy for client to use as well as being a user friendly application for client to use it without instruction needed. The application will also allow client to create different diary as everyone has different aspect in their life and this application will allow the user to record each of them in different diary for them to open the specific diary when they wanted to read or write about something related to that.

As for tool, I will use kivymd to create the application interface, SQLAlchemy to create and manage the database, and python 3.9 to create the function of the application. Firstly, I use kivymd to create the interface as kivymd is a simple framework that can allow the user to create the application interface like the login screen, home screen, and every interface needed in this project. Kivymd also provided their user with a detailed description, easy-to-follow example, and “how to use” for each command in their webpage and community online. In addition, Kivymd can also work with Python to create applications and since KivyMD works with OOP paradigm, it allows coder to easily structure, organize and create the UI according to [3]. In comparison to another UI creating software like Flutter, KivyMD has more advantage on some components like more supportive online community, user-friendliness but most importantly KivyMD is better as it can work with python coding language while Flutter cannot which therefore is more suitable in this project and flutter and other similar library as shown in [6].

Secondly, SQLAlchemy is the main library that will be used in this project to create and organize the database that will collect the data inputted by users in the form of an online library. SQLAlchemy is being used in this project because it allows me to use it along with normal python and kivymd and all of them can perfectly work together to create an application that can meet all the success criteria. SQLAlchemy is used in this project instead of SQLite which is the similar tool as SQLAlchemy use ORM language which simplify most of the syntax such as query which SQLite has to define the variable and connect to database while SQLalchemy can directly query the database if the setup of database is already there. Hence, SQLAlchemy is the most suitable tool for database management in this project as shown in [12]

Lastly, the main programming language that will be used in this project is Python because Python allows me to meet all the client’s requirements and it also allows me to create applications interface and manage the database by cooperating with Kivymd and SQLAlchemy mentioned before. Apart from having many libraries that allows many uses, python is also a more flexible coding language compared to C or Javascript as the use of python may include creating database, making application, coding for A.I. etc. In addition, what makes python stands out from other coding language is that python code is natural language that we use in our daily life not computer language that C and most of the other coding languages use as described in [9].Therefore, Python is the most suitable coding language for this project.

# Criteria B-Solution overview

## Flowchart

![Untitled Diagram drawio](https://user-images.githubusercontent.com/82266864/163771760-3bb20494-14a7-431f-8f51-aeab7e8f1fca.png)

**Figure 1**: The diagram above is the flow diagram which shows different techniques used to produce find the average word count per diary, starting from query the database, using for loop to get values in the column from database and use if statement to make the final condition when there is no diary. This flowchart also uses different shapes to show different function of each method or techniques and arrow to show the flow from start to the end of that particular coding section



## System Diagram

![Untitled drawing (1)](https://user-images.githubusercontent.com/82266864/163768959-76e62696-9f45-4416-878b-1df96bee20e8.jpg)

**Figure 2** This shows the system diagram from the input(keyboard) to the output which includes different systems being used in this project such as version of coding language(python and KivyMD) and application(PyCharm), computer version and detail(Processor,version, memory, etc.), module and database and the output screen(application interface on the computer screen).

## Wireframe Diagram

![IMG_637E054BF57E-1](https://user-images.githubusercontent.com/82266864/162605632-614d364a-6117-4b82-8307-4943742db26b.jpeg)

**Figure 3** This is the first version of the wireframe diagram or a prototype of the application's GUI. This is being used to show for the first MVP presentation with client. In this diagram, different screen that will be in the application will be put with different buttons. Arrows from one button to screen show which screen the button will open when it is pressed and released. In addition, the number on top of the screen also shows the  normal flow of the application from the Log in screen to the Registration screen and then Home screen, New diary screen and Open diary screen as shown above. 

![IMG_5DE50A8C9968-1](https://user-images.githubusercontent.com/82266864/163747867-8c6ead17-654e-4621-bcad-1c7d5481acba.jpeg)

**Figure 4** This is the final version of the wireframe diagram which is used to show the final product or final GUI of the application. This is made using the feedback from the client after the MVP  meeting(note in appendix) which had been asked to add another screen for editting as editting in the open diary screen seems hard for user. 

## ER Diagram

<img width="1071" alt="new_er" src="https://user-images.githubusercontent.com/82266864/165453165-ad7f3f97-f426-45ac-bd5b-d71959cfee81.png">


**Figure 5** This is the ER diagram showing the relationship between diary table and user table. In the diary table, there are 7 different columns including title, content, author, id ,email, last_update and date_added (shown above) which each column will have the specific data type after the column name. The second table has 4 columns which are username, ud, email and password. This diagram also shows that 1 user can have multiple diary. The underlined column name is the primary key which have to be unique and for these 2 tables the primary key will be the id.

## UML Diagram

<img width="1440" alt="newuml" src="https://user-images.githubusercontent.com/82266864/165453145-9b85b7a7-5fcf-4ca4-8fe3-fc72478ff1ac.png">


**Figure 6** This shows the UML diagram for the all the classes use in this project with methods in each class. There are 2 main parents class which are MDScreen and MDApp which all the other class inherited methods and attributes from them. The inheritance is shown by the arrow



## Test Plan
| Description                 | Type             | Inputs                                                                                                                                              | Outputs                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Registration system         | Unit test        | 1. Run the main_ORM.py 2. Click Register button on the application 3. Input information in each textfield following the hint text 4. Click register | If the user already exists: the message in red will say the user already exists. If 2 passwords don't match: the message will say that password doesn't match. If follow all instruction: successfully open WelcomeScreen.                                                                                                                                                                                                                          |
| User database check         | Unit test        | 1. Register 2. Open user table in application database.py 3. Check password column and id column                                                    | All passwords need to be encrypted with hash and id has to be unique between 1 to 99,999.                                                                                                                                                                                                                                                                                                                                                           |
| Log out system              | Unit test        | 1. Register 2. Press log out button                                                                                                                 | Login screen will appear.                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Login system                | Unit test        | 1. Input the registered email in email textfield 2. Input the password in the password textfield 3. Press login button                              | If the email is not registered: "User doesn't exists" will be displayed If the password is wrong: "Wrong password" will appeared If the email and passwords are correct: the WelcomeScreen will be opened                                                                                                                                                                                                                                           |
| Diary openning and checking | Integration test | 1. Press "New" button 2. Fill in the title, author(optional), and content 3. Press the save button 4. Press "List" button                           | Note: If the author is not inputted: the author name will be the username The table will appear with 1 diary that belongs to specific user and6 columns including ID(unique), Title,  Date added(today date in year month, and day), Last updated(the date that the document is last updated),  Author and Content(of the diary). At the bottom of the screen, there will be an average word count of  per diary which will be in the whole number. |
| Remove function             | Unit test        | 1. Press check on one of the diary in the TableScreen 2. Press delete                                                                               | That specific diary will be delete from the on screentable and database. The average will also be updated.                                                                                                                                                                                                                                                                                                                                          |
| Edit function               | Unit test        | 1. Press on one of the box in front of a diary in the TableScreen 2. Press open/edit button 3. Change some contents  4. Press save change           | The new content will be updated to the table which also change the last_update column and average word count                                                                                                                                                                                                                                                                                                                                        |
| Python Code Review          | Code Review      | Check the main_ORM.py and database_model.py file for: 1. Variable names 2. Comment 3. Repetition                                                    | The variable name and comment help the user to understand the functionality of the code The code should be easy to follow and not too complicated to understand with no repetition.                                                                                                                                                                                                                                                                 |

**Table 1** Test plan for tester to follow to test the application. There are 3 different types of tests presented in the test plan which are unit test(to test one part of the program), integration test(to test the cooperation of different parts) and code review(to check the quality of code). In addition, description, input(step to follow) and expected output are also presented in the table for user to follow and knnow what to expect from each test.
## Record of Task 

|    | Planned Action                                        | Planned Outcome                                                                            | Design Cycle   | Time Estimate | Target Completion | Criteria |
|----|-------------------------------------------------------|--------------------------------------------------------------------------------------------|----------------|---------------|-------------------|----------|
| 1  | First meeting with client                             | To understand client problem and requirements                                              | Planning       | 30 minutes    | 5 March           | A        |
| 2  | Write down success criteria                           | To list down the first success criteria                                                    | Planning       | 20 minutes    | 6 March           | A        |
| 3  | Write problem definition                              | Have problem definition which will identify who client is and the product that client want | Planning       | 1 hour        | 6 March           | A        |
| 4  | Update success criteria                               | List more success criteria and prepare for presentation to client                          | Planning       | 30 minutes    | 14 March          | A        |
| 5  | Meet with client to  present the success criteria     | Present success criteria to client to get the approval                                     | Planning       | 30 minutes    | 19 March          | A        |
| 6  | Research and write rationale for proposed solution    | Finish rationale for proposed solution                                                     | Planning       | 2 hours       | 20 March          | A        |
| 7  | Starts working on login and registration system       | Finish login and registration system with database                                         | Development    | 1 day         | 23 March          | C        |
| 8  | Create wireframe diagram                              | Wireframe diagram is ready to present to client as the first MVP                           | Design         | 1 hour        | 24 March          | B        |
| 9  | Create system diagram                                 | System diagram is done with details written on it                                          | Design         | 2 hours       | 25 March          | B        |
| 10 | Working on password encryption                        | Using sha256 to encrypt password and check password in login and registration              | Development    | 1 hour        | 2 April           | C        |
| 11 | Create welcome screen following the wireframe diagram | Have welcome screen ready                                                                  | Development    | 2 hours       | 8 April           | C        |
| 12 | Present the wireframe and application to the client   | Get client's feedback on the wireframe and application                                     | Planning       | 30 minutes    | 9 April           | A        |
| 13 | Make ER diagram                                       | ER diagram is created for both tables                                                      | Planning       | 40 minutes    | 9 April           | B        |
| 14 | Update record of task                                 | Record of task is up to date                                                               | Planning       | 20 minutes    | 10 April          | B        |
| 15 | Create table to show diary                            | Table is created and can show every diary belongs to that specific user                    | Development    | 3 hours       | 14 April          | C        |
| 16 | Make new diary screen                                 | Allow user to create new diary in the application and can check their diary in the table   | Development    | 3 hours       | 15 April          | C        |
| 17 | Create remove button and edit button                  | Allow user to remove and edit their diary                                                  | Development    | 5 hours       | 16 April          | C        |
| 18 | Update edit button                                    | Make new screen for editing                                                                | Development    | 1 hour        | 16 April          | C        |
| 19 | Work on average word count calculation                | Create a code to show average word count per diary                                         | Development    | 2 hours       | 16 April          | C        |
| 20 | Create flow diagram                                   | Make flow diagram for average word count code                                              | Development    | 1 hour        | 17 April          | B        |
| 21 | Update new Wireframe diagram                          | The new wireframe diagram match the UI of the application                                  | Design         | 30 minutes    | 17 April          | B        |
| 22 | Write about update                                    | Write about software update system of the application in the development part              | Planning       | 30 minutes    | 18 April          | C        |
| 23 | Work on development writing                           | Finish development with code and explanation written                                       | Development    | 6 hours       | 19 April          | C        |
| 24 | Create UML diagram                                    | UML diagram for TableScreen class is ready                                                 | Planning       | 30 minutes    | 19 April          | C        |
| 25 | Make test plan                                        | Test plan is ready and easy for tester to follow the steps                                 | Evaluation     | 2 hours       | 19 April          | B        |
| 26 | Show final product to the client                      | Get feedback or approval for client for the final product and let client test it           | Evaluation     | 15 minutes    | 20 April          | A        |
| 27 | Record video                                          | Make video to show functionality and extensibility of the application                      | Implementation | 10 minutes    | 21 April          | D        |
| 28 | Complete citation and appendix                        | Make citation and appendix                                                                 |                | 1 hour        | 21 April          | -        |
| 29 | Complete record of task                               | Complete and put record of task on github                                                  |                | 5 minutes     | 22 April          | B        |

**Table 2**: Record of Task- showing the planning and working process throughout the project. This includes, programming, documentation, client's meetings and other process from the start of the project to the due date. The table also shows the criteria and planning cycle of each activity with the time taking to complete each process.

### [Back To Top](#table-of-content)

# Criteria C-Development

## List of techniques used
- OOP paradigm
- KivyMD Library
- Relational Databases
- ORM - SQLAlchemy
- Random
- Datetime
- Pbkd2f


### 1. Developing GUI for application
KivyMD Library has been chosen to be used to create the application interface as the UI is one of the most important components in this project. I will first use decomposition to break down the setting up of GUI into 2 main parts. The first part will be in the main python file where the functionality and the setting up for each screen are happening. In the python files, 2 main parts at the setting up including the setting up for library(**figure 7**) and the running which use the method inherited from the class MDApp(**figure 8**). 

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

**Figure 7**: Setting up random, datetime,KivyMD, SQLAlchemy(ORM) and Pbkdf2 by importing necessary functions from each library.

```py
class app(MDApp):
    '''class with the same name as .kv file'''
    def build(self):
        return

k = app()
#define the variable which belong to class app to activate run method from MDApp class imported
k.run()
```
**Figure 8**: Create app class which has the same name as the kivy file to link 2 files together and to run and show the GUI a variable has to be created and designed as a class app to use the run method inherited from MDApp.


After that, I created the components of the interface screen in the kivy file. In this process, OOP paradigm in the python file and the screenmanager in kivy file will be used to breakdown the code into different classes such as LoginScreen in **figure 9** or classes which link to each screen in kivy file like the class LoginScreen in **figure 10**. In this project, the OOP paradigm will be the main coding paradigm as it allows me to have  a control over each section of the program and it also allows the inheritance which means to take attributes or methods from other classes such as LoginScreen class that inherit from MDScreen class(**figure 10**). 
```kv
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
**Figure 9**: Showing the kivy file with screenmanager which define names and id of each screen in the project. Followed by the LoginScreen part which allow me to develop the login screen with different components.

From **figure 9**, the login screen is shown to demonstrate the use of id which will be an essential part of this project. By defining id, changes can be made to the specific part of the screen. The use of id can be an example of pattern recognition by creating one variable to use repeatedly instead of creating a new variable or screen everytime. Example of the use of screen is used to complete part of the third criteria which will be the login system which use function try_login shown in **figure 10**. In this example, when the function is activated the data from the text field which we can get by using the id will be used for the login. The id can also be given to each screen which allows the switch of screen such as to open the welcome screen when the login function is completed(the method of switching screen in python is shown in **figure 11**). This makes the python file more organized as the screen can be directly from it instead of changing from the kivy file like the one shown in **figure 12**.

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
**Figure 10**: the login class in the python file that is connected to the login screen in the kivy file which allows functions to be created to be activated when a button is released. There is 1 function in this class which is used for logging in which is try_login.
  

```py
self.parent.current = "WelcomeScreen"
```
**Figure 11**: Changing screen to welcome screen in python file
  
```kv
root.parent.current = "RegisterScreen"
```
**Figure 12**: Changing screen to register screen in kivy file

### 2. Database
Database is another essential part of this project as it will be used to complete the first criteria of the client.The client wants the data to be stored when registered. To do so, the SQLAlchemy will be used to create the relation between the python file and the database created with the same library. By using SQLAlchemy, it allows me to create data table and the set up as shown in **figure 13** and link with python to manage the database in the main file. By using this database, the information that the user inputted from the text field(using id) could be stored in the user database for the login.
```py
from sqlalchemy import Column, Integer, String, create_engine
from sqlalchemy.orm import declarative_base
#import base and elements in the table and define it
Base = declarative_base()

class user(Base):
    #create table by making class of that table and name it
    __tablename__ = "user"
    #Give the detail to each column of table
    id = Column(Integer, primary_key=True)
    username = Column(String(250))
    email = Column(String(250), nullable=False)
    password = Column(String(256), nullable=False)
	
```
**Figure 13**: The separate python file called database_model.py to set up the detail of each table that will be used. In the code above, the base has been defined after different functions have been imported. After that the class to create a table was created with a table name and each column name with details such as information type and size.

One of the problems that I faced during the development of the login is that the user needs to have a unique email and unique id. To solve it, I will use the query and if-statement to check if the email has already been used by other users or not. As for the id, I will use use the method random.randint(a,b) from random module to get the random integer from a to b as shown in **figure 14**[8]. To make the id unique, the while loop will be used to query the user table by the newly generated id to compare if the id already exists or not. While the id already existed, the while loop will repeatedly generate a new id. By using the random integer, the number of users which will initially be set as 100,000 can be easily increased by simply changing the maximum amount of b in random.randint(a,b).
	
```py
def register(self):
  password = self.ids.rpassword.text
  confirm = self.ids.confirm.text
  email =  self.ids.remail.text
  username = self.ids.user.text
  # create variable to assign each id on screen to it
  check_user = session.query(user).filter(user.email == email,user.username == username).all()
  #query with email and username to check that they are unique 
  if password != "" and confirm != "":
      #Check that the confirmed password inputted is the same as the password
      if password == confirm and not check_user:
          #Create id using random number generator
          iden = random.randint(1, 100000)
          check_id = session.query(user).filter(user.id == iden).all()
          while iden == check_id:
              iden = random.randint(1, 100000)
          #query the database to check that id is unique and if not generate another random id 

          password = encrypt_password(password)
          #using encrypt function to make hash of password
          new = user(id=iden,
                      email=email,
                      username=username,
                      password=password
                  )
          session.add(new)
          session.commit()
          #input the information into the database and change screen to the welcome screen
          self.parent.current = "WelcomeScreen"

      elif password == confirm and check_user:
          #When user is already in database
          self.ids.msg.text = "User existed"
      else:
          #when password doesn't match with confirm password 
          self.ids.msg.text = "password doesn't match"
  else:
      #when password textfield is blank change the text and color of the text
      self.ids.msg.text = "password needed"
      self.ids.msg.text_color = 1, 0, 0,1
```
**Figure 14** The function above is used to check that inputted information is correct and unique for registration. After that, that information will be inputted in the database with an encrypted password. Each user will have a unique randomly generated id.

Shown in **figure 15**  Below is the function to save a new diary in the class NewItemScreen. This function is used to fulfill the forth success criteria and seventh success criteria. Starting with the breakdown of forth criteria into 2 main problems, first is to find today's date and second is to add the new data into the new table. To get the today's date, the datetime module (imported in **figure 7**) will be used to activate datetime.today(). strftime('%Y-%m-%d') method to get date in year,month and date.  The second part of the save function is to add it into the database which the database has already been setup before in **figure 13**,so the same process as the registration will be used. For the seventh criteria, I used abstraction to query the database for the username using the email that got from the textfield in the login screen. After getting the username, I will use if-statement to make a condition when the author textfield is empty to autofill with username.


```py
      def save(self):
        #function to save the new diary with 7 columns listed below
        #assign email from login screen to this email variable.
        email = self.parent.ids.loginscr.ids.email.text
        title = self.ids.title.text
        author = self.ids.author.text
        content = self.ids.content.text
        if author == "":
            #auto fill the author field if it's left blank with the username
            username = session.query(user.username).filter(user.email == self.parent.ids.loginscr.ids.email.text)
            for row in username:
                username = row[0]
            author = str(username)
        id = random.randint(1, 100000)
        day = datetime.today().strftime('%Y-%m-%d')
        #get the date and time for today and make it in YYYY-MM-DD form
        diary_id = session.query(diary).filter(diary.id == id).all()
        while id in diary_id:
          id = random.randint(1, 100000)
        #add them in database
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
        #change screen to welcome screen
```
**Figure 15**: The function to save the new diary written which works the same way as saving the new user in registration except in this function, the datetime.today() has been used to get the date when the user creates the new diary and input it into the database. 


  
```py
   def delete(self):
        #function to remove row in the datatable and also update the table
        id = self.parent.ids.OpenScreen.ids.label.text
        #use the id of the selected row
        dele = session.query(diary).filter(diary.id == id).delete()
        #delete using query with id and commit change
        session.commit()
        query = session.query(diary).filter(diary.email == self.parent.ids.loginscr.ids.email.text).all()
        print(query)
        #query with the user's email
        #define variable to update table and average
        number_of_row = 0
        total = 0
        result = []
        for q in query:

            list = q.content.split()
            total += len(list)
            number_of_row += 1
            #get total word counts and total diary
            result.append([q.id, q.title, q.date_added, q.last_update, q.author, q.content])
            # get each data in each column to update the table
        print(result)
```
**Figure 16**: Function to delete the checked row in the database using a query by id to get the row and update table and average number shown.

```py
def on_check_press(self,table,current_row):
   id,title,date_added,last_update,author,content = current_row
   print(id)
   self.parent.ids.OpenScreen.ids.label.text = id
   self.parent.ids.OpenScreen.ids.title.text = title
   self.parent.ids.OpenScreen.ids.author.text = author
   self.parent.ids.OpenScreen.ids.content.text = content
```
**Figure 17**: This is the function that will give the current_row when the check of that row in the datatable is pressed and input the selected value of that row in the Open screen.
  
Query will be the main technique to complete the success criteria 6. First part of this criteria will be removing the diary which I will use with the function on_check_press that will give the row of the the diary pressed and put the information of that diary in the OpenScreen as shown in **figure 17**. After finishing that step, we can call the id from the OpenScreen and use a query to commit the delete of that database as shown in **figure 16**. At the same time, the average and the table will also be updated. Next part of this criteria will be to create the save change function. I created another screen called OpenScreen where I used the select method  to get each value in the selected row pasted in the text field of the OpenScreen which allows the user to edit and when the save change button is pressed, the database will be updated (**figure 18**).  

```py
       def edit(self):
        # define each value with variable and query with id, then replace the data in the specific colum
        id = self.ids.label.text
        title = self.ids.title.text
        date = datetime.today().strftime('%Y-%m-%d')
        #update datetime
        author = self.ids.author.text
        content = self.ids.content.text
        #select work similar to query which will select a row and scalar_one
        upd = session.execute(select(diary).filter_by (id = id)).scalar()
        print(upd)
        upd.title = title
        upd.last_update = date
        upd.author = author
        upd.content = content
        session.commit()
        self.parent.current = "TableScreen"
```
  **Figure 18**: Function to save the change that the user made by replacing the old information with the new inputted information by defining each variable with each column data in the row using session.execute(select().filter_by()).scalar() and replace it with the inputted information from the text field using id.
  
  

```py
    def on_pre_enter(self, *args):
        """Get the data from the database"""
        query = session.query(diary).filter(diary.email == self.parent.ids.loginscr.ids.email.text).all()
        #query diary table using email to get diary that belong to specific user.
        print(query)
        result = []
        #create list to store detail of each column that would be presented in the table
        for q in query:
            result.append([q.id,q.title,q.date_added,q.last_update,q.author,q.content])
            #append all those information to the list
        #create table using MDDataTable
        self.data_tables = MDDataTable(
            size_hint =(1,0.6), #size of table
            pos_hint = {"center_x":0.5, "center_y":0.5}, #position of table
            check = True, #create check box
            column_data = [("ID",50),("Title",100),("Date added",40),("Last update",40),("Author", 40), ("Content", 100)], 
            #column name and size
            row_data = result, #input the data from the list result
        )
        self.data_tables.bind(on_row_press = self.on_row_press)
        #bind with function row_press to detect when the row has been pressed
        self.data_tables.bind(on_check_press=self.on_check_press)
        #bind with function on_check_press to detect the checkbox has been checked
        self.add_widget(self.data_tables)
        #add the table to screen
```
**Figure 19**: Function "on_pre_enter" will be used to create the datatable before the screen is opened. It will take the data from the database to insert into the data table and can be adjusted using the MDDataTable function to set the size, position, column data, row data, etc.
  
**Figure 19**  shows the function to create a table in the TableScreen class. This function will be used to show a list of diaries for each user which is the fifth success criteria. I will use the MDDatatable which is composed of KivyMD to create a data table and the use of database relation from SQL database to fill in the datatable with the information. First technique here is the on_pre_enter which is the special function name that will be activated before the screen is opened for the user to immediately have the table ready when they open the screen. Next, I will use the query method to query the database and print every needed data onto the MDDatatable using a for loop after query and append them in the list. Lastly, I will set up the column details and essential information which will be referred to information queried before to create the datatable and bind them with other functions created including on_row_press and on_check_press which is used for the edit and remove explained before. 


#### 2.4 Calculating Average Word Count
  
```py
#create variable for number of row(total diary) and total words
        number_of_row = 0
        total = 0
        for q in query:
            list = q.content.split()
            #split the content in each diary and check the length by using len then add it to the total word count
            total += len(list)
            number_of_row += 1
            #add number of diary by 1 until the last diary
        if number_of_row > 0:
            #if there is a diary the total word counts will be divide to give approximate average word count per diary in integer.
            self.ids.avg.text = f"Average word count of your diary is {total // number_of_row} words."
        else:
            #if there is 0 diary then average will be 0
            self.ids.avg.text = f"Average word count of your diary is 0 words."
```
**Figure 20**: Calculating average by calculating the total word count using split and len after query the content(the query part has been done in **figure 19**) after that it will use a loop to count the number of rows or number of diaries which then will be used to calculate the approximate word count per diary.
  
**Figure 20** will show how I solve for the eighth success criteria of the client which I will have to show the average word count of all diaries that the specific user has. I will use decomposition to break down what techniques are needed and create different steps to accomplish this. Firstly, I identified the 2 main parts needed for average which is the total word counts and number diary. Therefore, I will create 2 variables to store those values . After having those 2 variables, I will use loops to fill in those variables with values from the database. First, I will query the database to get the content column from the specific user. After that, I will use split and len to count the number of words. I chose to use a loop technique to add the word count of each diary into the variable total as it can  add 1 to number_of_row every time the loop repeats. Then, I decided to change text and display the average word count calculated by total/number_of_row. I chose to use if-statement to make a condition which will show that the average word count is 0 when the number of rows is 0 to prevent the error result. 


### 3.Password

 ```py  
from passlib.context import CryptContext
#import cryptcontext to use sha256 to create hash of user's password

pwd_context = CryptContext(
    schemes = ["pbkdf2_sha256"],
    default ="pbkdf2_sha256",
    pbkdf2_sha256__default_rounds = 30000
)
#use cryptcontext to make hash of password 30,000 times
def encrypt_password(password):
    #encrypt the inputted password
    return pwd_context.encrypt(password)


def check_password(password,hashed):
    #compare the inputted password with the inputted hash
    return pwd_context.verify(password,hashed)
```
 **Figure 21**: Setting up the cryptographic hash function to encrypt the password using function encrypt password and use check_password to verify password.
  
Another success criteria requirement that I have to meet isto secure the password that users inputted in the database. To deal with this problem, I will use algorithmic thinking to set steps to make password encryption possible. Firstly, I will use the Password Based Key Derivation Function(Pbkdf2) which will create a hash (unique code created from the function which will be very sensitive and very hard to decode [13]) using a cryptographic function called sha256. After that  will create function which would be used later for encryption as shown in **figure 21** . After that, I will use algorithmic thinking to create simple steps that the password will be used and apply those functions in the correct place. First step is to use encrypt_password function created in **figure 21** to encrypt the password in the registration screen shown in **figure 22**.

  ```py
  password = encrypt_password(password)
  ```
  **Figure 22**: This is part of the registration function(**figure 14**) which shows the use of function encrypt_password()

 The next step is to meet the third criteria which is to login using the registered password. In this part, I will break down the problem of how to compare that the encrypted and inputted are the same. In this process, another function that has been created earlier which is called "check_password" in **figure 21** will be used to verify by using the inputted password and compared with the hash. Next I will have to get the hash(password) from the database by querying a specific column  by email. This will be in the "try_login" * function in **figure 23** which will be in the LoginScreen class by doing that all the client's requirements will be met.

```py
  pwd = session.query(user.password).filter(user.email == email)
            for row in pwd:
                pwd = row[0]
            checkpass = check_password(password, pwd)  
```
**Figure 23**: This is part of the login function  which uses the checkpass to compare the password which is the variable assigned to the user's inputted password in the login screen and the hash in the database which was received by using a query.
  
### 4. Update
To develop software after the release to satisfy the user based on their feedback. The application will be automatically updated quarterly which mostly will be the corrective update which the user doesn't have to install. However, the application will also provide new features at least once a year. This type of update will be a functional update which the user will have to download from the developer's website. [11]

### [Back To Top](#table-of-content)
	
# Criteria D-Functionality and Extensibility of Product

https://user-images.githubusercontent.com/82266864/163828425-d20c6417-40ce-400f-af07-7200f3d366ba.mp4

  **Figure 26**: Video to show application functionality and extensibility
  
# Citation

1. “CryptContext Tutorial — Passlib V1.7.4 Documentation.” Passlib.readthedocs.io, passlib.readthedocs.io/en/stable/narr/context-tutorial.html. Accessed 1 Apr. 2022.
	
2. “DataTables — KivyMD 1.0.0.Dev0 Documentation.” Kivymd.readthedocs.io, kivymd.readthedocs.io/en/latest/components/datatables/index.html. Accessed 12 Apr. 2022.
	
3. Gupta, Kaustubh. “What Is KivyMD | Creating Android Machine Learning Apps Using KivyMD.” Analytics Vidhya, 30 June 2021, www.analyticsvidhya.com/blog/2021/06/creating-android-ml-app-kivymd/#:~:text=KivyMD%20is%20built%20on%20the. Accessed 27 Apr. 2022.
	
4. “How to Get Current Date and Time in Python?” Programiz.com, 2019, www.programiz.com/python-programming/datetime/current-datetime. Accessed 13 Apr. 2022.
	
5. “Insert, Updates, Deletes — SQLAlchemy 1.4 Documentation.” Docs.sqlalchemy.org, docs.sqlalchemy.org/en/14/core/dml.html. Accessed 14 Apr. 2022.
	
6. “Kivy vs Flutter | Learn the Key Differences between Kivy and Flutter.” EDUCBA, 9 July 2021, www.educba.com/kivy-vs-flutter/.
	
7. “Query API — SQLAlchemy 1.4 Documentation.” Docs.sqlalchemy.org, docs.sqlalchemy.org/en/14/orm/query.html. Accessed 22 Mar. 2022.
	
8. “Random — Generate Pseudo-Random Numbers — Python 3.8.2 Documentation.” Docs.python.org, docs.python.org/3/library/random.html. Accessed 1 Apr. 2022.
	
9. Sanyal, Sayantani. “10 Reasons Why Python Is One of the Best Programming Languages.” Analyticsinsight, 18 Feb. 2022, www.analyticsinsight.net/10-reasons-why-python-is-one-of-the-best-programming-languages/#:~:text=Python%20language%20can%20help%20automate. Accessed 20 Mar. 2022.
	
10. “Text Field — KivyMD Documentation.” Kivymd.readthedocs.io, kivymd.readthedocs.io/en/0.104.1/components/text-field/index.html. Accessed 20 Mar. 2022.
	
11. “Types of Software Updates.” Www.ibm.com, 8 Apr. 2021, www.ibm.com/docs/en/zos/2.4.0?topic=task-types-software-updates. Accessed 18 Apr. 2022.
	
12. Uwase, Ange. “Here Is the Reason Why SQLAlchemy Is so Popular.” Medium, 8 Feb. 2021, towardsdatascience.com/here-is-the-reason-why-sqlalchemy-is-so-popular-43b489d3fb00#:~:text=SQLAlchemy%20is%20the%20ORM%20of. Accessed 20 Mar. 2022.
	
13. Veness, Chris. “SHA-256 Cryptographic Hash Algorithm Implemented in JavaScript | Movable Type Scripts.” Movable-Type.co.uk, 2019, www.movable-type.co.uk/scripts/sha256.html. Accessed 2 Apr. 2022.


  
# Appendix
	
# Client Meeting note
	
### Meeting 1
Purpose: Ask for the problem and requirements
	
Response: Create application to take note or for diary
	
### Meeting 2

Purpose: Success criteria approval
	
Response: [Recording](###client-meeting-record-(success-criteria))
	
### Meeting 3

Purpose: Show first version of wireframe and login/registration/welcome screen

Respone: To update the wireframe diagram - create seperate screen for edit and show the full app next meeting

### Meeting 4

Purpose: Show the finish product

Response: -

## Whole Code
### Python file
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
#use cryptcontext to make hash of password 30,000 times
def encrypt_password(password):
    #encrypt the inputted password
    return pwd_context.encrypt(password)


def check_password(password,hashed):
    #compare the inputted password with the inputted hash
    return pwd_context.verify(password,hashed)


db_engine = create_engine("sqlite:///application_database.db")
Base.metadata.bind = db_engine
db_session = sessionmaker(bind = db_engine)
session = db_session()


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
        #make all the textfield blank when enter the screen
        self.ids.remail.text = ""
        self.ids.confirm.text = ""
        self.ids.user.text = ""
        self.ids.rpassword.text = ""
    def register(self):
        password = self.ids.rpassword.text
        confirm = self.ids.confirm.text
        email =  self.ids.remail.text
        username = self.ids.user.text
        # create variable to assign each id on screen to it
        check_user = session.query(user).filter(user.email == email).all()
        #query with email and username to check that they are unique
        if password != "" and confirm != "":
            #Check that the confirmed password inputted is the same as the password
            if password == confirm and not check_user:
                #Create id using random number generator
                iden = random.randint(1, 100000)
                check_id = session.query(user).filter(user.id == iden).all()
                while iden == check_id:
                    iden = random.randint(1, 100000)

                #query the database to check that id is unique and if not generate another random id

                password = encrypt_password(password)
                #using encrypt function to make hash of password
                new = user(id=iden,
                            email=email,
                            username=username,
                            password=password
                        )
                session.add(new)
                session.commit()
                self.parent.ids.loginscr.ids.email.text = self.ids.remail.text
                #input the information into the database and change screen to the welcome screen
                self.parent.current = "WelcomeScreen"

            elif password == confirm and check_user:
                #When user is already in database
                self.ids.msg.text = "User existed"
            else:
                #when password doesn't match with confirm password
                self.ids.msg.text = "password doesn't match"
        else:
            #when password textfield is blank change the text and color of the text
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
        #Make all the textfield blank before enter the screen
        self.ids.title.text = ""
        self.ids.author.text = ""
        self.ids.content.text = ""
    def save(self):
        #function to save the new diary with 7 columns listed below
        #assign email from login screen to this email variable.
        email = self.parent.ids.loginscr.ids.email.text
        title = self.ids.title.text
        author = self.ids.author.text
        content = self.ids.content.text
        if author == "":
            #auto fill the author field if it's left blank with the username
            username = session.query(user.username).filter(user.email == self.parent.ids.loginscr.ids.email.text)
            for row in username:
                username = row[0]
            author = str(username)
        id = random.randint(1, 100000)
        day = datetime.today().strftime('%Y-%m-%d')
        #get the date and time for today and make it in YYYY-MM-DD form
        diary_id = session.query(diary).filter(diary.id == id).all()
        while id == diary_id:
          id = random.randint(1, 100000)
        #add them in database
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
        #change screen to welcome screen


class TableScreen(MDScreen):
    data_tables = None


    def on_pre_enter(self, *args):
        """Get the data from the database"""
        query = session.query(diary).filter(diary.email == self.parent.ids.loginscr.ids.email.text).all()
        #query diary table using email to get diary that belong to specific user.
        print(query)
        result = []
        #create list to store detail of each column that would be presented in the table
        for q in query:
            result.append([q.id,q.title,q.date_added,q.last_update,q.author,q.content])
            #append all those information to the list
        #create table using MDDataTable
        self.data_tables = MDDataTable(
            size_hint =(1,0.6), #size of table
            pos_hint = {"center_x":0.5, "center_y":0.5}, #position of table
            check = True, #create check box
            column_data = [("ID",50),("Title",100),("Date added",40),("Last update",40),("Author", 40), ("Content", 100)],
            #column name and size
            row_data = result, #input the data from the list result
        )
        self.data_tables.bind(on_row_press = self.on_row_press)
        #bind with function row_press to detect when the row has been pressed
        self.data_tables.bind(on_check_press=self.on_check_press)
        #bind with function on_check_press to detect the checkbox has been checked
        self.add_widget(self.data_tables)

        #add the table to screen

        #create variable for number of row(total diary) and total words
        number_of_row = 0
        total = 0
        for q in query:
            list = q.content.split()
            #split the content in each diary and check the length by using len then add it to the total word count
            total += len(list)
            number_of_row += 1
            #add number of diary by 1 until the last diary
        if number_of_row > 0:
            #if there is a diary the total word counts will be divide to give approximate average word count per diary in integer.
            self.ids.avg.text = f"Average word count of your diary is {total // number_of_row} words."
        else:
            #if there is 0 diary then average will be 0
            self.ids.avg.text = f"Average word count of your diary is 0 words."




    def on_row_press(self,table, row):

        print(f"Item was clicked", row.text)

    def on_check_press(self,table,current_row):
        id,title,date_added,last_update,author,content = current_row
        print(id)
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
        #function to remove row in the datatbale and also update the table
        id = self.parent.ids.OpenScreen.ids.label.text
        #use the id of the selected row
        dele = session.query(diary).filter(diary.id == id).delete()
        #delete using query with id and commit change
        session.commit()
        query = session.query(diary).filter(diary.email == self.parent.ids.loginscr.ids.email.text).all()
        print(query)
        #query with the user's email
        #define variable to update table and average
        number_of_row = 0
        total = 0
        result = []
        for q in query:

            list = q.content.split()
            total += len(list)
            number_of_row += 1
            #get total word counts and total diary
            result.append([q.id, q.title, q.date_added, q.last_update, q.author, q.content])
            # get each data in each column to update the table
        print(result)

        if number_of_row>0:
            #if there is a diary then the total word count can be divided by the number of diary to show avarage word count per diary
            self.ids.avg.text = f"Average word count of your diary is {total // number_of_row} words"
        else:
            #if there is no diary then the average word count will be zero
            self.ids.avg.text =  f"Average word count of your diary is 0 words"
        #update the table with new data in from the list "result" created before
        self.data_tables.update_row_data(
            None, result
        )



class OpenScreen(MDScreen):


    def edit(self):
        # define each value with variable and query with id, then replace the data in the specific colum
        id = self.ids.label.text
        title = self.ids.title.text
        date = datetime.today().strftime('%Y-%m-%d')
        #update datetime
        author = self.ids.author.text
        content = self.ids.content.text
        #select work similar to query which will select a row and scalar_one
        upd = session.execute(select(diary).filter_by (id = id)).scalar()
        print(upd)
        upd.title = title
        upd.last_update = date
        upd.author = author
        upd.content = content
        session.commit()
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
