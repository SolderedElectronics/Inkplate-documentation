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

    int sdCardInit();

* **Arguments and return value**:
    | No Arguments

    Returns 0 if card initializaion unsuccessful, else some number which casts to true.

* **Description**:
    | Used to initialize SD card interface.
    | Must be called before using SD card functionality like SdFile::read();



Inkplate::getSdFat();
#####################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    SdFat Inkplate::getSdFat()

* **Arguments and return value**:
    | No Arguments

    Returns SdFat object.

* **Description**:
    | See SdFat library documentation for use examples.


Inkplate::getSPI();
###################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    SPIClass getSPI();

* **Arguments and return value**:
    | No Arguments
    
    Returns SPIClass object.


Inkplate::getPanelState();
##########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    uint8_t getPanelState();

* **Arguments and return value**:
    | No Arguments.

    Returns 1 if eink panel is on, and 0 if it's off.

* **Description**:
    | Used to see if the panel is on.

* **Example**:
    .. code-block:: c

        Serial.print(display.getPanelState(), DEC);


Inkplate::readTouchpad();
#########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    uint8_t readTouchpad(uint8_t);

* **Arguments and return value**:
    | uint8_t **_pad** - pass in PAD1, PAD2 or PAD3

    Returns state of the desired pad.

* **Description**:
    | Reads the state of each of three pads.

* **Example**:
    .. code-block:: c

        if (display.readTouchpad(PAD1)) 
        {
            //Do something
        }



Inkplate::readTemperature();
############################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    int8_t readTemperature();

* **Arguments and return value**:
    | No arguments.

    Returns panel temperature at the last refresh.

* **Description**:
    | Can be used to determine temperature roughly.
    | Keep in mind that the returned value was measured at the time of the last screen refresh.

* **Example**:
    .. code-block:: c

        Serial.print(display.readTemperature(), DEC);



Inkplate::readBattery();
#########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    double readBattery();

* **Arguments and return value**:
    | No Arguments.

    Returns battery voltage as a double.

* **Description**:
    | Function used to determine battery voltage.
    | Can be used to display how much more time will the device be on.

* **Example**:
    .. code-block:: c

        double voltage = display.readBattery();



Inkplate::einkOff();
####################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void einkOff(void);

* **Arguments and return value**:
    | No Arguments.

    Returns nothing.

* **Description**:
    | Turns the panel off to save energy.

* **Example**:
    .. code-block:: c

        display.einkOff();



Inkplate::einkOff();
####################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void einkOn(void);

* **Arguments and return value**:
    | No Arguments.

    Returns nothing.

* **Description**:
    | Turns the panel back on.

* **Example**:
    .. code-block:: c

        display.einkOn();



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

        display.drawPixel(100, 50, BLACK);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::clearDisplay();
#########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void clearDisplay();

* **Example**:
    .. code-block:: c

        display.clearDisplay();

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::display();
####################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void display();

* **Arguments and return value**:
    | No Arguments

    Returns nothing.

* **Description**:
    | Puts all data in frame buffer to screen.

* **Example**:
    .. code-block:: c

        //Any drawing code
        display.drawPixel(10, 100, BLACK);

        display.display();

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::partialUpdate();
##########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void partialUpdate();

* **Arguments and return value**:
    | No Arguments

    Returns nothing.

* **Description**:
    | Updates only the changed parts of the screen.
    | After a few updates creates blurry parts of the screen.
    | Fixed by calling Inkplate::clear();

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, BLACK);

        display.partialUpdate();

        display.drawPixel(100, 100, BLACK);

* **Result**:
    | Here is what the code above produces like:

    .. image:: images/index.jpg
        :width: 600



Inkplate::drawBitmap3Bit();
###########################

* **Method prototype (as seen in Inkplate.h)**:

.. code-block:: c

    void drawBitmap3Bit(int16_t _x, int16_t _y, const unsigned char *_p, int16_t _w, int16_t _h);

* **Arguments and return value**:
    | int16_t **_x** - x coordinate of image corner, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int16_t **_y** - y coordinate of image corner, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | const unsigned char ***_p** - unsigned char buffer containing bitmap data
    | int16_t **_w** - image width
    | int16_t **_h** - image height

    Returns nothing.

* **Description**:
    | Draws a bitmap image to screen.
    | Image data can be created using online tools or supplied Python script in some examples.

* **Example**:
    .. code-block:: c

        //Picture is a predefined image buffer
        display.drawBitmap3Bit(0, 0, picture, 800, 600);
        display.display();  

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

