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
   
+----------+-------------------------+--------------------------------------+  
|  Types   |            items        |             Parameters               |   
+==========+=========================+======================================+   
|          |     Frequency Scope     |                         2            |
+----------+-------------------------+--------------------------------------+  
    
