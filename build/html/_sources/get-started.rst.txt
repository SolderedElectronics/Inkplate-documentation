Inkplate Get Started Page
=========================

Arduino
-------

In order to get started with Inkplate 6 using Arduino IDE, follow the steps below:

#. Install the Inkplate 6 board definition to add Inkplate 6 as a board in Arduino IDE
#. Install the CH340 drivers (if you don't have them already)
#. Install the Inkplate 6 Arduino library from our GitHub repository (if you're not sure how, take a look at our tutorial)
#. Install this custom SdFat library to your Arduino IDE.
#. Your Inkplate 6 is now ready to go! Just select Tools -> Board -> Inkplate 6, choose the correct COM port, and upload your code!

Take a look at our examples in the library and the API refrence to see what you can code.

To use Peripheral Mode, connect your Inkplate 6 to the "Controller" board with a USB cable or via the ESP32 RX and TX pins. 
Using standard UART at 115200 baud, you can send commands to change the screen contents. 
For example, send #H(000,000,"/img.bmp") to display an img.bmp image file stored on the SD card. 
For detailed refrence see peripheral mode docs.

MicroPython
-----------

In order to get started with Inkplate 6 using MicroPython, follow the steps below:

#. Clone our repo at https://github.com/e-radionicacom/Inkplate-6-micropython and get your terminal inside the repo folder.
#. Flash MicroPython firmware supplied, or from http://micropython.org/download/esp32/ 
    To do so, run

    .. code-block:: 

        esptool.py --port /dev/cu.usbserial-1420 erase_flash 

    to erase esp32 flash and then

    .. code-block:: 

        esptool.py --chip esp32 --port /dev/cu.usbserial-1420 write_flash -z 0x1000 esp32spiram-idf4-20191220-v1.12.bin

    to flash supplied firmware.

    If you don't have esptool.py installed, install it from here: https://github.com/espressif/esptool.
#. Copy library files to your board, something like:

    .. code-block:: 

        python3 pyboard.py --device /dev/ttyUSB0 -f cp mcp23017.py sdcard.py inkplate.py image.py gfx.py gfx_standard_font_01.py :

    Replace /dev/ttyUSB0 with the port to which Inkplate is connected. Easiest way to find that our is to open Arduino IDE and see it under ports menu.
    
    (You can find pyboard.py in the MicroPython tools directory or just download it from GitHub: https://raw.githubusercontent.com/micropython/micropython/master/tools/pyboard.py)
#. Run example.py:

    .. code-block:: 

        python3 pyboard.py --device /dev/ttyUSB0 example.py

    Again replacing /dev/ttyUSB0 with the correct port.
    
    You can run our other 2 examples, showing how to use the Sd card and network class.

    In the same manner as running our examples you can run your own code and even set it to run on boot or similiar by following other MicroPython tutorials.