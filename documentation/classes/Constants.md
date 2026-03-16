# Constant Libraries

## Color

### Importing

```python
import COLOR
```

### Items
needs to be updated to fit all MonkeyC colors

```
COLOR.RED
COLOR.ORANGE
COLOR.YELLOW
COLOR.GREEN
COLOR.BLUE
COLOR.PURPLE
COLOR.BLACK
COLOR.WHITE
COLOR.CLEAR # In Monkey C, this is called TRANSPARENT, but changed to CLEAR as it's easier to type
```

## Text Justifying

### Importing

```python
import JUSTIFY
```

### Items

```

JUSTIFY.LEFT           # Justifies text to the left of the x coordinate; the y coordinate represents the baseline.
JUSTIFY.LEFT_TOP       # Justifies text to the left of the x coordinate and anchors the top to the y coordinate.
JUSTIFY.LEFT_BOTTOM    # Justifies text to the left of the x coordinate and anchors the bottom to the y coordinate.
JUSTIFY.LEFT_CENTER    # Justifies text to the left of the x coordinate and centers it vertically on the y coordinate.

JUSTIFY.RIGHT          # Justifies text to the right of the x coordinate; the y coordinate represents the baseline.
JUSTIFY.RIGHT_TOP      # Justifies text to the right of the x coordinate and anchors the top to the y coordinate.
JUSTIFY.RIGHT_BOTTOM   # Justifies text to the right of the x coordinate and anchors the bottom to the y coordinate.
JUSTIFY.RIGHT_CENTER   # Justifies text to the right of the x coordinate and centers it vertically on the y coordinate.

JUSTIFY.CENTER         # Justifies text centered horizontally and vertically on the (x, y) coordinates.
JUSTIFY.CENTER_TOP     # Centers text horizontally on the x coordinate and anchors the top to the y coordinate.
JUSTIFY.CENTER_BOTTOM  # Centers text horizontally on the x coordinate and anchors the bottom to the y coordinate.
JUSTIFY.CENTER_CENTER  # Same as JUSTIFY.CENTER, but provided in case someone prefers the <HORIZ>_<VERT> format.

```

### Special Notes

The first word after JUSTIFY is how it is aligned horizontally, the second is how it is vertically. Think of it like <x,y> except it is for alignment.

