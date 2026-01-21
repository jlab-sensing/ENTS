# Getting Started for End Users

Prerequisites: An assembled ENTS board with the [latest firmware](#how-to-check-what-firmware-is-on-your-ents-board).

1. After receiving your ENTS board, plug it into power. You can use a USB cable to connect the ENTS board's USB-C port to your computer or to a 5V >=500mA power supply (such as a phone charger).
2. Upon bootup, the ENTS board will broadcast a WiFi hotspot named `ents-unconfigured` (or `ents-` followed by some numbers according to its logger ID, ex. `ents-572`). Use your phone or computer to connect to this WiFi network.
    - It is recommended to uncheck any options to "remember this network" or "automatically connect" to avoid accidentally connecting to ENTS board's WiFi in the future. You can also manually forget the network after finishing this guide.
3. After connecting to the ENTS' WiFi network, open a web browser and navigate to [192.168.4.1](http://192.168.4.1). This webpage is hosted locally by the ENTS board, and is used to configure the ENTS board for your use case.
4. Fill out the form on the webpage. Some details may already be filled in based on previous configurations to that ENTS board.
    - Upload Settings
      - Logger ID: In order for the logger's data to be accepted by the server, you must provide a valid Logger ID here.
        - You can create a Logger ID on your instance of [ents-backend](https://github.com/jlab-sensing/ENTS-backend) by logging in and navigating to your Loggers page. When creating the Logger, use the values provided to you for the DevEUI, JoinEUI, and AppKey.
      - Cell ID: Specify which cell that this logger should upload data to.
        - You can create a cell on your instance of [ents-backend](https://github.com/jlab-sensing/ENTS-backend) and get its Cell ID by logging in and navigating to your Cells page.
      - Upload Method: Choose between WiFi or LoRaWAN communication. LoRaWAN communication requires a nearby LoRaWAN gateway (such as the Sentrius [RG191](https://www.ezurio.com/part/rg191)), so it is recommended to start with WiFi.
      - Upload Interval: Time in seconds between uploads. Minimum recommended time is 10 seconds.
    - Measurement Settings: In this section, check the box next to each sensor that you want to enable and connect to this ENTS board.
      - If you are using voltage or current, you should also input the calibration values provided to you.
    - WiFi Settings
      - WiFi SSID: Name of the WiFi network to connect to.
      - WiFi Password: Password for the WiFi network to connect to. Leave blank if you are connecting to a non password-protected (open) WiFi network.
        - Keep the "Use previous password" box unchecked so that the new password that you enter will be used instead!
      - API Endpoint URL: Change this to point to your [ents-backend](https://github.com/jlab-sensing/ENTS-backend) instance's API endpoint URL. Typically, this should look similar to: `http://your-ents-backend-instance.com/api/sensor/`
5. Click on the green `Save Configuration` button and follow the instructions to press the white `RST` button on the ENTS board near the USB port.
6. On your host device, close the webpage and disconnect from the ENTS' WiFi network.
7. Unplug your ENTS board from its power source.
8. Connect your ENTS board to the sensors that you have enabled.
9. Reconnect your ENTS board to a power source.
10. Observe the blinking status LED near the white RST button at the corner of the board.
    - It should initially be blinking slowly: searching for internet connection.
    - Then it will blink quickly: connecting to internet and attempting to upload data.
    - Finally it will turn off: successfully uploaded data.
    - If the LED is solidly on, then it has encountered an error and has halted the program. Try power cycling the device: While the board is connected to power, press and hold the blue RST button and white RST button at the same time, then release the blue RST button before releasing the white RST button.

<figure>
  <img src="wifi user config cropped.png" alt="ENTS wifi user config" />
  <figcaption><em>Figure 2:</em> For a duration after booting up, the ESP32 on the ENTS board broadcasts a wifi network for the purposes of letting the user wirelessly configure the device. The webpage hosted by the ESP32 is shown here.
</figcaption>
</figure>

# How to check what firmware is on your ENTS board

1. To check if you have the latest firmware, connect your ENTS board to your computer with a USB cable.
2. Open a serial monitor on the port that you just connected with 8N1 (typically the default setting) and 115200 baud.
   - [CoolTerm](https://freeware.the-meiers.org/) (Windows, MacOS, Linux), [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) (Windows), `screen` (MacOS, Linux), and `minicom` (MacOS, Linux) are examples of commonly used desktop applicaations for opening a serial monitor.
   - There are also a variety of serial monitor apps available for Android and iOS which will also suffice.
   - If there does not appear to be any ports connected, you may need to install drivers for your device to recognize the ENTS board's serial chip ([CP2102](https://www.silabs.com/software-and-tools/usb-to-uart-bridge-vcp-drivers?tab=downloads)) as a device capable of being connected to with a serial monitor. Installation instructions are available within the zip file's release notes text file.
3. After connecting your serial monitor, press the white RST button near the corner of the board and observe the text on the serial monitor. There is a line that is printed near the large "ENTS" message that describes the commit ID.
4. Compare the commit ID reported by the ENTS board against the commit ID of the latest release on the [ents-firmware repository's releases page](https://github.com/jlab-sensing/ENTS-node-firmware/releases). If they match, then you have the latest release of the firmware.
