User Manual for ESP-F
==============================
:Date:   2018-01-26

This section provides the user manual for ESP-F.

Introduction
------------
  The WiFi module ESP-F is manufactured by using a high-performance chip ESP8266EX, which can be seen in Fig. 1. This small chip is encapsulated an enhanced Tensilica’sL106  diamond series 32-bit kennel CPU with a SRAM. Thus, ESP8266 has the complete function Wi-Fi function; it not only can be applied independently, but can be used as a slaver working with other host CPU. When ESP8266 is applied as a slaver, it can start from the onboard Flash.  The built-in high-speed buffer is not only benefit to improve the system performance, but optimize the store system. In addition, ESP8266 can be used as Wi-Fi adapter by SPI/SDIO or I2C/UART interface, when it is applied to other MCU design.
  
  .. figure:: ../_static/ESPFStructure.png
    :align: center
    :alt: ESP-F Module Structure
    :figclass: align-center

    ESP-F Module Structure
  
  The ESP-F module supports the standard IEEE802.11 b/g/n/e/i protocol and the complete TCP/IP protocol stack. User can use it to add the  WiFi function for the installed devices, and also can be viewed as a independent network controller.  Anyway, ESP-F module provides many probabilities with the best price.

Parameters for ESP-F are listed as follows.

Paramters for ESP-F
"""""""""
+----------+-------------------------+--------------------------------------+  
|  Types   |            items        |             Parameters               |   
+==========+=========================+======================================+   
|          |     Frequency Scope     |  2.4G~2.5G(2400M~2483.5M)            |
+          +-------------------------+--------------------------------------+  
|          |                         |        802.11b: +20 dBm              |
+          +                         +--------------------------------------+ 
|          |      Transmit Power     |        802.11g: +17 dBm              |
+          +                         +--------------------------------------+  
|   WiFi   |                         |        802.11n: +14 dBm              |
+          +-------------------------+--------------------------------------+
|          |                         |       802.11b: -91 dbm (11Mbps)      |
+          +                         +--------------------------------------+  
|          |  Receiving sensitivity  |       802.11g: -75 dbm(54Mbps)       |
+          +                         +--------------------------------------+ 
|          |                         |       802.11n: -72 dbm(MCS7)         |
+          +-------------------------+--------------------------------------+  
|          |      Antenna            |       PCB onboard antenna            |
+----------+-------------------------+--------------------------------------+ 
|          |      CPU                |       Tensilica L106 32 bit MCU      |
+          +-------------------------+--------------------------------------+  
|          |                         | UART/SDIO/SPI/I2C/I2S/IR control     |
+          +    Perpherl             +--------------------------------------+
|          |                         |   GPIO/ADC/PWM/SPI/I2C/I2S           |
+          +-------------------------+--------------------------------------+  
|          |    Working voltage      |    2.5V ~ 3.6V                       |
+          +-------------------------+--------------------------------------+ 
| Hardware |    Working current      |    Average current: 80 mA            |
+          +-------------------------+--------------------------------------+ 
|          |   Working temperature   |    -40°C ~85°C                       |
+          +-------------------------+--------------------------------------+  
|          | Environment temperature |    -40°C ~ 85°C                      |
+          +-------------------------+--------------------------------------+
|          |      Size               |    16mm x 24mm x 3mm                 |
+----------+-------------------------+--------------------------------------+  
|          |    Wi-Fi  mode          |     Station/SoftAP/SoftAP+Station    |
+          +-------------------------+--------------------------------------+ 
|          |    Security mode        |     WPA/WPA2                         |
+          +-------------------------+--------------------------------------+ 
|          |    Encryption type      |    WEP/TKIP/AES                      |
+          +-------------------------+--------------------------------------+  
|Software  |    Update firmware      |    UART Download/OTA (by internet)   |
+          +-------------------------+--------------------------------------+
|          |     Software develop    |    Non-RTOS/RTOS/Arduino IDE etc.    |
+          +-------------------------+--------------------------------------+  
|          |    Network protocol     |    IPv4, TCP/UDP/HTTP/FTP/MQTT       |
+          +-------------------------+--------------------------------------+ 
|          |   User configuration    |AT+command/cloud sever/Android/iOS APP|
+----------+-------------------------+--------------------------------------+ 

PINs Definition

PINs definition of ESP-F can be shown in the following.

 .. figure:: ../_static/pinofESPF.png
    :align: center
    :alt: Pins definition for ESP-F Module
    :figclass: align-center

    Pins definition for ESP-F Module
    
Selection of Working Mode
^^^^^^^^^^^^^^^^^^^^^^^^^
    
Working mode and definition of pins:
"""""""""
+----------------+-------------------------+---------------------------+---------------+  
|  Mode          |        GPIO15           |          GPIO0            |    GPIO2      |   
+================+=========================+===========================+===============+   
|UART download   |        low              |          low              |     high      |
+----------------+-------------------------+---------------------------+---------------+ 
|FlashBoot mode  |        low              |          low              |     high      |
+----------------+-------------------------+---------------------------+---------------+ 

Function Definition of Module Pins
"""""""""
+----+-----+----+---------------------------------------------------------------------+  
| Num| Pin |Type|                            Function                                 |   
+====+=====+====+=====================================================================+   
| 1  | RST | I  |Reset the signal outside (enable with low), Reset module             |
+----+-----+----+---------------------------------------------------------------------+ 
| 2  | ADC | I  |A/D pin. Input voltage 0~1V,  value: 0~1024                          |
+----+-----+----+---------------------------------------------------------------------+
| 3  | EN  | I  |high level:chip work;low level:chip closes with small current.       |
+----+-----+----+---------------------------------------------------------------------+ 
| 4  | IO16| I/O|deep sleep/wakeup                                                    |
+----+-----+----+---------------------------------------------------------------------+ 
| 5  | IO14|I/O |GPIO14; HSPI_CLK                                                     |
+----+-----+----+---------------------------------------------------------------------+ 
| 6  | IO12|I/O |GPIO12;HSPI_MISO                                                     |
+----+-----+----+---------------------------------------------------------------------+ 
| 7  | IO13|I/O |GPIO13;HSPI_MOSI;UART0_CTS                                           |
+----+-----+----+---------------------------------------------------------------------+ 
| 8  | VCC | P  |Module working voltage: 3.3V                                         |
+----+-----+----+---------------------------------------------------------------------+ 
| 9  | CS0 |I/O |GPIO11; SD_CMD; SPI_CS0                                              |
+----+-----+----+---------------------------------------------------------------------+ 
| 10 |MISO |I/O |GPIO7; SD_D0, SPI_MSIO                                               |
+----+-----+----+---------------------------------------------------------------------+ 
| 11 | IO9 |I/O |GPIO9; SD_D2 PIHD; HSPIHD                                            |
+----+-----+----+---------------------------------------------------------------------+ 
| 12 | IO10|I/O |GPIO10; SD_D3;SPIWP; HSPIWP1                                         |
+----+-----+----+---------------------------------------------------------------------+ 
| 13 | MOSI|I/O |GPIO8; SD_D1;SPI_MOSI1                                               |
+----+-----+----+---------------------------------------------------------------------+ 
| 14 |SCLK |I/O |GPIO6; SD_CLK; SPI_CLK                                               |
+----+-----+----+---------------------------------------------------------------------+ 
| 15 | GND |  P |GND                                                                  |
+----+-----+----+---------------------------------------------------------------------+ 
| 16 |IO15 |I/O |GPIO15; MTDO;HSPICS;UART0_RTS                                        |
+----+-----+----+---------------------------------------------------------------------+ 
| 17 | IO2 |I/O |GPIO2; UART1_TXD                                                     |
+----+-----+----+---------------------------------------------------------------------+ 
| 18 | IO0 |I/O |GPIO0;SPI_CS2                                                        |
+----+-----+----+---------------------------------------------------------------------+
| 19 | IO4 | I/O|GPIO4                                                                |
+----+-----+----+---------------------------------------------------------------------+ 
| 20 | IO5 |I/O |GPIO5                                                                |
+----+-----+----+---------------------------------------------------------------------+ 
| 21 | RXD |I/O |GPIO3; used to build in Flash as UART Rx                             |
+----+-----+----+---------------------------------------------------------------------+ 
| 22 | TXD |I/O |GPIO1; used to build in Flash as UART Tx                             |
+----+-----+----+---------------------------------------------------------------------+ 

Shape and Size
---------------

Shape and size for this module can be shown as follows. Its size is 16mm*24mm*3mm, and the Flash is 4M bytes (32Mbits), together with the following picture.

 .. figure:: ../_static/ESPF.png
    :align: center
    :alt: ESP-F Module
    :figclass: align-center

    ESP-F Module
    
Size of ESP-F module
"""""""""
+--------+-------+--------+-----+-----------------------+  
| Length | Width | Height | Pin | Distance between pins |                                                         
+========+=======+========+=====+=======================+   
| 24.5mm | 14mm  |  3mm   | 4x2 |       2.54mm          |
+--------+-------+--------+-----+-----------------------+   
    
Electronical Characteristics
---------------------------

Please refers to the following table.

Electronical Property
"""""""""""
+-------------------+-------------+-------------+-----------+-----------+-----------+  
|    Parameters     | Condition   |      Min    | Classical |     Max   |    Unite  |                                            +===================+=============+=============+===========+===========+===========+   
|Store Temperature  |   N/A       |    -40      |   Normal  |    125    |    degree |
+-------------------+-------------+-------------+-----------+-----------+-----------+   
|Sold Temperature   |IPC/JEDEC    | N/A         | N/A       |    260    |   degree  |
|                   |J-STD-020    |             |           |           |           |
+-------------------+-------------+-------------+-----------+-----------+-----------+  
|Working Voltage    |   N/A       |   2.5       |   3.3     |    3.6    |     V     |
+-------------------+-------------+-------------+-----------+-----------+-----------+   
|       |  VIL/VIH  |  N/A        |-0.3/0.75VIO |   N/A     |0.25VIO/3.6|     V     |
+       +-----------+-------------+-------------+-----------+-----------+-----------+
|  I/O  |  VOL/VOH  |  N/A        |  N/0.8VIO   |   N/A     |  0.1VIO/N |    V      |
+       +-----------+-------------+-------------+-----------+-----------+-----------+   
|       |     IMAX  |   N/A       |  N/A        |  N/A      |    12     |   mA      |
+-------+-----------+-------------+-------------+-----------+-----------+-----------+
|Electrostatic(BODY)|  TAMB=25    |    N/A      |  N/A      |    2      |    kV     |
+-------------------+-------------+-------------+-----------+-----------+-----------+   
|Electrostatic(BODY)|  TAMB=25    |   N/A       |  N/A      |    0.5    |    kV     |
+-------------------+-------------+-------------+-----------+-----------+-----------+

Please refer to the following table.

Power Consumption
"""""""
+--------------------------------------+--------+------------+-------+------+
|     Parameters                       |  Min   |  Classical |  Max  |Unite |
+======================================+========+============+=======+======+
|Tx802.11b, CCK 11Mbps, POUT=+17dBm    |  N/A   |   170      |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+
|Tx802.11g, OFDM 54 Mbps, POUT =+15dBm |  N/A   |   140      |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+
|Tx802.11n,MCS7,POUT =+13dBm           |  N/A   |   120      |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+
|Rx 802.11b，1024 Bytes, -80dBm        |  N/A   |    50      |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+
|Rx 802.11g，1024 Bytes, -70dBm        |  N/A   |     56     |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+
|Rx 802.11n，1024 Bytes, -65dBm        |  N/A   |     56     |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+
|Modem-sleep①                          |  N/A   |     15     |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+
|Light-sleep②                          |  N/A   |     0.9    |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+
|Deep-sleep③                           |  N/A   |     20     |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+
|close                                 |  N/A   |    0.5     |  N/A  |  mA  |
+--------------------------------------+--------+------------+-------+------+

.. Note::
①  Modem-Sleep mode can be used for the case that CPU is always working, e.g., PWM or I2S etc. If WiFi is connected and no data is to transmitted, in this case, WiFi modem can be closed to save power energy. For example, if at DTIM3 status,  keep asleep at 300ms, Then, the module can wake up to receive the Beacon package within 3ms and the current being 15mA.

② Light-Sleep mode can used for the case that CUP can stop the application temporally, e.g.,  Wi-Fi Switch .  If  Wi-Fi is connected and there is no data packet to transmitted, by the 802.11 standard (e.g., U-APSD), module can close Wi-Fi Modem and stop CPU to save power. For example, at DTIM3,  keep up sleeping at  300ms, it would receive the Beacon package from AP after each 3ms, then the whole average current is about 0.9mA.

③ Deep-Sleep mode is applied to the case that Wi-Fi is not necessary to connect all the time, just send a data packet after a long time  (e.g., transmit one temperate data each 100s) . it just need 0.3s-1s to connect AP after each 300s, and the whole average current is much smaller 1mA.

Wi-Fi RF Characteristics
------------------------

The data in the following Table is gotten when voltage is 3.3V and1.1V in the indoor temperature environment. 

Wi-Fi RF Characteristics
""""""""""""""""""""""""
+----------------------------------------------+--------+----------+-------+------+
|At 72.2Mbps, output power consumption for PA  |  Min   | Classical|  Max  | unite|
+==============================================+========+==========+=======+======+
|Input frequencey                              | 2412   |    N/A   | 2484  | MHz  |
+----------------------------------------------+--------+----------+-------+------+
|Input impedance                               | N/A    |    50    | N/A   | Ω    |
+----------------------------------------------+--------+----------+-------+------+
|Input reflection                              | N/A    |    N/A   | -10   | dB   |
+----------------------------------------------+--------+----------+-------+------+
|At 72.2Mbps, output power consumption for PA  | 15.5   |    16.5  | 17.5  | dBm  |
+----------------------------------------------+--------+----------+-------+------+
|At 11b mode, output power consumption for PA  | 19.5   |    20.5  | 21.5  | dBm  |
+----------------------------------------------+--------+----------+-------+------+
|Sensibility                                   | N/A    |    N/A   | N/A   | N/A  |
+----------------------------------------------+--------+----------+-------+------+
|DSSS, 1Mbps                                   | N/A    |    -98   | N/A   | dBm  |
+----------------------------------------------+--------+----------+-------+------+
|CCK11, Mbps                                   | N/A    |    -91   | N/A   | dBm  |
+----------------------------------------------+--------+----------+-------+------+
|6Mbps(1/2 BPSK)                               | N/A    |    -93   | N/A   | dBm  |
+----------------------------------------------+--------+----------+-------+------+
|54Mbps(3/4 64-QAM)                            | N/A    |    -75   | N/A   | dBm  |
+----------------------------------------------+--------+----------+-------+------+
|HT20, MCS7(65 Mbps, 72.2 Mbps)                | N/A    |    -72   | N/A   | dBm  |
+----------------------------------------------+--------+----------+-------+------+
|Adjacent Inhibition                                                              |
+----------------------------------------------+--------+----------+-------+------+
|OFDM, 6Mbps                                   | N/A    |    37    | N/A   | dB   |
+----------------------------------------------+--------+----------+-------+------+
|OFDM, 54Mbps                                  | N/A    |    21    | N/A   | dB   |
+----------------------------------------------+--------+----------+-------+------+
|HT20, MCS0                                    | N/A    |    37    | N/A   | dB   |
+----------------------------------------------+--------+----------+-------+------+
|HT20, MCS7                                    | N/A   |     22    | N/A   | dB   |
+----------------------------------------------+--------+----------+-------+------+

The Recommended Sold Temperature Curve
-----------------------------------

 .. figure:: ../_static/ESPFtemperaturecurve.png
    :align: center
    :alt: ESP-F temperature curve
    :figclass: align-center

    ESP-F temperature curve
    
 Schematics for ESP-F
 --------------
 
    .. figure:: ../_static/ESPFSchematics.png
    :align: center
    :alt: Schematics for ESP-F
    :figclass: align-center
    
    Schematics for ESP-F
    
 Minimum System
 --------------
 
   .. figure:: ../_static/ESPFSchematics.png
    :align: center
    :alt: Schematics for ESP-F
    :figclass: align-center
    
 Schematics for ESP-F
 --------------   
 
 .. figure:: ../_static/ESPFMinimum.png
    :align: center
    :alt: Minimum for ESP-F
    :figclass: align-center
    
 Minimum for ESP-F
 
.. Note::
(1) the working voltage for module is DC 3.3V;
(2) the max current from IO of this module is 12mA;
(3) RST Pin is enabled when it is low level; and EN pin is enabled when it is high level;
(4) WiFi module is at update mode: GPIO0 is low level, then module reset to power;  Wi-Fi module is at working mode: GPIO0 is at high level, and then reset to power; 
(5) Wi-Fi module is connected to RXD of the other MCU, and TXD is connected to RXD of the other MCU.

The Recommended PCB Design
------------

Wi-Fi module can be inserted into the PCB board directly. For the high RF performance for the end device, please note the placement for the antenna and the module. 
    It is suggested that the module is placed along with PCB side, the antenna is placed outside the board, or along with the PCB side,  and the below board is blank, please refer to the scheme 1 and scheme 2; if the PCB antenna must placed on the board, please do not cover the copper at the bottom of PCB antenna, as can be shown at scheme 3.
    
 .. figure:: ../_static/ESPFS1.png
    :align: center
    :alt: Scheme1 for ESP-F
    :figclass: align-center
    
 Scheme1 for ESP-F
 
  .. figure:: ../_static/ESPFS1.png
    :align: center
    :alt: Scheme2 for ESP-F
    :figclass: align-center
    
 Scheme2 for ESP-F
 
  .. figure:: ../_static/ESPFS1.png
    :align: center
    :alt: Scheme3 for ESP-F
    :figclass: align-center
    
 Scheme3 for ESP-F
 
