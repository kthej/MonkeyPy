# IDEAS

- Find most common and useful classes, simplify into one class, have each class be something like Drawing (for Dc), or Storage (for application.storage)
- Enhance readme (this is intended for users unfamiliar with Monkey C)
- First goal: Get language up and running for watch faces.
- Do not release until after mission

## Write simplified syntax for toyboxes

Toybox.System -> Sys
Toybox.Application.Storage -> Store
Toybox.Graphics -> Draw
Toybox.Sensors -> Sense
Graphics.COLOR_COLOR -> COLOR.RED
Graphics.TEXT_JUSTIFY_RIGHT -> JUSTIFY.RIGHT


## Conventions
Constants will each have their own class, but each constant is all caps.
Constant classes will have all items in caps, including class definitions, to separate from other classes that have functions.
Example: COLOR.RED

## Misc
String concantenation and other python native things are not native in MonkeyC, so special functions will be made accordingly and called whenever a python type item is called
example: an f-string will become Lang.format
## Examples

import Draw
event Update:
    Draw.color(foreground,background)
    Draw.text("Hello World",x ,y ,font, justify) # Font and justify will default to predefined fonts and justifications


## Required headers (onUpdate, onLayout, etc)
Stylized by 'event'

```python

event Update:    # This is mandatory to exist for all types of apps
    #code to run in the onUpdate loop
    
event Sleep:
    #code to run when the watch goes into sleep mode, for watch faces

event Wake:
    #code to run when the watch comes out of sleep mode, for watch faces

event Key:
    #code to run when a button is pressed and released.
    #Key() will return which key was pressed
    
event Touch:
    # code to run when the screen is touched.
    #Touch() returns the coordinates of where the screen was touched as tuple
    #only supports tapping, dragging not supported. This is for simplicity

event Swipe:
    #code to run when the screen is swiped.
    #Swipe() returns the direction of the swipe as a direction like DIR.RIGHT.
    #Only supports up,down,left,right
```
## The Menu Class

- Only does Menu2
- is built as a class, requiring importing
- Has a special event-like header, called menu
- For every time a Menu class is called, an xml is created accordingly

### Menu example creation and usage

```python

import Menu #(imports it, only import it if you need to use it)

MainMenu = Menu(
"Title",
[
["id1","Label", "SubLabel","IconPath"], #Only id and label are required, sublabel and icon path default
["id2","Label2","SubLabel2","IconPath2"]
],
"DefaultIconPath" #For menu-wide icon path
)

menu MainMenu: #this code is referenced when a menu2 is launched, this one here is just called MainMenu, can be whatever
    item1: #this is the ID of each menu item. This means that id's in the menu creation must not have spaces. throw error if a space is caught.
        #code to run when this item is selected
        # by default, does not exit upon clicking, but can go back by doing
        MainMenu.goBack()
```

## Special Input modes
- Other special select options, other than menu
- Text Input
- Yes / No (for confirmation)
- Number Picker
- Date Picker
- Time Picker
~~- Multiple Choice~~ too complex for MonkeyPy

all handled by Input class

## Example usage

```python

import Input

event Update:
    Input.bool(codeIfTrue,codeIfFalse)
    Input.text("defaultText") # stuff in parens specifies what to put when launching text picker
    Input.num("defaultNum")
    Input.time("defaultTime") # All time formats are in 24 hour. A special time class will allow for switching from 24 to 12 hour
    
    

```
    


## Resources
- Some watches have different shapes, we need to handle resource management for different devices
- Layouts, graphics, anything, are all handled in a single file, called the config file.
- Variables are called with the Config class
perhaps something like

```python
config Default: # default layout, variables, whatever. Not required if config doesn't exist, but if at least one other configuration exists, this must exist.
    clock_x = 10% # or 20px
    clock_y = 50%

    

config Shape "semioctagon": # for layouts of specific shape
    clock_y = 30%
    clock_y = 50%

config Model "instinct3solar45mm": # for layouts of specific models. Will make list later.
    layout params

config Dimensions 245 245: # for layouts of specific dimensions



#usage in main code block:
import Config

Config.path = "path to file of config" # this is so you can tell where to put the config file.

event Update:
    Draw.color(COLOR.RED,COLOR.CLEAR) # clear is the same as transparent, makes it easier to type than transparent
    Draw.text(
    f"{hours}:{minutes}",
    Config.clock_x,#clock_x is called for the specific device or specs only, varies per watch, so clock_x will be different per model
    Config.clock_y,# same for clock y
    FONT.SMALL,
    JUSTIFY.CENTER
    )

```

## Files and other stuff

MonkeyPy logic will have the extension .mpy
Config files will have the same extension. 
Accessing bitmaps and shapes will be handled by a very similar logic to ```open()``` like python,
just open(file) to access the image. This will be the passing for things like bitmaps or vector images.
.FNT files will be handled differently, since they need to be loaded differently and work differently. 

## Conventions

All Monkey C native classes are turned into simpler classes (Activity.Sensor -> Sense), but all retain capital first letter, lowercase rest.
Importing other files must include the file extension.

```python
import Config.mpy #is allowed and the only way to import other .mpy files.

import Config # is NOT allowed


```
