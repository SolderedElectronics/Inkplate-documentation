.. raw:: html

    <script>
        window.location.href = "https://soldered.com/documentation/inkplate";
    </script>
    <p>If you are not redirected, <a href="https://soldered.com/documentation/inkplate">click here</a>.</p>

Inkplate esp-idf
==================

System Functions
----------------

Inkplate object initialization
##############################
    To use any of Inkplates functionalities you need to include Inkplate header, as mentioned on the Index and Get Started pages.
    After you've done that you can create a new instance of the Inkplate object, like this:

    .. code-block:: c

        Inkplate display(DisplayMode::INKPLATE_1BIT);

    or

    .. code-block:: c

        Inkplate display(DisplayMode::INKPLATE_3BIT);


    depending on what you need, monochrome (INKPLATE_1BIT) of grayscale (INKPLATE_3BIT) functionality.

    In here given examples, Inkplate object will always be named display, if not said otherwise.
    After calling this below your "#include" lines, you have access to all Inkplate functionality as display object methods.

begin() method
##############
    | Before calling any display method you **must** call .begin() like this: 

    .. code-block:: c

        display.begin();

* **Description**:

    If you forget to do this most method calls will result in core panick and esp32 resetting.
    For most use cases this function is called in Arduino's setup function.
    After you've done this you can proceed calling all other methods described below.


Inkplate::einkOff();
####################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c

    inline void einkOff();

* **Arguments and return value**:
    | No Arguments.
    | Returns nothing.

* **Description**:
    | Turns the panel off to save energy.

* **Example**:
    .. code-block:: c

        display.einkOff();


Inkplate::einkOn();
####################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c

    void einkOn();

* **Arguments and return value**:
    | No Arguments.
    | Returns nothing.

* **Description**:
    | Turns the panel back on.

* **Example**:
    .. code-block:: c

        display.einkOn();

Inkplate::getPanelState();
##########################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c

    uint8_t getPanelState();

* **Arguments and return value**:
    | No Arguments.
    | Returns 1 if eink panel is on, and 0 if it's off.

* **Description**:
    | Used to see if the panel is on.

* **Example**:
    .. code-block:: c

        Serial.print(display.getPanelState(), DEC);

Inkplate::readBattery();
#########################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c

    double readBattery();

* **Arguments and return value**:
    | No Arguments.
    | Returns battery voltage as a double.

* **Description**:
    | Function used to determine battery voltage.
    | Can be used to display how much more time will the device be on.

* **Example**:
    .. code-block:: c

        double voltage = display.readBattery();

Inkplate::readTemperature();
############################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c

    int8_t readTemperature();

* **Arguments and return value**:
    | No arguments.
    | Returns panel temperature at the last refresh.

* **Description**:
    | Can be used to determine temperature roughly.
    | Keep in mind that the returned value was measured at the time of the last screen refresh.

* **Example**:
    .. code-block:: c

        int  temp = display.readTemperature();

Inkplate::readTouchpad();
#########################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c

    uint8_t readTouchpad(int c);

* **Arguments and return value**:
    | int **c** - pass in PAD1, PAD2 or PAD3

    | Returns state of the desired pad.

* **Description**:
    | Reads the state of each of three pads.

* **Example**:
    .. code-block:: c

        if (display.readTouchpad(PAD1)) 
        {
            //Do something
        }

Inkplate::sdCardInit();
#######################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c

    bool sdCardInit();

* **Arguments and return value**:
    | No Arguments
    | Returns 0 if card initialization unsuccessful, else some number which casts to true.

* **Description**:
    | Used to initialize SD card interface.
    | Must be called before using SD card functionality like SdFile::read();


Graphics Functions
------------------

Inkplate::setRotation();
########################

* **Method prototype (as seen in graphics.hpp)**:

.. code-block:: c

    void setRotation(uint8_t r);

* **Arguments and return value**:
    | uint8_t **r** - screen rotation.
    | Returns nothing.

* **Description**:
    | Rotates the screen to be used in different orientations.
    | Default is 2, to flip 180 input 4
    | 1 and 3 are for portait mode.
    | Once flipped coordinate space remains to have the origin in the top left corner.

* **Example**:
    .. code-block:: c
        
        display.setRotation(3);

        display.setCursor(100, 100);
        display.print("INKPLATE");

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4347.jpg
        :width: 600


Inkplate::getRotation();
########################

* **Method prototype (as seen in graphics.hpp)**:

.. code-block:: c

    uint8_t getRotation(void);

* **Arguments and return value**:
    | No arguments.
    | Returns nothing.

* **Description**:
    | Returns screen rotation, in range [0,3], 2 is default.

* **Example**:
    .. code-block:: c

        if(display.getRotation() == 4)
            display.print("I'm upside down!");
            display.display();

Inkplate::drawPixel();
######################

* **Method prototype (as seen in graphics.hpp)**:

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
    | Requires Inkplate::display() to be called afterwards to update the screen,
    | See below.

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, BLACK);

* **Result**:
    | Here is what the code above produces:
    | Quite small, isn't it.

    .. image:: images/IMG_4345.jpg
        :width: 600


Inkplate::selectDisplayMode();
##############################

* **Method prototype (as seen in graphics.hpp)**:

.. code-block:: c

    void selectDisplayMode(DisplayMode mode)

* **Arguments and return value**:
    | DisplayMode mode **mode** - New display mode, INKPLATE_1BIT or INKPLATE_3BIT.
    | Returns nothing.

* **Description**:
    | Changes the screen mode to from monochrome to 3 bit grayscale or vice versa.

* **Example**:
    .. code-block:: c

        display.selectDisplayMode(DisplayMode::INKPLATE_3BIT);

Inkplate::getDisplayMode();
###########################

* **Method prototype (as seen in graphics.hpp)**:

.. code-block:: c

    DisplayMode getDisplayMode();

* **Arguments and return value**:
    | No arguments.
    | Returns currently set display mode.

* **Description**:
    | Used to determine which display mode is currently used.
    | Returns DisplayMode::INKPLATE_1BIT or DisplayMode::INKPLATE_3BIT.

* **Example**:
    .. code-block:: c

        if(display.getDisplayMode() == DisplayMode::INKPLATE_3BIT)
        {
            display.print("I'm in grayscale mode!");
            display.display()
        }

Inkplate::clearDisplay();
#########################

* **Method prototype (as seen in graphics.hpp)**:

.. code-block:: c

    void clearDisplay();

* **Arguments and return value**:
    | No Arguments
    | Returns nothing.

* **Description**:
    | Clears all data in buffer. Call display() after this to update/clear display.

* **Example**:
    .. code-block:: c

        display.clearDisplay();
        display.display();

Inkplate::display();
####################

* **Method prototype (as seen in graphics.hpp)**:

.. code-block:: c

    void display();

* **Arguments and return value**:
    | No Arguments
    | Returns nothing.

* **Description**:
    | Displays all data in frame buffer to screen.

* **Example**:
    .. code-block:: c

        //Any drawing code
        display.drawPixel(10, 100, BLACK);

        display.display();

Inkplate::partialUpdate();
##########################

* **Method prototype (as seen in graphics.hpp)**:

.. code-block:: c

    void partialUpdate();

* **Arguments and return value**:
    | No Arguments
    | Returns nothing.

* **Description**:
    | Updates only the changed parts of the screen. (monochrome/INKPLATE_1BIT mode only!)
    | After a few updates creates blurry parts of the screen.
    | Fixed by calling Inkplate::clean();

* **Example**:
    .. code-block:: c

        display.drawPixel(100, 50, BLACK);

        display.partialUpdate();

        display.drawPixel(100, 100, BLACK);

Inkplate::width();
##################

* **Method prototype (as seen in graphics.hpp)**:

.. code-block:: c

    int16_t width();

* **Arguments and return value**:
    | No arguments.

* **Description**:
    | Returns screen width.

* **Example**:
    .. code-block:: c

        display.width();

Inkplate::height();
###################

* **Method prototype (as seen in graphics.hpp)**:

.. code-block:: c

    int16_t height(void);

* **Arguments and return value**:
    | No arguments.

    Returns nothing.

* **Description**:
    | Returns screen height.

* **Example**:
    .. code-block:: c

        display.height();

Inkplate::drawImage();
#############################

* **Method prototype (as seen in Image.h)**:

.. code-block:: c

    bool drawImage(const char *path, int x, int y, bool dither = 1, bool invert = 0);
    bool drawImage(const String path, int x, int y, bool dither = 1, bool invert = 0);
    bool drawImage(const uint8_t *buf, int x, int y, int16_t w, int16_t h, uint8_t c = BLACK, uint8_t bg = 0xFF);
    bool drawImage(const char *path, const Format &format, const int x, const int y, const bool dither = 1, const bool invert = 0);
    bool drawImage(const String path, const Format &format, const int x, const int y, const bool dither = 1, const bool invert = 0);
    bool drawImage(const char *path, const Format &format, const Position &position, const bool dither = 1, const bool invert = 0);


* **Arguments and return value**:
    | const char ***path** - Path to file.
    | int **x** - x coordinate to draw the image at
    | int **y** - y coordinate to draw the image at
    | bool **dither** - to dither the image or not 
    | bool **invert** - invert all colors, defaults to false
    |
    | const String **path** - Path to file.
    | int **x** - x coordinate to draw the image at
    | int **y** - y coordinate to draw the image at
    | bool **dither** - to dither the image or not 
    | bool **invert** - invert all colors, defaults to false
    |
    | const uint8_t ***p** - Buffer to draw from.
    | int **x** - x coordinate to draw the image at
    | int **y** - y coordinate to draw the image at
    | int16_t **w** - x coordinate to draw the image at
    | int16_t **h** - y coordinate to draw the image at
    | bool **dither** - to dither the image or not 
    | bool **invert** - invert all colors, defaults to false
    | uint8_t **c** - color to draw 1 pixels if in BW mode
    | uint8_t **bg** - color to draw all 0 pixels if in BW mode.

    | const char ***path** - Path to file.
    | const Format **&format** - image format (bmp, jpeg, png).
    | int **x** - x coordinate to draw the image at
    | int **y** - y coordinate to draw the image at
    | bool **dither** - to dither the image or not 
    | bool **invert** - invert all colors, defaults to false

    | const String ***path** - Path to file.
    | const Format **&format** - image format (bmp, jpeg, png).
    | int **x** - x coordinate to draw the image at
    | int **y** - y coordinate to draw the image at
    | bool **dither** - to dither the image or not 
    | bool **invert** - invert all colors, defaults to false

    | const char ***path** - Path to file.
    | const Format **&format** - image format (bmp, jpeg, png).
    | const Position **&position** - image position (Center, TopLeft, BottomLeft, TopRight, BottomRight, _npos)
    | bool **dither** - to dither the image or not 
    | bool **invert** - invert all colors, defaults to false

    Returns 0 if error occured, else returns 1.

* **Description**:
    | Should always have Inkplate::sdCardInit() called before if file is from SD.
    | Can draw all kinds of images, but they should have a file extensions in them.
    | Can draw from web if path starts with http:// or https:// or if not from SD.
    | Draws bmp, png and jpeg images.
    | Automatically adjusts for current display mode.


Shapes Functions
----------------

Inkplate::drawElipse();
#######################

* **Method prototype (as seen in shapes.hpp)**:

.. code-block:: c

    void drawElipse(int rx, int ry, int xc, int yc, int c);

* **Arguments and return value**:
    | int **rx** - Elipse X radius.
    | int **ry** - Elipse Y radius.
    | int **xc** - Elipse center x.
    | int **yc** - Elipse center y.
    | int **color** - Elipse color (just the edge, see fillElipse for fully filled).

    Returns nothing.

* **Description**:
    | Draws an empty(not filled) elipse.

* **Example**:
    .. code-block:: c

       display.drawElipse(100, 200, 400, 300, 0);

Inkplate::fillElipse();
#######################

* **Method prototype (as seen in shapes.hpp)**:

.. code-block:: c

    void fillElipse(int rx, int ry, int xc, int yc, int c);

* **Arguments and return value**:
    | int **rx** - Elipse X radius.
    | int **ry** - Elipse Y radius.
    | int **xc** - Elipse center x.
    | int **yc** - Elipse center y.
    | int **color** - Elipse color.

    Returns nothing.

* **Description**:
    | Draws an filled elipse.

* **Example**:
    .. code-block:: c

       display.fillElipse(100, 200, 400, 300, 0);


Inkplate::drawPolygon();
########################

* **Method prototype (as seen in shapes.hpp)**:

.. code-block:: c

    void drawPolygon(int *x, int *y, int n, int color);

* **Arguments and return value**:
    | int ***x** - Polygon points X coordinates.
    | int ***y** - Polygon points Y coordinates.
    | int **n** - Number of points.
    | int **color** - Elipse color (just the edge, see fillElipse for fully filled).

    Returns nothing.

* **Description**:
    | Draws an empty(not filled) polygon.

* **Example**:
    .. code-block:: c

       display.drawPolygon(xt, yt, n, 0);

Inkplate::fillPolygon();
########################

* **Method prototype (as seen in shapes.hpp)**:

.. code-block:: c

    void fillPolygon(int *x, int *y, int n, int color);

* **Arguments and return value**:
    | int ***x** - Polygon points X coordinates.
    | int ***y** - Polygon points Y coordinates.
    | int **n** - Number of points.
    | int **color** - Elipse color (just the edge, see fillElipse for fully filled).

    Returns nothing.

* **Description**:
    | Draws a filled polygon.
    | Can be quite slow.

* **Example**:
    .. code-block:: c

       display.fillPolygon(xt, yt, n, 0);

Inkplate::drawThickLine();
##########################

* **Method prototype (as seen in shapes.hpp)**:

.. code-block:: c

    void drawThickLine(int x1, int y1, int x2, int y2, int color, float thickness);

* **Arguments and return value**:
    | int **x1** - x coordinate of line start, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int **y1** - y coordinate of line start, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | int **x2** - x coordinate of line end, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int **y2** - y coordinate of line end, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | int **color** - line color, in 3 bit mode in range [0, 7]
    | float **thickness** - line thickness in pixels

    Returns nothing.

* **Description**:
    | For drawing thick lines.

* **Example**:
    .. code-block:: c

        display.drawThickLine(random(0, 799), random(0, 599), random(0, 799), random(0, 599), BLACK, (float)random(1, 20));

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4350.jpg
        :width: 600


Inkplate::drawGradientLine();
#############################

* **Method prototype (as seen in shapes.hpp)**:

.. code-block:: c

    void drawGradientLine(int x1, int y1, int x2, int y2, int color1, int color2, float thickness = -1);

* **Arguments and return value**:
    | int **x1** - x coordinate of line start, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int **y1** - y coordinate of line start, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | int **x2** - x coordinate of line end, [0, 799] in rotations 2, 4 and [0, 599] in 1, 3
    | int **y2** - y coordinate of line end, [0, 599] in rotations 2, 4 and [0, 799] in 1, 3 
    | int **color1** - start line color, in 3 bit mode in range [0, 7]
    | int **color2** - start line color, in 3 bit mode in range [0, 7]
    | float **thickness** - line thickness, defaults to -1 meaning use normal, non thick, line.

    Returns nothing.

* **Description**:
    | For drawing color gradient lines.
    | color1 should always be less than color2.

* **Example**:
    .. code-block:: c

        int startColor = random(0, 7);
        int endColor = random(startColor, 7);
        display.drawGradientLine(random(0, 799), random(0, 599), random(0, 799), random(0, 599), startColor, endColor, (float)random(1, 20));

* **Result**:
    | Here is what the code above produces:

    .. image:: images/IMG_4353.jpg
        :width: 600


Network Client
--------------

Inkplate::disconnect();
#######################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c 

    void disconnect();

* **Arguments and return value**:
    | No arguments.
    | Returns nothing.

* **Description**:
    | Disconnects Inkplate from wifi network (shuts network).

* **Example**:
    .. code-block:: c

        display.disconnect();

Inkplate::isConnected();
########################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c 

    bool isConnected();

* **Arguments and return value**:
    | No arguments.
    | Returns 1 if connected to wifi, 0 if not.

* **Description**:
    | Checks if inkplate is connected to wifi.

* **Example**:
    .. code-block:: c

        if(display.isConnected())
        {
            //Do something
        }

Inkplate::joinAP();
#######################

* **Method prototype (as seen in inkplate.hpp)**:

.. code-block:: c 

    bool joinAP(const char *ssid, const char *pass);

* **Arguments and return value**:
    | const char \*ssid - name of the wifi network.
    | const xhar \*pass - network password.
    | Returns 1 if successfuly connected, 0 if not.

* **Description**:
    | Sets and connects inkplate to wifi network.

* **Example**:
    .. code-block:: c

        //In setup
        while(!display.joinAP(ssid, pass))
        {
            Serial.println("Connecting to wifi");
        }

Inkplate::downloadFile();
#########################

* **Method prototype (as seen in network_client.hpp)**:

.. code-block:: c 

    uint8_t *downloadFile(const char *url, int32_t *defaultLen);

* **Arguments and return value**:
    | const char \*url - link to file.
    | int32_t \*defaultLen - expected lenght (only matters if real length cant be checked).
    | Returns file as byte buffer, NULL if failed to get file.

* **Description**:
    | Downloads file from given url.

* **Example**:
    .. code-block:: c

        char url = "https//:www.somepic.com/pic.jpg"
        int32_t len = 54373;
        jpeg file = display.downloadFile(url, len);

ESP Functions
-------------

Inkplate::millis();
###################

* **Method prototype (as seen in esp.hpp)**:

.. code-block:: c 

    long millis();

* **Arguments and return value**:
    | No arguments.
    | Returns time in milliseconds since boot.

* **Description**:
    | Returns time in milliseconds since boot.

* **Example**:
    .. code-block:: c

        long time = millis();

Inkplate::delay_microseconds();
###############################

* **Method prototype (as seen in esp.hpp)**:

.. code-block:: c 

    void delay_microseconds(uint32_t micro_seconds);

* **Arguments and return value**:
    | uint32_t **micro_seconds**.
    | Returns nothing.

* **Description**:
    | Stops program for given micro_seconds.

* **Example**:
    .. code-block:: c

        delay_microseconds(2000000)//waits for 2 seconds

Inkplate::delay();
##################

* **Method prototype (as seen in esp.hpp)**:

.. code-block:: c 

    void delay(uint32_t milliseconds);

* **Arguments and return value**:
    | uint32_t **milliseconds**.
    | Returns nothing.

* **Description**:
    | Stops program for given milliseconds.

* **Example**:
    .. code-block:: c

        delay(2000)//waits for 2 seconds

Inkplate::analog_read();
########################

* **Method prototype (as seen in esp.hpp)**:

.. code-block:: c 

    int16_t analog_read(adc1_channel_t channel);

* **Arguments and return value**:
    | adc1_channel_t **channel** to read from.
    | Returns read value.

* **Description**:
    | Returns read value from channel/pin.

* **Example**:
    .. code-block:: c

        float val = analog_read(15);

Wire Functions
--------------

Inkplate::begin_transmission();
###############################

* **Method prototype (as seen in wire.hpp)**:

.. code-block:: c 

    void begin_transmission(uint8_t addr);

* **Arguments and return value**:
    | uint8_t **addr** device address we will establish communication with.
    | Returns nothing.

* **Description**:
    | Starts communication with device.

* **Example**:
    .. code-block:: c

        begin_transmission(0xH3);

Inkplate::end_transmission();
#############################

* **Method prototype (as seen in wire.hpp)**:

.. code-block:: c 

    void end_transmission();

* **Arguments and return value**:
    | No Arguments.
    | Returns nothing.

* **Description**:
    | Ends communication with device.

* **Example**:
    .. code-block:: c

        end_transmission();

Inkplate::write();
##################

* **Method prototype (as seen in wire.hpp)**:

.. code-block:: c 

    void write(uint8_t val);

* **Arguments and return value**:
    | uint8_t **val** data that will be sent to device.
    | Returns nothing.

* **Description**:
    | Sends data to device.

* **Example**:
    .. code-block:: c

        uint8_t data = 0x21;
        write(data);

Inkplate::read();
#################

* **Method prototype (as seen in wire.hpp)**:

.. code-block:: c 

    void read(uint8_t val);

* **Arguments and return value**:
    | No Arguments.
    | Returns data from device.

* **Description**:
    | Reads data from device.

* **Example**:
    .. code-block:: c

        uint8_t data = read();

Inkplate::request_from();
#########################

* **Method prototype (as seen in wire.hpp)**:

.. code-block:: c 

    esp_err_t request_from(uint8_t addr, uint8_t size);

* **Arguments and return value**:
    | uint8_t **addr** device address to request data from.
    | uint8_t **size** number of bytes we are requesting.
    | Returns esp_err_t value that indicates successful or failed connection.

* **Description**:
    | Requests data from device.

* **Example**:
    .. code-block:: c

        esp_err_t error = request_from(0xH3, 7);

MCP Functions
-------------

Inkplate::set_direction();
##########################

* **Method prototype (as seen in mcp.hpp)**:

.. code-block:: c 

    void set_direction(Pin pin, PinMode mode);

* **Arguments and return value**:
    | Pin **pin** pin number.
    | PinMode **mode** pin mode.
    | Returns nothing.

* **Description**:
    | Sets device pin mode (INPUT, INPUT_PULLUP OUTPUT).

* **Example**:
    .. code-block:: c

        display.set_direction(11, OUTPUT);

Inkplate::digital_write();
##########################

* **Method prototype (as seen in mcp.hpp)**:

.. code-block:: c 

    void digital_write(Pin pin, SignalLevel state);

* **Arguments and return value**:
    | Pin **pin** pin number.
    | SignalLevel **state** HIGH or LOW signal.
    | Returns nothing.

* **Description**:
    | Sets device output state (HIGH or LOW).

* **Example**:
    .. code-block:: c

        display.digital_write(11, SignalLevel::HIGH);

Inkplate::digital_read();
#########################

* **Method prototype (as seen in mcp.hpp)**:

.. code-block:: c 

    SignalLevel digital_read(Pin pin);

* **Arguments and return value**:
    | Pin **pin** pin number.
    | Returns pin INPUT state (HIGH or LOW).

* **Description**:
    | Gets pin input state (HIGH or LOW).

* **Example**:
    .. code-block:: c

        uint8_t pin_state = display.digital_read(11);

Inkplate::set_int_output();
###########################

* **Method prototype (as seen in mcp.hpp)**:

.. code-block:: c 

    void set_int_output(IntPort intPort, bool mirroring, bool openDrain, SignalLevel polarity);

* **Arguments and return value**:
    | IntPort intPort - intPort portA or portB.
    | bool mirroring - mirroring set 1 to make ports mirror each other so that any interrupt will cause both to go HIGH.
    | bool openDrain - openDrain set 1 to set interupt port as open drain, this will override port polarity.
    | SignalLevel polarity - sets port interrupt polarity, 1 active high, 0 active low.
    | Returns nothing.

* **Description**:
    | Sets port interupt state.

* **Example**:
    .. code-block:: c

        display.set_int_output(IntPort::INTPORTA, 0, 0, SignalLevel::LOW);

Inkplate::set_int_pin();
########################

* **Method prototype (as seen in mcp.hpp)**:

.. code-block:: c 

    void set_int_pin(Pin pin, IntMode mode);

* **Arguments and return value**:
    | Pin pin - pin number.
    | IntMode mode - interrupt mode (CHANGE, FALLING, RISING).
    | Returns nothing.

* **Description**:
    | Sets pin interupt state.

* **Example**:
    .. code-block:: c

        display.set_int_pin(11,IntMode::CHANGE);

Inkplate::remove_int_pin();
###########################

* **Method prototype (as seen in mcp.hpp)**:

.. code-block:: c 

    void remove_int_pin(Pin pin);

* **Arguments and return value**:
    | Pin pin - pin number.
    | Returns nothing.

* **Description**:
    | Removes interupt from pin.

* **Example**:
    .. code-block:: c

        display.remove_int_pin(11);

Inkplate::get_int();
####################

* **Method prototype (as seen in mcp.hpp)**:

.. code-block:: c 

    void get_int();

* **Arguments and return value**:
    | No Arguments.
    | Returns interupt registers state.

* **Description**:
    | Returns interrupt registers state for portA and portB. 
    | Every bit represents interrupt pin, MSB is  PORTB PIN7, LSB is PORTA PIN1.

* **Example**:
    .. code-block:: c

        display.get_int();

Inkplate::get_int_state();
##########################

* **Method prototype (as seen in Mcp.h)**:

.. code-block:: c 

    uint16_t get_int_state();

* **Arguments and return value**:
    | No argument.
    | Returns interupt registers state at the time interrupt occured.

* **Description**:
    | Returns interrupt registers state for portA and portB. 
    | Every bit represents interrupt pin, MSB is  PORTB PIN7, LSB is PORTA PIN1.

* **Example**:
    .. code-block:: c

        uint16_t intrrupts = display.get_int_state();

Inkplate::set_ports();
######################

* **Method prototype (as seen in Mcp.h)**:

.. code-block:: c 

    void set_ports(uint16_t values);

* **Arguments and return value**:
    | uint16_t values - values to be writen to port A and port B registers.
    | Returns nothing.

* **Description**:
    | sets internal state of PORTA and PORTB registers.
    | MSB byte is for PORTB, LSB byte for PORTA

* **Example**:
    .. code-block:: c

        uint16_t data = 0xFFFF;//to make all bits ones
        display.set_ports(data);

Inkplate::getPorts();
#####################

* **Method prototype (as seen in Mcp.h)**:

.. code-block:: c 

    uint16_t getPorts();

* **Arguments and return value**:
    | No arguments.
    | Returns register states of PORTA and PORTB.

* **Description**:
    | returns internal states of PORTA and PORTB registers.
    | MSB byte is for PORTB, LSB is for PORTA.

* **Example**:
    .. code-block:: c

        display.getPorts();
