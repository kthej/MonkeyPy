# To Do
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
example: an f-string will become Lang.format(
## Examples

import Draw
event Update:
    Draw.color(foreground,background)
    Draw.text("Hello World",x ,y ,font, justify) # Font and justify will default to predefined fonts and justifications


## Required headers (onUpdate, onLayout, etc)
Stylized by 'event'

event Update:    <-- This is mandatory to exist for all types of apps
    code to run in the onUpdate loop
    
event Sleep:
    code to run when the watch goes into sleep mode, for watch faces

event Wake:
    code to run when the watch comes out of sleep mode, for watch faces

event Key:
    code to run when a button is pressed and released.
    Key() will return which key was pressed
    
event Touch:
    # code to run when the screen is touched.
    Touch() returns the coordinates of where the screen was touched as tuple
    only supports tapping.

event Swipe:
    code to run when the screen is swiped.
    Swipe() returns the direction of the swipe as a direction like DIR.RIGHT.
    Only supports up,down,left,right
    
## The Menu Class

- Only does Menu2
- is built as a class, requiring importing
- Has a special event-like header, called menu

### example creation and usage

import Menu (imports it, only import it if you need to use it)

MainMenu = Menu(
"Title",
[
["id1","Label", "SubLabel"],


]
)



menu MainMenu: (this code is referenced when a menu2 is launched, this one here is just called MainMenu, can be whatever)
    item1: (this is the ID of each menu item. This means that id's in the menu creation
    
    





