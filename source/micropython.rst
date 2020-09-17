Inkplate MicroPython
====================

.begin() method
###############
    | Before calling any display method you **must** call .begin() like this: 

    .. code-block:: python

        display.begin()

* **Description**:

    If you forget to do this most method calls will result in core panick and esp32 resetting.
    After you've called this you can proceed calling all other methods described below.


.drawPixel()
######################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: python

    .drawPixel(x, y, color)

* **Arguments and return value**:
    | **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel()
    | Draws one pixel at x0, y0 in desired color.
    | Requires .display() to be called afterwards to update the screen,
    | See below.

* **Example**:
    .. code-block:: python

        display.drawPixel(100, 50, display.BLACK)

* **Result**:
    | Here is what the code above produces:
    | Quite small, isn't it.

    .. image:: images/IMG_4345.jpg
        :width: 600



.clearDisplay()
###############

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: python

    .clearDisplay()

* **Arguments and return value**:
    | No Arguments

    Returns nothing.

* **Description**:
    | Clears all data in buffer.

* **Example**:
    .. code-block:: python

        display.clearDisplay()


.display()
##########

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: python

    .display()

* **Arguments and return value**:
    | No Arguments

    Returns nothing.

* **Description**:
    | Displays all data in frame buffer to screen.

* **Example**:
    .. code-block:: python

        # Any drawing code
        display.drawPixel(10, 100, display.BLACK)

        display.display()


.partialUpdate()
################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: python

    .partialUpdate()

* **Arguments and return value**:
    | No Arguments

    Returns nothing.

* **Description**:
    | Updates only the changed parts of the screen.
    | After a few updates creates blurry parts of the screen.
    | Fixed by calling .clean()

* **Example**:
    .. code-block:: python

        display.drawPixel(100, 50, display.BLACK)

        display.partialUpdate()

        display.drawPixel(100, 100, display.BLACK)



.setRotation()
##############

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: python

    .setRotation(r)

* **Arguments and return value**:
    | **r** - screen rotation.

    Returns nothing.

* **Description**:
    | Rotates the screen to be used in different orientations.
    | Default is 2, to fip 180 input 4
    | 1 and 3 are for portait mode.
    | Once flipped coordinate space remains to have the origin in the top left corner.

* **Example**:
    .. code-block:: python
        
        display.setRotation(3)

        display.setCursor(100, 100)
        display.print("INKPLATE6")

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4347.jpg
        :width: 600



.selectDisplayMode()
####################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: python

    .selectDisplayMode(_mode)

* **Arguments and return value**:
    | **_mode** - New display mode, display.INKPLATE_1BIT or display.INKPLATE_3BIT.

    Returns nothing.

* **Description**:
    | Changes the screen mode to from monochrome to 3 bit grayscale or vice versa.

* **Example**:
    .. code-block:: python

        display.selectDisplayMode(INKPLATE_3BIT)


.getDisplayMode()
#################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: python

    .getDisplayMode()

* **Arguments and return value**:
    | No arguments.

    Returns currently set display mode.

* **Description**:
    | Used to determine which display mode is currently used.
    | Returns INKPLATE_1BIT or INKPLATE_3BIT.

* **Example**:
    .. code-block:: python

        if(display.getDisplayMode() == INKPLATE_3BIT)
            print("I'm in grayscale mode!")


.clean()
########

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: python

    clean()

* **Arguments and return value**:
    | No arguments.

    Returns nothing.

* **Description**:
    | Cleans the actual screen of any possible burn in.
    | Should not be used in intervals less than 5 seconds.

* **Example**:
    .. code-block:: python

        display.clean()


.drawFastVLine()
################

* **Method prototype**:

.. code-block:: python

    drawFastVLine(x, y, h, color)

* **Arguments and return value**:
    | **x** - x coordinate of the line start point
    | **y** - y coordinate of the line start point
    | **h** - line height
    | **color** - line color

    Returns nothing.

* **Description**:
    | Draw a perfectly vertical line.
    | Garantees to be faster than regular line draw.

* **Example**:
    .. code-block:: python

        display.drawFastVLine(100, 100, 400, 0)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4354.jpg
        :width: 600



.drawFastHLine()
################

* **Method prototype**:

.. code-block:: python

    drawFastHLine(x, y, w, color)

* **Arguments and return value**:
    | **x** - x coordinate of the line start point
    | **y** - y coordinate of the line start point
    | **w** - line width
    | **color** - line color

    Returns nothing.

* **Description**:
    | Draw a perfectly horizontal line.
    | Garantees to be faster than regular line draw.

* **Example**:
    .. code-block:: python

        display.drawFastHLine(100, 100, 600, 0)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4355.jpg
        :width: 600



.fillRect()
###########

* **Method prototype**:

.. code-block:: python

    fillRect(x, y, w, h, color)

* **Arguments and return value**:
    | **x** - x coordinate of the rectangle
    | **y** - y coordinate of the rectangle
    | **w** - rectangle width
    | **h** - rectangle height
    | **color** - rectanle color, in range [0, 6]

    Returns nothing.

* **Description**:
    | Draws a filled rectangle on the screen.

* **Example**:
    .. code-block:: python

        display.fillRect(random(0, 799), random(0, 599), 30, 30, random(0, 7))

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4356.jpg
        :width: 600




.fillScreen()
#############

* **Method prototype**:

.. code-block:: python

    fillScreen(color)

* **Arguments and return value**:
    | **color** - color of the screen after filling.

    Returns nothing.

* **Description**:
    | Fills the whole screen to a solid color.

* **Example**:
    .. code-block:: python

        display.fillScreen(0)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4357.jpg
        :width: 600



.drawLine()
###########

* **Method prototype**:

.. code-block:: python

    drawLine(x0, y0, x1, y1, color)

* **Arguments and return value**:
    | **x0** - Start point x coordinate.
    | **y0** - Start point y coordinate.
    | **x1** - End point x coordinate.
    | **y1** - End point y coordinate.
    | **color** - Line color.

    Returns nothing.

* **Description**:
    | General purpose line drawing function.
    | If the line is vertical or horizontal it is recommended to use drawFastHLine or drawFastVLine,
    | although drawLine automatically checks and uses faster drawing function if needed.

* **Example**:
    .. code-block:: python

        #Diagonal lines
        display.drawLine(0, 0, 799, 599, 0)
        display.drawLine(799, 0, 0, 599, 0)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4358.jpg
        :width: 600

.drawRect()
###########

* **Method prototype**:

.. code-block:: python

    drawRect(x, y, w, h, color)

* **Arguments and return value**:
    | **x** - Rectangle x coordinate.
    | **y** - Rectangle y coordinate.
    | **w** - Rectangle width.
    | **h** - Rectangle height.
    | **color** - Rectangle color (edges only, see fillRect for fully filled one).

    Returns nothing.

* **Description**:
    | Draws and empty (not filled) rectangle.

* **Example**:
    .. code-block:: python

        display.drawRect(200, 200, 400, 300, 0)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4359.jpg
        :width: 600

.drawCircle()
#############

* **Method prototype**:

.. code-block:: python

    drawCircle(x0, y0, r, color)

* **Arguments and return value**:
    | **x0** - Circle center x coordinte.
    | **y0** - Circle center y coordinate.
    | **r** - Circle radius.
    | **color** - Circle color (just the edge, see fillCircle for fully filled).

    Returns nothing.

* **Description**:
    | Draws an empty(not filled) circle.

* **Example**:
    .. code-block:: python

        display.drawCircle(400, 300, 75, 0)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4360.jpg
        :width: 600


.fillCircle()
#############

* **Method prototype**:

.. code-block:: python

    fillCircle(x0, y0, r, color)

* **Arguments and return value**:
    | **x0** - Circle center x coordinte.
    | **y0** - Circle center y coordinate.
    | **r** - Circle radius.
    | **color** - Circle color (fully filled).


    Returns nothing.

* **Description**:
    | Draws a filled circle to screen in a supplied color.

* **Example**:
    .. code-block:: python

        display.fillCircle(random(0, 799), random(0, 599), 15, random(0, 7))

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4361.jpg
        :width: 600



.drawTriangle()
###############

* **Method prototype**:

.. code-block:: python

    drawTriangle(x0, y0, x1, y1,
      x2, y2, color)

* **Arguments and return value**:
    | **x0** - First point x coordinate.
    | **y0** - First point y coordinate.
    | **x1** - Second point x coordinate.
    | **y1** - Second point y coordinate.
    | **x2** - Third point x coordinate.
    | **y2** - Third point y coordinate.
    | **color** - Triangle edge color(see fillTriangle for a fully filled one).

    Returns nothing.

* **Description**:
    | Draw an empty rectangle to screen.

* **Example**:
    .. code-block:: python

        display.drawTriangle(250, 400, 550, 400, 400, 100, 0)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4362.jpg
        :width: 600


.fillTriangle()
###############

* **Method prototype**:

.. code-block:: python

    fillTriangle(x0, y0, x1, y1,
      x2, y2, color)

* **Arguments and return value**:
    | **x0** - First point x coordinate.
    | **y0** - First point y coordinate.
    | **x1** - Second point x coordinate.
    | **y1** - Second point y coordinate.
    | **x2** - Third point x coordinate.
    | **y2** - Third point y coordinate.
    | **color** - Triangle fill color.

    Returns nothing.

* **Description**:
    | Draw a rectangle filled with a certain color.

* **Example**:
    .. code-block:: python

        display.fillTriangle(300, 350, 500, 350, 400, 150, 0)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4363.jpg
        :width: 600


.drawRoundRect()
################

* **Method prototype**:

.. code-block:: python

    drawRoundRect(x0, y0, w, h,
      radius, color)

* **Arguments and return value**:
    | **x0** - Rectangle x coordinate.
    | **y0** - Rectangle y coordinate.
    | **w** - Rectangle width.
    | **h** - Rectangle height.
    | **radius** - Curvature radius of the edges.
    | **color** - Rectangle edges color (for a fully filled one see fillRoundRect).

    Returns nothing.

* **Description**:
    | Draws an empty (not filled) rectangle with round edges to screen.

* **Example**:
    .. code-block:: python

        display.drawRoundRect(200, 200, 400, 300, 10, 0) 

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4364.jpg
        :width: 600



.fillRoundRect()
################

* **Method prototype**:

.. code-block:: python

    fillRoundRect(x0, y0, w, h,
      radius, color)

* **Arguments and return value**:
    | **x0** - Rectangle x coordinate.
    | **y0** - Rectangle y coordinate.
    | **w** - Rectangle width.
    | **h** - Rectangle height.
    | **radius** - Curvature radius of the edges.
    | **color** - Rectangle fill color.

    Returns nothing.

* **Description**:
    | Draws a fully filled rectangle with rounded corners to screen.

* **Example**:
    .. code-block:: python

        display.fillRoundRect(200, 200, 400, 300, 10, 0)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4365.jpg
        :width: 600

.drawBitmap()
#############

* **Method prototype**:

.. code-block:: python

    drawBitmap(x, y, b, w, h)

* **Arguments and return value**:
    | **x** - Bitmap x coordinate.
    | **y** - Bitmap y coordinate.
    | **b** - Bytearray to draw from.
    | **w** - Bitmap width.
    | **h** - Bitmap height.
  
    Returns nothing.

* **Description**:
    | Draws a monochrome bitmap to screen. 
    | To get image data, use LCD image Converter.

* **Example**:
    .. code-block:: python

        display.drawBitmap(100, 250, logo, 576, 100)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4366.jpg
        :width: 600


.drawImageFile()
################

* **Method prototype**:

.. code-block:: python

    drawBitmap(x, y, path, invert=False)

* **Arguments and return value**:
    | **x** - Bitmap x coordinate.
    | **y** - Bitmap y coordinate.
    | **path** - File path e.g. "sd/file.bmp"
    | **w** - Bitmap width.
    | **h** - Bitmap height.
    | **invert** - Inverts color.
  
    Returns nothing.

* **Description**:
    | Draws a bitmap file to screen. 

* **Example**:
    .. code-block:: python

        display.drawBitmap(100, 250, "sd/file.bmp", 576, 100)

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4366.jpg
        :width: 600


.setTextSize()
########################

* **Method prototype**:

.. code-block:: python

    setTextSize(s)

* **Arguments and return value**:
    | **s** - font scale

    Returns nothing.

* **Description**:
    | Scales the font to some value.

* **Example**:
    .. code-block:: python

        display.setTextSize(4)

.setFont()
####################

* **Method prototype**:

.. code-block:: python

    setFont(f)

* **Arguments and return value**:
    | **f** - font dictionary

    Returns nothing.

* **Description**:
    | Used to change the text font.
    | Fonts can be found in the supplied Fonts folder or made using tools.

* **Example**:
    .. code-block:: python

        # Font has to be included
        display.setFont(font)
        display.println("Inkplate 6")

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4371.jpg
        :width: 600


.printText()
######################

* **Method prototype**:

.. code-block:: python

    print(x, y, s)

* **Arguments and return value**:
    | **x** - x coordinate to write text
    | **y** - y coordinate to write text
    | **s** - String to be printed.

    Returns nothing.

* **Description**:
    | Puts the text on screen. 

* **Example**:
    .. code-block:: python

        display.printText(100, 100, "Some text")

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4373.jpg
        :width: 600

.width()
##################

* **Method prototype**:

.. code-block:: python

    width()

* **Arguments and return value**:
    | No arguments.

    Returns nothing.

* **Description**:
    | Returns screen width.

* **Example**:
    .. code-block:: python

        display.width()


.height()
###################

* **Method prototype**:

.. code-block:: python

    height()

* **Arguments and return value**:
    | No arguments.

    Returns nothing.

* **Description**:
    | Returns screen height.

* **Example**:
    .. code-block:: python

        display.height()


.getRotation()
########################

* **Method prototype**:

.. code-block:: python

    getRotation()

* **Arguments and return value**:
    | No arguments.

    Returns nothing.

* **Description**:
    | Returns screen rotation, in range [0,3], 2 is default.

* **Example**:
    .. code-block:: python

        if(display.getRotation() == 4)
            print("I'm upside down!")
