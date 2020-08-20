Inkplate GUI designer 
=====================

Nomenclature
############

Component
---------
    | Primitive or widget, object representation that can be drawn to screen on Inkplate or in web editor.

Entity
------
    | Component but in code, or when rendering.
 
Primitives and widgets
----------------------
    | A design component can be a primitive or a widget.
    | Primitives are simple drop in replacements of Arduino API elements.
    | Widgets on the other hand are more complex, and can't have their attributes changed using simple editables.
    | Located on the left of the main screen.

Editables
---------
    | Sliders, input boxes, buttons etc. on the right of the screen.

Modifiers
---------
    | Draggable elements on screen, also mutable by editables if specified.
    | Also, by clicking on those after a red dot appears changes settings tab to current component.

Exporting code
##############
    | After you're done with editing, simlpy click on "Export C Code" in the upper left corner.
    | A download prompt will show and upon accepitng it a header file will be downloaded.
    | Simply put the file in the same folder as your sketch, include it by putting:

    .. code-block:: C

        #include "generatedUI.h"

    | With all your other includes.

In code rendering
#################
    | Be sure to call mainDraw(); in your code when you want it to draw prespecified content.
    | You must clear the buffer before hand by calling display.clearDisplay();
    | and call display.display(); after mainDraw(); to put data on screen.

Custom data rendering
#####################
    | Of course you can leave the default values to be drawn on screen, but where's the fun in that.
    | To change primitive or widget data, simply acces a global variable in C.
    | You can find it's name in editor, on the top left, 
    | where it says Editing [ name ] and adding _[ whatever property you want to change]
    | Example:

    .. code-block:: C

        line0_start_x = 0;

    | Find all changeable properties under primitives and widgets documentation.
    | Note that you can't change bitmap width or height afterwards, indicated by their const declaration in generated header.

Editing widgets
###############
    | To be sure that widgets are as customizable as possible, they directly allow you to eddit their variables.
    | You can edit their JSON file by changing data under default or writing newer data into value slot, first one is always supported,
    | while second one is not guarantied.
    | To enter values click somewhere on screen to change focus.

Making widgets
##############
    | We strongly incourage those familiar with JavaScript to try their luck making widgets.
    | Take a look in our source, under widgets/clock.js or graph.js.
    | Basicaly all there needs to be is name, type (widget), id initialized to 0, 
    | variables shown to user, draw function (here used as a helper to _draw method),
    | getCCodeVariables (to be put globally) and getCCodeDraw (to be put into mainDraw);
    |
    | You can also specify getIncludes to include fonts or other.
    | Be sure to also push your widget object to widgets array to be deep cloned later into entites array.
    |
    | As for modifiers, make sure that in your variables you put set and distSqr (distance squared) functions into a specific variable.
    |
    | z value is default 0 to be rendered same priority as all, but can be changed, might even as a editable.

Using fonts
###########
    | Our editor does not include fonts, that needs to be done locally.
    | Easiest way is to use fonts already included in library, see https://learn.adafruit.com/adafruit-gfx-graphics-library/using-fonts
    | for list.
    |
    | Fonts **need** to be specified like this:
    | [ editor size ]px [ c font name ]
    | Example:
    | 32px FreeSansBold24pt7b

Primitives list
###############
    
Line
----
    | Basic line.

Modifiers
    | start - coordinate (accessed through _x and _y suffixes in c)
    | end - coordinate (accessed through _x and _y suffixes in c)

Editables
    | start - coordinate (accessed through _x and _y suffixes in c)
    | end - coordinate (accessed through _x and _y suffixes in c)
    | color - integer
    | thickness - float
    | gradient - float

Rectangle
---------
    | Basic rectangle.

Modifiers
    | a - coordinate (accessed through _x and _y suffixes in c)
    | b - coordinate (accessed through _x and _y suffixes in c)

Editables
    | a - coordinate (accessed through _x and _y suffixes in c)
    | b - coordinate (accessed through _x and _y suffixes in c)
    | color - integer (0 to 7)
    | fill - bool
    | radius - integer (round corners)

Circle
------
    | Basic circle.

Modifiers
    | center - coordinate (accessed through _x and _y suffixes in c)

Editables
    | radius - integer 
    | color - integer (0 to 7)
    | thickness - float
    | gradient - int (0 to 7, should be more than color to be used)

Triangle
--------
    | Basic triangle.

Modifiers
    | a - coordinate (accessed through _x and _y suffixes in c)
    | b - coordinate (accessed through _x and _y suffixes in c)
    | c - coordinate (accessed through _x and _y suffixes in c)

Editables
    | a - coordinate (accessed through _x and _y suffixes in c)
    | b - coordinate (accessed through _x and _y suffixes in c)
    | c - coordinate (accessed through _x and _y suffixes in c)
    | color - integer (0 to 7)
    | fill - bool

Text
----
    | Basic text element.

Modifiers
    | cursor - coordinate (accessed through _x and _y suffixes in c

Editables
    | cursor - coordinate (accessed through _x and _y suffixes in c)
    | content - text
    | font - font (be sure to put editor size followed by font name in c, see "Using fonts" for example)
    | color - integer (0 to 7)

Bitmap
------
    | Basic bitmap, dithers and stores data into an array.

Modifiers
    | a - coordinate (accessed through _x and _y suffixes in c)
    | b - coordinate (accessed through _x and _y suffixes in c)

Editables
    | a - coordinate (accessed through _x and _y suffixes in c)
    | b - coordinate (accessed through _x and _y suffixes in c)
    | url - file (all standard image formats supported)

Widgets list
############

Graph
-----
    | As seen in bitcoin tracker example.
    | On screen always draws a sine function.

Modifiers
    | a - coordinate (accessed through _x and _y suffixes in c)
    | b - coordinate (accessed through _x and _y suffixes in c)

Editables
    | a - coordinate (accessed through _x and _y suffixes in c)
    | b - coordinate (accessed through _x and _y suffixes in c)
    | data - array to be filled in C, or in editor for advaced uses

Clock
-----
    | Simple auto scalable clock.

Modifiers
    | center - coordinate (accessed through _x and _y suffixes in c)

Editables
    | center - coordinate (accessed through _x and _y suffixes in c)
    | size - int
    | h - int (hours to be displayed)
    | m - int (minutes to be displayed) 
