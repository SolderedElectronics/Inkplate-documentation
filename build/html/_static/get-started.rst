Inkplate Get Started Page
=========================

Arduino
-------

In order to get started with Inkplate using Arduino IDE, follow the steps below:

#. Install the `Inkplate board definition <https://github.com/e-radionicacom/Croduino-Board-Definitions-for-Arduino-IDE>`_ to add Inkplate as a board in Arduino IDE
#. Install the `CH340 drivers <https://e-radionica.com/en/blog/ch340-driver-installation-croduino-basic3-nova2/>`_ (if you don't have them already)
#. Install the `Inkplate Arduino library <https://github.com/e-radionicacom/Inkplate-Arduino-library>`_ from our GitHub repository (if you're not sure how, take a look at our `tutorial <https://e-radionica.com/en/blog/arduino-library/#Kako%20instaliraty%20library?>`_)
#. Your Inkplate is now ready to go! Just select Tools -> Board -> Inkplate x, choose the correct COM port, and upload your code! To tweak your upload speed, you can set Upload speed to 921600. 

.. image:: images/BoardSelection.jpg
    :width: 500

Take a look at our `examples <examples.html>`_ in the library and the `API reference <api-reference.html>`_ to see what you can code.
To use `Peripheral Mode <peripheral-mode.html>`_, connect your Inkplate to the "Controller" board or computer with a USB cable or via the ESP32 RX and TX pins. For detailed reference see `Peripheral Mode <peripheral-mode.html>`_ docs.

MicroPython
-----------

In order to get started with Inkplate using MicroPython, follow the steps below:

#. Clone our repo for `micropython <https://github.com/e-radionicacom/Inkplate-6-micropython>`_ and get your terminal inside the repo folder.
#. Flash MicroPython firmware supplied, or from `official page <http://micropython.org/download/esp32/>`_
    To do so, run

    .. code-block:: 

        esptool.py --port /dev/cu.usbserial-1420 erase_flash 

    to erase esp32 flash and then

    .. code-block:: 

        esptool.py --chip esp32 --port /dev/cu.usbserial-1420 write_flash -z 0x1000 esp32spiram-idf4-20191220-v1.12.bin

    to flash supplied firmware.
    If you don't have esptool.py installed, install it from here: `esptool <https://github.com/espressif/esptool>`_.
    
#. Copy library files to your board, something like:

    .. code-block:: 

        python3 pyboard.py --device /dev/ttyUSB0 -f cp mcp23017.py sdcard.py inkplate.py image.py gfx.py gfx_standard_font_01.py :

    Replace /dev/ttyUSB0 with the port to which Inkplate is connected. Easiest way to find that out is to open Arduino IDE and see it under ports menu.
    (You can find pyboard.py in the MicroPython tools directory or just download it from GitHub: `pyboard <https://raw.githubusercontent.com/micropython/micropython/master/tools/pyboard.py>`_)

#. Run example.py:

    .. code-block:: 

        python3 pyboard.py --device /dev/ttyUSB0 example.py

    Again replacing /dev/ttyUSB0 with the correct port.
    You can run our other 2 examples, showing how to use the Sd card and network class.
    In the same manner as running our examples you can run your own code and even set it to run on boot or similiar by following other MicroPython tutorials.
    
ESP-IDF
-------

In order to get started with Inkplate using ESP-IDF, follow the steps below:

#. Clone `repo <https://github.com/turgu1/ESP-IDF-InkPlate.git>`_.

#. Setup ESP-IDF `tools <https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/>`_.

#. Connect Inkplate device and follow `instructions <https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/>`_.

#. You can run few examples from examples `folder <https://github.com/turgu1/ESP-IDF-InkPlate/tree/master/examples>`_ in repository.