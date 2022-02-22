Inkplate MicroPython
====================

.__init__() method
##################

* **Method prototype (as seen in gfx.py)**:
    .. code-block:: python

        display.__init__(
            self,
            width,
            height,
            pixel,
            hline=None,
            vline=None,
            fill_rect=None,
            text=None,
            font=None,
        )

* **Arguments and return value**:
    | **self** - This object
    | **width** - The width of the drawing area in pixels.
    | **height** -  The height of the drawing area in pixels.
    | **pixel** - A function to call when a pixel is drawn on the display. This function
                  should take at least an x and y position and then any number of optional
                  color or other parameters.
    | **hline** - A function to quickly draw a horizontal line on the display.
                  This should take at least an x, y, and width parameter and
                  any number of optional color or other parameters.
    | **vline** - A function to quickly draw a vertical line on the display.
                  This should take at least an x, y, and height paraemter and
                  any number of optional color or other parameters.
    | **fill_rect** - A funtion to quickly draw a solid rectangle with four
                  input parameters: x,y, width, and height. Any number of other
                  parameters for color or screen specific data.
    | **text** - A function to quickly place text on the screen. The inputs include:
                  x, y data(top left as starting point).
    | **font** - An optional input to augment the default text method with a new font.
                  The input shoudl be a properly formatted dict.

    Returns nothing.

* **Description**:
    Method used to initialize display.



.pixel() method
###############

* **Method prototype (as seen in gfx.py)**:
    .. code-block:: python

        display.pixel(x0, y0, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of pixel.
    | **y0** - y coordinate of pixel.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    A function to pass through in input pixel functionality.



._slow_hline() method
#####################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display._slow_hline(x0, y0, width, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of line.
    | **y0** - y coordinate of line.
    | **width** - length of line.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    Slow implementation of a horizontal line using pixel drawing.
        This is used as the default horizontal line if no faster override
        is provided.



._slow_vline() method
#####################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display._slow_vline(x0, y0, height, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of Line.
    | **y0** - y coordinate of line.
    | **height** - height of line.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    Slow implementation of a vertical line using pixel drawing.
        This is used as the default vertical line if no faster override
        is provided.




.rect() method
###############

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display._rect(x0, y0, width, height, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of rectangle.
    | **y0** - y coordinate of rectangle.
    | **height** - height of rectangle.
    | **width** - width of rectangle.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    Rectangle drawing function.  Will draw a single pixel wide rectangle
        starting in the upper left x0, y0 position and width, height pixels in
        size.



._fill_rect() method
####################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display._fill_rect(x0, y0, width, height, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of rectangle.
    | **y0** - y coordinate of rectangle.
    | **height** - height of rectangle.
    | **width** - width of rectangle.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    Filled rectangle drawing function.  Will draw a single pixel wide
        rectangle starting in the upper left x0, y0 position and width, height
        pixels in size.



.line() method
###############

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display.line(x0, y0, x1, y1, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of start .
    | **y0** - y coordinate of start.
    | **x1** - x coordinate of end.
    | **y1** - y coordinate of end.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    Line drawing function.  Will draw a single pixel wide line starting at
        x0, y0 and ending at x1, y1.



.line() method
###############

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display.line(x0, y0, x1, y1, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of start .
    | **y0** - y coordinate of start.
    | **x1** - x coordinate of end.
    | **y1** - y coordinate of end.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    Line drawing function.  Will draw a single pixel wide line starting at
        x0, y0 and ending at x1, y1.



.circle() method
################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display.circle(x0, y0, radius, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of center.
    | **y0** - y coordinate of center.
    | **circle** - Radius of circle.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    Circle drawing function.  Will draw a single pixel wide circle with
        center at x0, y0 and the specified radius.


.triangle() method
##################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display.triangle(x0, y0, x1, y1, x2, y2, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of first point.
    | **y0** - y coordinate of first point.
    | **x1** - x coordinate of second point.
    | **y1** - y coordinate of second point.
    | **x2** - x coordinate of third point.
    | **y2** - y coordinate of third point.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    Triangle drawing function.  Will draw a single pixel wide triangle
        around the points (x0, y0), (x1, y1), and (x2, y2).



.fill_triangle() method
#######################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display.fill_triangle(x0, y0, x1, y1, x2, y2, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of first point.
    | **y0** - y coordinate of first point.
    | **x1** - x coordinate of second point.
    | **y1** - y coordinate of second point.
    | **x2** - x coordinate of third point.
    | **y2** - y coordinate of third point.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

   Filled triangle drawing function.  Will draw a filled triangle around
        the points (x0, y0), (x1, y1), and (x2, y2).



.round_rect() method
####################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display.round_rect(x0, y0, width, height, radius, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of first point.
    | **y0** - y coordinate of first point.
    | **width** - width of rectangle.
    | **height** - height of rectangle.
    | **radius** - radius of rounded corners.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

   Rectangle with rounded corners drawing function.
        This works like a regular rect though! if radius = 0
        Will draw the outline of a rextabgle with rounded corners with (x0,y0) at the top left



._place_char() method
#####################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display._place_char(x0, y0, char, size, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of first point.
    | **y0** - y coordinate of first point.
    | **char** - Char to put.
    | **size** - Size of char.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

   A sub class used for placing a single character on the screen



._very_slow_text method
#######################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display._place_char(x0, y0, string, size, *args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of first point.
    | **y0** - y coordinate of first point.
    | **string** - string to write on display.
    | **size** - Size of string.
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

   A function to place text on the display.(temporary)
        to use special characters put "__" on either side of the desired characters.
        letter format:
        {'character_here' : bytearray(b',WIDTH,HEIGHT,right-most-data, more-bytes-here,left-most-data') ,}
        (replace the "," with backslashes!!)
        each byte:
                        | lower most bit(lowest on display)
                        V
                 x0110100
                  ^c
                  | top most bit (highest on display)



.set_text_background method
###########################

* **Method prototype (as seen in gfx.py)**:

    .. code-block:: python

        display._place_char(*args, **kwargs)

* **Arguments and return value**:
    | **self** - This object
    | ***args** - Additional arguments.
    | ****kwargs** - Keywords.

    Returns nothing.

* **Description**:

    A method to change the background color of text, input any and all color paramsself.
        run without any inputs to return to "clear" background.


.begin() method
###############
    | Before calling any display method you **must** call .begin() like this: 

    .. code-block:: python

        display.begin()

* **Description**:

    If you forget to do this most method calls will result in core panick and esp32 resetting.
    After you've called this you can proceed calling all other methods described below.



.init()
######################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .init(x, y, color)

* **Arguments and return value**:
    | No arguments.

    Returns nothing.

* **Description**:
    |   Method to initialize all perihperals.





.drawPixel()
######################

* **Method prototype (as seen in Inkplate.py)**:

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

* **Method prototype (as seen in Inkplate.py)**:

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

* **Method prototype (as seen in Inkplate.py)**:

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

* **Method prototype (as seen in Inkplate.py)**:

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



.read_battery()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .read_battery(cls)

* **Arguments and return value**:
    | **cls** - Instance

    |Returns battery voltage.

* **Description**:
    | Read the battery voltage. Note that the
    | result depends on the ADC calibration, and be a bit off.



.readBattery()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .readBattery(self)

* **Arguments and return value**:
    | **self** - Instance

    |Returns battery voltage.

* **Description**:
    | Read the battery voltage. Note that the
    | result depends on the ADC calibration, and be a bit off.



.read_temperature()
###################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .read_temperature(cls)

* **Arguments and return value**:
    | **cls** - Instance

    |Returns panel temperature.

* **Description**:
    | Read panel temperature. It varies +- 2 degree



.readTemperature()
##################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .readTemperature(self)

* **Arguments and return value**:
    | **self** - Instance

    |Returns panel temperature.

* **Description**:
    | Read panel temperature. It varies +- 2 degree


.power_on()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .power_on(cls)

* **Arguments and return value**:
    | **cls** - Instance

    |Returns nothing.

* **Description**:
    | power_on turns the voltage regulator on and wakes up the display (GMODE and OE)



.power_off()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .power_off(cls)

* **Arguments and return value**:
    | **cls** - Instance

    |Returns nothing.

* **Description**:
    |  power_off puts the display to sleep and cuts the power



.vscan_start()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .vscan_start(cls)

* **Arguments and return value**:
    | **cls** - Instance

    |Returns nothing.

* **Description**:
    |  vscan_start begins a vertical scan by toggling CKV and SPV
    | sleep_us calls are commented out 'cause MP is slow enough...



.vscan_write()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .vscan_start()

* **Arguments and return value**:
    | No arguments.

    |Returns nothing.

* **Description**:
    |  vscan_write latches the row into the display pixels and moves to the next row



.gen_byte2gpio()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .gen_byte2gpio(cls)

* **Arguments and return value**:
    | **cls** - Instance

    |Returns nothing.

* **Description**:
    |  gen_byte2gpio converts a byte of data for the screen to 32 bits of gpio0..31



.fill_screen()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .fill_screen(data)

* **Arguments and return value**:
    | **data** - Value to write to display

    |Returns nothing.

* **Description**:
    |  fill_screen writes the same value to all bytes of the screen, it is used for cleaning



._gen_luts()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    ._gen_luts(cls)

* **Arguments and return value**:
    | **cls** - Instance

    |Returns nothing.

* **Description**:
    |  gen_luts generates the look-up tables to convert a nibble (4 bits) of pixels to the
    | 32-bits that need to be pushed into the gpio port.
    | The LUTs used here were copied from the e-Radionica Inkplate-6-Arduino-library.



._send_row()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    ._send_row(lut_in, framebuf, row: int)

* **Arguments and return value**:
    | **lut_in** - Lookup table
    | **framebuf** - Buffer
    | **row** - Row number

    |Returns nothing.

* **Description**:
    | _send_row writes a row of data to the display



._send_row()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    ._send_row(lut_in, old_framebuf, new_framebuf, row: int)

* **Arguments and return value**:
    | **lut_in** - Lookup table
    | **old_framebuf** - Old content of display
    | **new_framebuf** - New content of display
    | **row** - Row number

    |Returns nothing.

* **Description**:
    | _send_row writes a row of data to the display



._gen_wave()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    ._gen_wave(cls)

* **Arguments and return value**:
    | **cls** - Instance

    |Returns nothing.

* **Description**:
    | _gen_wave generates the waveform table. The table consists of N phases or steps during
    | each of which the entire display gets written. The array in each phase gets indexed with
    | a nibble of data and contains the 32-bits that need to be pushed into the gpio port.
    | The waveform used here was adapted from the e-Radionica Inkplate-6-Arduino-library
    | by taking colors 0 (black), 3, 5, and 7 (white) from "waveform3Bit[8][7]".



.start()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .start(cls)

* **Arguments and return value**:
    | **self** - Instance

    |Returns nothing.

* **Description**:
    | start makes a reference copy of the current framebuffer



._gen_lut_mono()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    ._gen_lut_mono(cls)

* **Arguments and return value**:
    | **cls** - Instance

    |Returns nothing.

* **Description**:
    |  gen_lut_mono generates a look-up tables to change the display from a nibble of old
    | pixels (4 bits = 4 pixels) to a nibble of new pixels. The LUT contains the
    | 32-bits that need to be pushed into the gpio port to effect the change.



._skip_rows()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    ._skip_rows(rows)

* **Arguments and return value**:
    | **rows** - Number of rows to skip

    |Returns nothing.

* **Description**:
    |  _skip_rows skips N rows



.einkOn()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .einkOn(self)

* **Arguments and return value**:
    | **self** - Instance

    |Returns nothing.

* **Description**:
    |  einkOn turns on epapers supply on and enables IO pins




.einkOff()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .einkOff(self)

* **Arguments and return value**:
    | **self** - Instance

    |Returns nothing.

* **Description**:
    |  einkOff turns off epapers supply on and puts  IO pins in Z state




.setRotation()
##############

* **Method prototype (as seen in Inkplate.py)**:

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



._rotateCoordinates()
#####################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .setRotation(self,x,y)

* **Arguments and return value**:
    | **self** - Instance.
    | **x** - x coordinate to rotate.
    | **y** - y coordinate to rotate.

    Returns nothing.

* **Description**:
    | Rotates one pixel for new orientation.


.writePixel()
##############

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .writePixel(x, y, c)

* **Arguments and return value**:
    | **self** - Instance.
    | **x** - x coordinate to rotate.
    | **y** - y coordinate to rotate.
    | **c** - color (3 bit mode).

    Returns nothing.

* **Description**:
    | Writes one pixel to display.



.writeFillRect()
################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .writeFillRect(x, y, w, h, c)

* **Arguments and return value**:
    | **self** - Instance.
    | **x** - x coordinate of rectangle.
    | **y** - y coordinate of rectangle.
    | **w** - width.
    | **h** - height.
    | **c** - color (3 bit mode).

    Returns nothing.

* **Description**:
    | Writes rectangle to display.




.writeFastVLine()
#################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .writeFastVLine(x, y, h, c)

* **Arguments and return value**:
    | **self** - Instance.
    | **x** - x coordinate of start.
    | **y** - y coordinate of start.
    | **h** - length of line.
    | **c** - color (3 bit mode).

    Returns nothing.

* **Description**:
    | Method to fast write vertical line on display.



    
.writeFastHLine()
#################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .writeFastHLine(x, y, w, c)

* **Arguments and return value**:
    | **self** - Instance.
    | **x** - x coordinate of start.
    | **y** - y coordinate of start.
    | **w** - length of line.
    | **c** - color (3 bit mode).

    Returns nothing.

* **Description**:
    | Method to fast write horizontal line on display.



.writeLine()
##############

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .writeLine(x, y, x1, y1, c)

* **Arguments and return value**:
    | **self** - Instance.
    | **x0** - x coordinate of start.
    | **y0** - y coordinate of start.
    | **x1** - x coordinate of end.
    | **y1** - y coordinate of end.
    | **c** - color (3 bit mode).

    Returns nothing.

* **Description**:
    | Method to write line on display.


.writeLine()
##############

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .writeLine(x, y, x1, y1, c)

* **Arguments and return value**:
    | **self** - Instance.
    | **x0** - x coordinate of start.
    | **y0** - y coordinate of start.
    | **x1** - x coordinate of end.
    | **y1** - y coordinate of end.
    | **c** - color (3 bit mode).

    Returns nothing.

* **Description**:
    | Method to write line on display.



.setDisplayMode()
####################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .setDisplayMode(mode)

* **Arguments and return value**:
    | **self** - Instance
    | **mode** - New display mode, display.Inkplate.INKPLATE_1BIT or display.Inkplate.INKPLATE_2BIT.

    Returns nothing.



.selectDisplayMode()
####################

* **Method prototype (as seen in Inkplate.py)**:

.. code-block:: python

    .selectDisplayMode(_mode)

* **Arguments and return value**:
    | **_mode** - New display mode, display.Inkplate.INKPLATE_1BIT or display.Inkplate.INKPLATE_2BIT.

    Returns nothing.

* **Description**:
    | Changes the screen mode to from monochrome to 3 bit grayscale or vice versa.

* **Example**:
    .. code-block:: python

        display.selectDisplayMode(Inkplate.INKPLATE_2BIT)


.getDisplayMode()
#################

* **Method prototype**:

.. code-block:: python

    .getDisplayMode()

* **Arguments and return value**:
    | No arguments.

    Returns currently set display mode.

* **Description**:
    | Used to determine which display mode is currently used.
    | Returns Inkplate.INKPLATE_1BIT or Inkplate.INKPLATE_2BIT.

* **Example**:
    .. code-block:: python

        if display.getDisplayMode() == Inkplate.INKPLATE_2BIT:
            print("I'm in grayscale mode!")


.clean()
########

* **Method prototype:

.. code-block:: python

    clean(c, rep)

* **Arguments and return value**:
    | uint8_t **c** - one of four posible pixel states (0 will light screen, 1 will darken screen, 2 will discharge screen and 3 will skip).
    | uint8_t **rep** - number of repetitions.

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
    | **self** - font dictionary
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
    | **self** - font dictionary
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
    | Doesn't work on Inkplate 6COLOR

    .. image:: images/IMG_4366.jpg
        :width: 600


.setTextSize()
##############

* **Method prototype**:

.. code-block:: python

    setTextSize(s)

* **Arguments and return value**:
    | **self** - Instance
    | **s** - font scale

    Returns nothing.

* **Description**:
    | Scales the font to some value.

* **Example**:
    .. code-block:: python

        display.setTextSize(4)

.setFont()
##########

* **Method prototype**:

.. code-block:: python

    setFont(self , f)

* **Arguments and return value**:
    | **self** - font dictionary
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
############

* **Method prototype**:

.. code-block:: python

    print(x, y, s)

* **Arguments and return value**:
    | **self** - font dictionary
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
########

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
#########

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
##############

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

        if display.getRotation() == 4:
            print("I'm upside down!")



.circle()
#########

* **Method prototype (as seen in shapes.py)**:

.. code-block:: python

    circle(x0, y0, r, color)

* **Arguments and return value**:
    | **self** - Instance
    | **x0** - x coordinate of center
    | **y0** - y coordinate of center
    | **r** - radius
    | **color** - color in 3 bit mode

    Returns nothing.

* **Description**:
    | Single pixel circle




.fill_circle()
##############

* **Method prototype (as seen in shapes.py)**:

.. code-block:: python

    fill_circle(x0, y0, r, color)

* **Arguments and return value**:
    | **self** - Instance
    | **x0** - x coordinate of center
    | **y0** - y coordinate of center
    | **r** - radius
    | **color** - color in 3 bit mode

    Returns nothing.

* **Description**:
    | Draw filled circle



.triangle()
###########

* **Method prototype (as seen in shapes.py)**:

.. code-block:: python

    triangle(x0, y0, x1, y1, x2, y2, color)

* **Arguments and return value**:
    | **self** - Instance
    | **x0** - x coordinate of first point
    | **y0** - y coordinate of first point
    | **x1** - x coordinate of second point
    | **y1** - y coordinate of second point
    | **x2** - x coordinate of third point
    | **y2** - y coordinate of third point
    | **color** - color in 3bit mode

    Returns nothing.

* **Description**:
    | Triangle drawing function.  Will draw a single pixel wide triangle
        around the points (x0, y0), (x1, y1), and (x2, y2).


.round_rect() method
####################

* **Example**:

    .. code-block:: python

        display.round_rect(x0, y0, width, height, radius, color)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of first point.
    | **y0** - y coordinate of first point.
    | **width** - width of rectangle.
    | **height** - height of rectangle.
    | **radius** - radius of rounded corners.
    | **color** - color in 3 bit mode.

    Returns nothing.

* **Description**:

   |Rectangle with rounded corners drawing function.
    |    This works like a regular rect though! if radius = 0
     |   Will draw the outline of a rextabgle with rounded corners with (x0,y0) at the top left



.fill_round_rect() method
#########################

* **Example**:

    .. code-block:: python

        display.fill_round_rect(x0, y0, width, height, radius, color)

* **Arguments and return value**:
    | **self** - This object
    | **x0** - x coordinate of first point.
    | **y0** - y coordinate of first point.
    | **width** - width of rectangle.
    | **height** - height of rectangle.
    | **radius** - radius of rounded corners.
    | **color** - color in 3 bit mode.

    Returns nothing.

* **Description**:

   |Filled rectangle with rounded corners drawing function.
    |    This works like a regular rect though! if radius = 0
     |   Will draw the outline of a rextabgle with rounded corners with (x0,y0) at the top left    



.init_spi() method
##################

* **Example**:

    .. code-block:: python

        display.init_spi(baudrate)

* **Arguments and return value**:
    | **self** - This object
    | **baudrate** - Communication speed

    Returns nothing.

* **Description**:

   | Initializes SPI communication.



.init_card() method
###################

* **Example**:

    .. code-block:: python

        display.init_card()

* **Arguments and return value**:
    | **self** - This object

    Returns nothing.

* **Description**:

   | Initializes SD card.


.setFrontlight() method
#######################

* **Example**:

    .. code-block:: python

        display.setFrontlight(value)

* **Arguments and return value**:
    | **cls** - This object.
    | **value** - frontlight intensity.

    Returns nothing.

* **Description**:

   | Turns on or off frontlight
   | Used on Inkplate 6PLUS



.touchInArea() method
#####################

* **Example**:

    .. code-block:: python

        display.touchInArea(x, y, width, height)

* **Arguments and return value**:
    | **cls** - This object.
    | **x** - x coordinate of start of rectangle.
    | **y** - y coordinate of start of rectangle.
    | **width** - width of rectangle.
    | **height** - height of rectangle.

    Returns nothing.

* **Description**:

   | Checks if part of touchscreen is touched



.tsInit() method
################

* **Example**:

    .. code-block:: python

        display.tsInit(pwrState)

* **Arguments and return value**:
    | **cls** - This object.
    | **pwrState** - x coordinate of start of rectangle.

    Returns nothing.

* **Description**:

   | Enables or disables touchscreen


.tsShutdown() method
####################

* **Example**:

    .. code-block:: python

        display.tsShutdown()

* **Arguments and return value**:
    | **cls** - This object.

    Returns nothing.

* **Description**:

   | Disables touchscreen



.tsHardwareReset() method
#########################

* **Example**:

    .. code-block:: python

        display.tsHardwareReset()

* **Arguments and return value**:
    | **cls** - This object.

    Returns nothing.

* **Description**:

   | Resets hardware of touchscreen


.tsSoftwareReset() method
#########################

* **Example**:

    .. code-block:: python

        display.tsSoftwareReset()

* **Arguments and return value**:
    | **cls** - This object.

    Returns nothing.

* **Description**:

   | Resets settings of touchscreen



.tsGetRawData() method
######################

* **Example**:

    .. code-block:: python

        display.tsGetRawData()

* **Arguments and return value**:
    | **cls** - This object.

    Returns data from touchscreen registers.

* **Description**:

   | Returns raw data from touchscreen registers which needs to be converted to
   | touch coordinates.


.tsGetXY() method
#################

* **Example**:

    .. code-block:: python

        display.tsGetXY(data,i)

* **Arguments and return value**:
    | **cls** - This object.
    | **data** - Data array to convert.
    | **i** - Index of data.

    Returns nothing.

* **Description**:

   | Converts raw data to X and Y coordinates of touched area



.tsGetData() method
###################

* **Example**:

    .. code-block:: python

        display.tsGetData()

* **Arguments and return value**:
    | **cls** - This object.

    Returns how many fingers are touching touchscreen.

* **Description**:

   | Returns how many fingers are touching touchscreen.



.tsGetResolution() method
#########################

* **Example**:

    .. code-block:: python

        display.tsGetResolution()

* **Arguments and return value**:
    | **cls** - This object.

    Returns nothing.

* **Description**:

   | Calculates X and Y resolution of touchscreen and saves them into internal variables.



.tsSetPowerState() method
#########################

* **Example**:

    .. code-block:: python

        display.tsSetPowerState(state)

* **Arguments and return value**:
    | **cls** - This object.
    | **state** - State to set to touchscreen.

    Returns nothing.

* **Description**:

   | Sets power state of touchscreen.



.tsGetPowerState() method
#########################

* **Example**:

    .. code-block:: python

        display.tsGetPowerState()

* **Arguments and return value**:
    | **cls** - This object.

    Returns touchscreen power state.

* **Description**:

   | Gets power state of touchscreen.



.tsAvailable() method
#####################

* **Example**:

    .. code-block:: python

        display.tsAvailable()

* **Arguments and return value**:
    | **cls** - This object.

    Returns 1 if touchscreen is initialized and operating.

* **Description**:

   | Checks if touchscreen is operating.



.setMCPForLowPower() method
###############################
* **Example**:

    .. code-block:: python

        display.setMCPForLowPower(self)

* **Arguments and return value**:
    | **self** - This object.

* **Description**:

   | Sets MCP pinmodes for low power.



.getPanelDeepSleepState() method
################################
* **Example**:

    .. code-block:: python

        display.getPanelDeepSleepState(self)

* **Arguments and return value**:
    | **self** - This object.

    Returns True if panel is in deepsleep mode

* **Description**:

   | Used to check if panel is in deep sleep.




.setPanelDeepSleepState() method
################################
* **Example**:

    .. code-block:: python

        display.setPanelDeepSleepState(state):

* **Arguments and return value**:
    | **self** - This object.
    | **state** - What to set deep sleep.

    Returns nothing.

* **Description**:

   | Used to set panel deep sleep, or turn it off.


.resetPanel() method
################################
* **Example**:

    .. code-block:: python

        display.resetPanel(self):

* **Arguments and return value**:
    | **self** - This object.

    Returns nothing.

* **Description**:

   | Used to reset Inkplates panel

