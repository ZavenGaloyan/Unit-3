# Python code
'''py
from kivymd.app import MDApp

class calculator(MDApp):
    def build(self):
        return
c = calculator()
c.run()
'''

# KV
'''kv
Screen:
    size: 500,500
    MDBoxLayout:
        orientation: "vertical"
        MDLabel:
            text: "0"
            halign: "right"
            font_size: '80 pt'
            size_hint:1,0.25
            valign: "top"
        MDLabel:
            text: "A calculator by Aup"
            halign: "right"
            font_size: '24 px'
            size_hint:1,0.03
            valign: "center"

        MDBoxLayout:
            orientation: "horizontal"
            size_hint: 1,0.144
            MDRaisedButton:
                size_hint: 0.25,1
                text: "AC"
                font_size: "40px"
                md_bg_color:255/255,204/255,153/255,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "+/-"
                font_size: "40px"
                md_bg_color:255/255,204/255,153/255,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "%"
                font_size: "40px"
                md_bg_color:255/255,204/255,153/255,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "/"
                font_size: "40px"
                md_bg_color:255/255,153/255,51/255,1
        MDBoxLayout:
            orientation: "horizontal"
            size_hint: 1,0.144
            MDRaisedButton:
                size_hint: 0.25,1
                text: "7"
                font_size:"40px"
                md_bg_color:0/255,0/255,0/255,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "8"
                font_size: "40px"
                md_bg_color:0,0,0,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "9"
                font_size: "40px"
                md_bg_color:0,0,0,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "x"
                font_size: "40px"
                md_bg_color:255/255,153/255,51/255,1
        MDBoxLayout:
            orientation: "horizontal"
            size_hint: 1,0.144
            MDRaisedButton:
                size_hint: 0.25,1
                text: "4"
                font_size:"40px"
                md_bg_color:0/255,0/255,0/255,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "5"
                font_size: "40px"
                md_bg_color:0,0,0,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "6"
                font_size: "40px"
                md_bg_color:0,0,0,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "-"
                font_size: "40px"
                md_bg_color:255/255,153/255,51/255,1
        MDBoxLayout:
            orientation: "horizontal"
            size_hint: 1,0.144
            MDRaisedButton:
                size_hint: 0.25,1
                text: "1"
                font_size:"40px"
                md_bg_color:0/255,0/255,0/255,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "2"
                font_size: "40px"
                md_bg_color:0,0,0,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "3"
                font_size: "40px"
                md_bg_color:0,0,0,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "+"
                font_size: "40px"
                md_bg_color:255/255,153/255,51/255,1
        MDBoxLayout:
            orientation: "horizontal"
            size_hint: 1,0.144
            MDRaisedButton:
                size_hint: 0.5,1
                text: "0"
                font_size: "40px"
                md_bg_color:0,0,0,1
                border: (30,30,30,30)
            MDRaisedButton:
                size_hint: 0.25,1
                text: "."
                font_size: "40px"
                md_bg_color:0,0,0,1
            MDRaisedButton:
                size_hint: 0.25,1
                text: "="
                font_size: "40px"
                md_bg_color:255/255,153/255,51/255,1
'''

# Test 
<img width="804" alt="calculator" src="https://user-images.githubusercontent.com/82266864/156272824-48fb69db-c781-40f5-bbe8-980037e94733.png">
