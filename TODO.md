# To Do
- Find most common and useful classes, simplify into one class, have each class be something like Drawing (for Dc), or Storage (for application.storage)
- Enhance readme (this is intended for users unfamiliar with Monkey C)
- 

## Write simplified syntax for toyboxes
Toybox.System -> Sys
Toybox.Application.Storage -> Store
Toybox.Graphics -> Draw
Toybox.Sensors -> Sense


## Required headers (onUpdate, onLayout, etc)
Stylized by 'event'

event Update:    <-- This is mandatory to exist for all types of apps
    # code to run in the onUpdate loop
    
event Sleep:
    # code to run when the watch goes into sleep mode, for watch faces

event Wake:
    # code to run when the watch comes out of sleep mode, for watch faces

event Key:
    # code to run when a button is pressed.
    # can determine which key because 
    Key() will return which key was pressed
    
event Touch:
    # code to run when the screen is touched.
    Touch() returns the coordinates of where the screen was touched

event Swipe:
    # code to run when the screen is swiped.
    # Swipe() returns the direction of the swipe.





