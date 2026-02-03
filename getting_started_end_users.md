# Getting Started for End Users

Prerequisites: An assembled ENTS board with the [latest firmware](#how-to-check-what-firmware-is-on-your-ents-board).

<ol>
    <li>Open any resources that you need. During part of the ENTS configuration process, you will use your device to connect to a wifi network with no internet access.</li>
    <ul>
        <li>Keep this guide open in a window or tab.</li>
        <li>If you were provided with a spreadsheet containing the calibration values and other ENTS information, keep that open as well.</li>
        <li>If you were not provided with a logger ID on your instance of [ents-backend](https://github.com/jlab-sensing/ENTS-backend), create a logger by logging in to your instance and navigating to your profile page's "Loggers" tab.</li>
        <ul>
            <li>When creating the Logger, use the values provided to you for the DevEUI, JoinEUI, and AppKey (also visible during step 3 of the process to find out what [firmware version](#how-to-check-what-firmware-is-on-your-ents-board) you have). Take note of the Logger ID after you successfully create your logger, you will use it later.</li>
        </ul>
        <li>If you were not provided with a cell ID on your instance of [ents-backend](https://github.com/jlab-sensing/ENTS-backend), create a cell by logging in to your instance and navigating to your profile page's "Cells" tab.</li>
        <ul>
            <li>You should give your cell a memorable name. The location and coordinates can be edited later, so you can enter in placeholder values if you are not sure (or do not want to use the map functionality). Take note of the Cell ID after you successfully create your cell, you will use it later.</li>
        </ul>
    </ul>

<li>After receiving your ENTS board, plug it into power. You can use a USB cable to connect the ENTS board's USB-C port to your computer or to a 5V >=500mA power supply (such as a phone charger).</li>

<p align="center" width="100%">
    <img src="ents power cropped.png" alt="ENTS power connection options" width="50%"/>
    <br>
    <em>Figure 1:</em> To power the ENTS board, use a USB cable to connect the board to a charger or a host device.
</p>

<li>Upon bootup, the ENTS board will broadcast a WiFi hotspot named `ents-` followed by its device address, which looks like 8 random letters and numbers (ex. `ents-06099AEA`). You can find your board's device address written on the back of the board in the white boxes. Use your phone or computer to connect to your board's WiFi network. The default password for initial configuration is `ilovedirt`.</li>
    <ul>
    <li>It is recommended to uncheck any options to "remember this network" or "automatically connect" to avoid accidentally connecting to ENTS board's WiFi in the future. You can also manually forget the network after finishing the setup process in this guide.</li>
    <li>While you are connected to the ENTS' WiFi network, you will not have access to the broader internet.</li>
    </ul>
<p align="center" width="100%">
    <img src="ents wifi cropped.png" alt="ENTS wifi for configuration" width="50%"/>
    <br>
    <em>Figure 2:</em> After powering on the ENTS board, connect to the wifi network it is broadcasting, then open a web browser to [192.168.4.1](http://192.168.4.1).
</p>

<li>After connecting to the ENTS' WiFi network, open a web browser and navigate to [192.168.4.1](http://192.168.4.1). This webpage is hosted locally by the ENTS board, and is used to configure the ENTS board for your use case.</li>

<li>Fill out the form on the webpage. Some details may already be filled in based on previous configurations to that ENTS board. Text which has a triangle next to it can be clicked on to show help text.</li>
    <ul>
        <li>If you do not have a LoRaWAN gateway, make sure to select "WiFi" for the upload method.</li>
    </ul>

<p align="center" width="100%">
    <img src="wifi user config cropped.png" alt="ENTS wifi user config" width="50%"/>
    <br>
    <em>Figure 3:</em> For a duration after booting up, the ESP32 on the ENTS board broadcasts a wifi network for the purposes of letting the user wirelessly configure the device. The webpage hosted by the ESP32 is shown here.
</p>

<li>Click on the green `Save Configuration` button and follow the instructions to press the white `RST` button near the USB port, closest to the corner.</li>

<li>On your host device, close the webpage and disconnect from the ENTS' WiFi network.</li>

<li>Unplug your ENTS board from its power source.</li>

<li>Connect your ENTS board to the sensors that you have enabled.</li>
    <ul>
        <li>To simultaneously take voltage and current readings, use the following configuration, where R is a 2 kOhm resistor:</li>
    </ul>

        ```
        (+) -----+----- [V+]
                 |      [V-]
                 +--R-- [I+]
                        [I-]
        (-) ----------- [GND]
        ```


<p align="center" width="100%">
    <img src="ents connect sensors cropped.png" alt="ENTS sensor connections" width="50%"/>
    <br>
    <em>Figure 4:</em> The I2C and SDI-12 bus is exposed at the bottom of the board through the JST header and 3 position screw terminal. Voltage and current readings can be made through the 5 position screw terminal at the right.
</p>

<li>Reconnect your ENTS board to a power source.</li>

<li>Observe the blinking status LED near the white RST button at the corner of the board.</li>
    <ul>
    <li>It should initially be blinking slowly: searching for internet connection.</li>
    <li>Then it will blink quickly: connecting to internet and attempting to upload data.</li>
    <li>Finally it will turn off: successfully uploaded data.</li>
    <li>If the LED is solidly on, then it has encountered an error and has halted the program. Try power cycling the device: While the board is connected to power, press and hold the blue RST button and white RST button at the same time, then release the blue RST button before releasing the white RST button.</li>
    </ul>
</ol>


# How to check what firmware is on your ENTS board

0. You will need a serial monitor application and may need to install USB drivers in order to check your firmware.
    - [CoolTerm](https://freeware.the-meiers.org/) (Windows, MacOS, Linux), [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) (Windows), `screen` (MacOS, Linux), and `minicom` (MacOS, Linux) are examples of commonly used desktop applicaations for opening a serial monitor. There are also a variety of serial monitor apps available for [Android](https://play.google.com/store/apps/details?id=de.kai_morich.serial_usb_terminal) and iOS.
    - If you cannot, you may need to install drivers for your device to recognize the ENTS board's serial chip ([CP2102](https://www.silabs.com/software-and-tools/usb-to-uart-bridge-vcp-drivers?tab=downloads)) as a device capable of being connected to with a serial monitor. Installation instructions are available within the zip file's release notes text file.
1. To check if you have the latest firmware, connect your ENTS board to your computer with a USB cable.
2. Open a serial monitor on the port that you just connected with 8N1 (typically the default setting) and 115200 baud.
   
3. After connecting your serial monitor, press the white RST button near the corner of the board and observe the text on the serial monitor. There is a line that is printed near the large "ENTS" message that describes the commit ID.
    - For firmware versions after commit [3031db9](https://github.com/jlab-sensing/ENTS-node-firmware/commit/3031db9a9ec6f4b8116c062067c236101f7b3d51) (2026-01-08), the DevEUI, JoinEUI, and AppKey are provided as well.
4. Compare the commit ID reported by the ENTS board against the commit ID of the latest release on the [ents-firmware repository's releases page](https://github.com/jlab-sensing/ENTS-node-firmware/releases). If they match, then you have the latest release of the firmware.
