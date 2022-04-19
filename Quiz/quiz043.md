# Code

### Python File
```py

from kivymd.app import MDApp
from kivymd.uix.screen import MDScreen
#import md app to run the kivymd
#import mdscreen to inherit and link with screen in the kivy file

#create class for each screen with pass as there is no function needed
class LoginScreen(MDScreen):
    pass
class MainScreen(MDScreen):
    pass
class NewItemScreen(MDScreen):
    pass

class quiz43(MDApp):
    #class with the same name as the kivy file to use build function to build app
    def build(self):
        return

#create a variable that belong to class quiz43 to run the code
test = quiz43()
test.run()

```


### Kivy file

```kv

ScreenManager:
    #define each screen with name in the screen manager
    LoginScreen:
        name: "LoginScreen"
    MainScreen:
        name: "MainScreen"
    NewItemScreen:
        name: "NewItemScreen"

<LoginScreen>:
#organize interface for login screen
    MDRaisedButton:
        #Use button and set position, text, and size
        text: "Log in"
        pos_hint: {"center_x":.5,"center_y": .3}
        size_hint: 0.5,0.05
        on_release:
            #When it is released it will change screen to main screen
            root.parent.current = "MainScreen"

<MainScreen>
#Code for interface of the main screen
    MDLabel:
        #Label(text)
        text: "Main Screen"
        # Center horizontally and set position for y coordinate
        halign: "center"
        pos_hint: {"center_y":.9}
        #set fond style to be Heading 3
        font_style: "H3"
    MDRaisedButton:
    #Create another button and set the on release to be new item screen
        text: "New"
        pos_hint: {"center_x":.5,"center_y": .7}
        size_hint: 0.5,0.05
        on_release:
            root.parent.current = "NewItemScreen"
    MDRaisedButton:
        text: "List"
        pos_hint: {"center_x":.5,"center_y": .5}
        size_hint: 0.5,0.05
    MDRaisedButton:
        text: "Log out"
        pos_hint: {"center_x":.5,"center_y": .3}
        size_hint: 0.5,0.05
        on_release:
            root.parent.current = "LoginScreen"
<NewItemScreen>
#interface of new item screen
    MDLabel:
        text:"New"
        halign: "center"
        pos_hint: {"center_y":.9}
        font_style: "H3"
    MDRaisedButton:
        text: "Back"
        pos_hint: {"center_x":.5,"center_y": .1}
        size_hint: 0.5,0.05
        on_release:
            root.parent.current = "MainScreen"

```


# Test

Uploading Screen Recording 2565-04-19 at 19.44.34.mov…

