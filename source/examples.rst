Examples
========

All examples included in our library can be found here: `Examples for Inkplate <https://github.com/e-radionicacom/Inkplate-Arduino-library/tree/master/examples>`_
After you download inkplate Arduino library you will have all examples inside Arduino IDE. There are comments in all examples that describe how it works and what hardware you need.

Basic Inkplate Functionality
----------------------------

Inkplate_Basic_BW
#################
    This example shows basic Inkplate functionalities in black and white mode (writing text, drawing shapes and images).

Inkplate_Basic_Gray
###################
    This example shows basic Inkplate functionalities in gray mode (writing text, drawing shapes and images).

Inkplate_Basic_Partial_Update
#############################
    This example shows how to properly use partial update on Inkplate.
    
    .. image:: images/example1.jpg
        :width: 500

Inkplate_Full_Screen_Colors
###########################
    Simple Inkplate example showing all colors of the Inkplate..

Inkplate_6Color_Basic
#####################
    Simple Inkplate example showing drawing functionalities of the Inkplate 6COLOR library.

Advanced Inkplate Features
--------------------------

Inkplate_Battery_Voltage_Temperature
####################################
    For this example you will need a Lithium battery (3.6V) with two pin JST connector. This example will show you how to read voltage of the battery and read temperature from on-board
    temperature sensor which is part of TPS65186 e-paper PMIC.
    NOTE: In order to read temperature, e-paper has to be refreshed at least one time
    
    .. image:: images/example2.jpg
        :width: 500

Inkplate_EasyC
##############
    For this example you will need a micro USB cable, Inkplate, BME680 sensor with easyC connector on it. 
    This example will show you how you can read temperature, humidity, air pressure and gas data from BME680.

    .. image:: images/example18.jpg
        :width: 500

Inkplate_Low_Power
##################
    For this example you will need USB cable and Inkplate.
    This example will show you how you can use low power functionality of Inkplate board.
    In deep sleep, whole board will consume about 25uA from battery.
    Inkplate will wake every 20 seconds change content on screen.
    
    .. image:: images/example3.jpg
        :width: 500

Inkplate_MCP23017_Expander
##########################
    For this example you will need only a micro USB cable, Inkplate, 330 Ohm resistor and LED diode.
    This example will show you how you can manipulate with I/Os of MCP23017 Expander.
    You can only manipulate with Port B of MCP23017 (GPB1-GPB7). Port A is used for epaper panel and TPS65186 PMIC.
    GPB0 is used for ESP32 GPIO0 so you can't use it either.
    
    .. image:: images/example19.jpg
        :width: 500

Inkplate_Partial_Update_With_Deep_Sleep
#######################################
    In this example we will show how to use partial update of epaper screen with deep sleep functionality of ESP32.

    .. image:: images/example4.jpg
        :width: 500

Inkplate_SD_Pictures
####################
    For this example you will need a micro USB cable, Inkplate and a SD card loaded with image1.bmp and image2.bmp file that can be found inside folder of this example.
    This example will show you how you can read .bmp and .jpeg files (pictures) from SD card and
    display that image on e-paper display.

Inkplate_SD_TXT_File
####################
    For this example you will need only a micro USB cable, Inkplate and a SD card loaded with text.txt file that can be found inside folder of this example.
    This example will show you how to open .txt files and display the content of that file on Inkplate epaper display.

Inkplate_Touchpads
##################
    For this example you will need only a micro USB cable and Inkplate.
    This example will show you how you can use built-in touchpads (on PCB marked with numbers 1, 2 and 3).
    They are basically touch sensitive switches.
    
    .. image:: images/example5.jpg
        :width: 500

Inkplate_Wake_Up_On_Touchpads
#############################
    This example will shown how to use MCP and ESP interrupts to wake up the MCU from deepsleep when touchpad is pressed.

    .. image:: images/example6.jpg
        :width: 500

Web_BMP_Pictures
################
    For this example you will need a micro USB cable, Inkplate, and an available WiFi connection.
    This example will show you how you can download a .bmp file (picture) from the web and
    display that image on e-paper display.

    .. image:: images/example7.jpg
        :width: 500

Inkplate_Web_Server
###################
    For this example you will need a micro USB cable, Inkplate and a device with WiFi and Internet brower (PC, Laptop, Smartphone etc).
    This example will show you how you can use Inkplate as a small and simple standlone Web Server.
    You need to connect to Inkplate with WiFi and open IP address shown on Inkplate display.

    .. image:: images/example8.jpg
        :width: 500

Inkplate_WiFi_HTTP
##################
    For this example you will need USB cable, Inkplate and stable WiFi Internet connection.
    This example will show you how to connect to WiFi network, get data from Internet and display that data on epaper.
    This example is NOT on to how to parse HTML data from Internet - it will just print HTML on the screen.
    
    .. image:: images/example9.jpg
        :width: 500

Community contributions
-----------------------

Game_Of_Life_By_Claud9999
#########################
    To run it, jut upload the code and watch Conways game of life animation!

    .. image:: images/example10.jpg
        :width: 500

Others
------

Inkplate_Factory_Programming_VCOM
#################################
    This example should not be used if you dont know what VCOM is and what exactly you are doing as it can damage panel.

Inkplate_Mandelbrot_Set
#######################
    This example renders the mandelbrot set to coordiantes to Inkplate. Due to the nature of Mandelbrot set, it is quite slow on low powered MCUs, so please be patient.

    .. image:: images/example11.jpg
        :width: 500

Inkplate_Maze_Generator
#######################
    This example renders a random maze every time.
    You can write on it with a whiteboard marker or a graphite pen to solve it, just be sure not to use pernament markers.

    .. image:: images/example12.jpg
        :width: 500

Inkplate_Peripheral_Mode
########################
    Using this sketch, you don't have to program and control e-paper using Arduino code. 
    Instead, you can send UART command. This give you flexibility that you can use this Inkplate on any platform.

Inkplate_VariPass_Graphs
########################
    This example will show you how you can use the API on the VariPass website to download and display
    a sensor graph on the e-paper display.
    
    .. image:: images/example13.jpg
        :width: 500

Mapbox_Api
########################
    This example will show you how you can use Inkplate 6COLOR to display map data.
    This example gets html data from crowdsource campaing and displays them on Inkplate screen.


Gallery
########################
     This example will show you how you can use Inkplate 6COLOR to random images in the root sdcard folder.

Projects
--------

Campaing_Tracker
################
    This example will show you how you can use Inkplate to display html data. 
    It gets html data from crowdsource campaing and displays them on Inkplate screen.

    .. image:: images/example14.jpg
        :width: 500

Cryptocurrency_Tracker
######################
    This example will show you how you can use Inkplate to display API data.
    Here we use Coingecko API to get last 90 days prices and display them on the Inkplate screen.

    .. image:: images/example15.jpg
        :width: 500

Daily_Weather_Station
#####################
    This example will show you how you can use Inkplate to display API data, e.g. Metaweather public weather API.

    .. image:: images/example16.jpg
        :width: 500

Google_Calendar
###############
    This project shows you how Inkplate can be used to display events in your Google Calendar using their provided API.   

    .. image:: images/example17.jpg
        :width: 500

Hourly_Weather_Station
######################
    This example will show you how you can use Inkplate to display API data, e.g. Metaweather public weather API, and weatherstack for real time data.

    .. image:: images/example21.jpg
        :width: 500
        
Image_Frame
###########
    This example shows how you can set inkplate to show random pictures from web.

Open_weather_station
####################
    This example will show you how you can use Inkplate to display API data, e.g. Metaweather public weather API.

    .. image:: images/example20.jpg
        :width: 500