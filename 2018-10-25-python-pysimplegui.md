---
layout: post
title:  python-pysimplegui
date:   2018-10-25 05:49:54 +0200
category: Dev
tags: [Python]
---

<https://github.com/MikeTheWatchGuy/PySimpleGUI>

<https://pysimplegui.readthedocs.io/tutorial/>

```python
import PySimpleGUI as sg

# Very basic window.  Return values as a list

layout = [
          [sg.Text('Please enter your Name, Address, Phone')],
          [sg.Text('Name', size=(15, 1)), sg.InputText('name')],
          [sg.Text('Address', size=(15, 1)), sg.InputText('address')],
          [sg.Text('Phone', size=(15, 1)), sg.InputText('phone')],
          [sg.Submit(), sg.Cancel()]
         ]

window = sg.Window('Simple data entry window').Layout(layout)
button, values = window.Read()

print(button, values[0], values[1], values[2])
```