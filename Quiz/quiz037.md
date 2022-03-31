# Python
```py

from kivy.lang import Builder
from kivymd.app import MDApp

class quiz(MDApp):
    def build(self):
        return
    def convert(self):
        self.root.ids.yen.text = str(int(self.root.ids.usd.text)*121.74)

q = quiz()
q.run()

```
# Kivymd

```kv
Screen:
    size:500,500

    MDBoxLayout:
        orientation: "horizontal"
        size_hint: .8,.25
        pos_hint: {"center_x": .5, "center_y":.5}
        spacing:100
        MDTextField:
            id: usd
            hint_text: "USD"
            text_color:0,0,0,1
            mode: "rectangle"
            size_hint: .3,1
        MDRaisedButton:
            size_hint: .4,1
            center_y: .5
            font_size: "20pt"
            md_bg_color: 0.2392,.8314,.5216,.8124
            text: "Convert"
            on_release:
                app.convert()
        MDTextField:
            id: yen
            text: ""
            hint_text: "JPY"
            font_size: "10pt"
            text_color: 0,0,0,1
            mode: "rectangle"
            size_hint: .3,1

```

# Test

<img width="801" alt="App" src="https://user-images.githubusercontent.com/82266864/161064877-5da25778-980e-42d0-b5f2-80368f41bd07.png">
