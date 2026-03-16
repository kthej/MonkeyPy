# Events

## Overview

In Monkey C, the tasks that draw the layout, handle input, or load menus are all types of functions in certain classes.
For example, the task that is called every time the screen is redrawn is called ```onUpdate()```. 

The structure, inheritance and accessing for these functions will be taken care of on project creation and while programming, will be handled by special predefined functions called events.

In MonkeyC, for example, the drawing loop is handled like so:

```C++
function onUpdate(){
    // Code to run
}
```

whereas in MonkeyPy, it will be handled like so:

```python

event Update:
    
    # Code to run

```

There are several different types of events, each handles a specific type of trigger:

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

## Update

```event Update:```

This is required to be in every project.
This is called either every second (if in high power mode), or when ```Update()``` is called somewhere else. 
This is the ```onUpdate()``` function in MonkeyC. ```Update()``` is the ```WatchUi.requestUpdate()``` function in MonkeyC.



## Sleep

``` event Sleep:```

This is called when the watch is enters its low power mode.
It is the equivalent of MonkeyC's ```onEnterSleep()```.

## Wake

``` event Wake:```

Called when the watch exits high power mode.
It is the equivalent of MonkeyC's ```onExitSleep()```

## Key

``` event Key:```

Called when a key is pressed and released. Does not support holding.

```Key()``` Returns which key was pressed. 

InputDelegates and prerequisites will be handled by the transpiler.

## Swipe

``` event Swipe:```

Called after the touchscreen is swiped. 

```Swipe()``` returns which direction as a direction object 

DIR.UP, DIR.DOWN, DIR.LEFT, or DIR.RIGHT

## Touch

Called after the screen is tapped.
```Touch()``` returns the x and y location of the tap as a tuple

(132, 54)

## Settings

```event Settings()```

Called after one of the following:

    - Key up is pressed and held (button watches)
    - Key back is pressed and held (touchscreen watches)
    - The menu button is pressed (any other type of watch)




