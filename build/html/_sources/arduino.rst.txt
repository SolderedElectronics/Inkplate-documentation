Inkplate Arduino
==================

System Functions
----------------

Inkplate object initialization
##############################
    | To use any of Inkplates functionalities in Arduino IDE you need to include Inkplate header, as mentioned on the Index and Get Started pages.
    | After you've done that you can create a new instance of the Inkplate object, like this:

    .. code-block:: c

        Inkplate display(INKPLATE_1BIT);

    or

    .. code-block:: c

        Inkplate display(INKPLATE_3BIT);

    depending on what you need, monochrome (INKPLATE_1BIT) of grayscale(INKPLATE_3BIT) functionality.

    In here given examples, Inkplate object will always be named display, if not said otherwise.
    After calling this below your imports you have access to all Inkplate functionality as display object methods.

begin() method
##############
    | Before calling any display method you **must** call .begin() like this: 

    .. code-block:: c

        display.begin();

* **Description**:

    If you forget to do this most method calls will result in core panick and esp32 resetting.
    For most use cases this function is called in Arduino's setup function.
    After you've done this you can proceed calling all other methods described below.





Inkplate::sdCardInit();
#######################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600




Inkplate::getSdFat();
#####################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::getSPI();
###################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600





Inkplate::getPanelState();
##########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600





Inkplate::readTouchpad();
#########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600





Inkplate::readTemperature();
############################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600





Inkplate::readBattery();
#########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::einkOff();
####################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::einkOn();
###################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600




Drawing Functions
-----------------

Inkplate::drawPixel();
######################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::clearDisplay();
#########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::display();
####################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::partialUpdate();
##########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::drawBitmap3Bit();
###########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::setRotation();
########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::selectDisplayMode();
##############################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::getDisplayMode();
###########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600


Inkplate::drawBitmapFromSD();
#############################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600


Inkplate::drawBitmapFromWeb();
##############################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600


Inkplate::drawThickLine();
##########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::drawGradientLine();
#############################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600




Inkplate::clean();
#########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawPixel(int16_t x0, int16_t y0, uint16_t color);

* **Arguments and return value**:
    | int16_t **x0** - x coordinate of pixel, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **y0** - y coordinate of pixel, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | uint16_t **color** - pixel color, in 3 bit mode in range [0, 7]

    Returns nothing.

* **Description**:
    | Most basic drawing command in the library is .drawPixel();
    | Draws one pixel at x0, y0 in desired color.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, 0);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600

