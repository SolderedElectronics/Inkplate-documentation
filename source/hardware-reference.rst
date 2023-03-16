Inkplate Hardware Reference
============================

Inkplate family of e-paper displays is fully open-source and its full hardware design can be found in corresponding GitHub repositories:
    | `Inkplate 6 hardware <https://github.com/e-radionicacom/Inkplate-6-hardware>`_
    | `Inkplate 10 hardware <https://github.com/e-radionicacom/Inkplate-10-hardware>`_
    | `Inkplate 6PLUS hardware <https://github.com/e-radionicacom/Inkplate-6PLUS-Hardware>`_

Additionally, all active Inkplate boards are OSHWA certified:
    | `Inkplate 6 OSHWA <https://certification.oshwa.org/hr000003.html>`_
    | `Inkplate 10 OSHWA <https://certification.oshwa.org/hr000006.html>`_

Short overview
----------------

The schematics speak for themselves, but here is the short introduction to Inkplate hardware. Most boards share the same basic components:
    | ESP32 - microcontroller as the brains of the whole board. WiFi with PCB antenna, BLE, 4MB Flash, 8MB PSRAM, 240MHz. Driving the e-paper parallel lines directly.
    | \*MCP23017 - I2C IO expander. Driving the misc (slower) e-paper lines and providing some extra GPIO pins.
    | PCAL6416A - I2C IO expander. Replacement for MCP in newer Inkplates in time of chip shortage.
    | e-paper panel - depending on the specific Inkplate, the contents are shown on EPD. There's a special connector for each of them. Some have a backlight and touchscreen and thus the additional circuitry for those. 
    | CH340C - USB-UART adapter, paired with USB-C for programming and power. 
    | \*microSD card slot.
    | \*\*TPS65186 - special EPD power management IC, providing specific voltages needed to drive EPD properly. 
    | MCP73831 - lithium-ion battery charger. Linear and not so efficient one, but simple to use. Auto-select voltage source is on board as well.
    | 22uA low-power thanks to low Iq voltage regulator from TI TPS7A2633.
    | \*3 pieces touch pads based on TTP223. 
    | Reset supervisor TPS3840PL27D takes care of proper reset at upload and manual reset. 
    | \*Pushbutton style power button thanks to MC14093BD logic gate and a single MOSFET.

        | *Note* \* *- Not available on every Inkplate, check Features page.*
        | *Note* \*\* *- Colored screens (Inkplate 2 and 6COLOR) have integrated EPD power management.*