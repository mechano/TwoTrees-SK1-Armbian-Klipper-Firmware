# TwoTrees-SK1-Armbian-Klipper-Firmware
An Armbian and Klipper firmware for TwoTrees SK1

**READ CAREFULLY THIS README. 
IT'S MANDATORY TO FLASH BOTH MCU AND THR BOARD!**

TwoTrees SK1 firmware based on Armbian 1.1.3-25.11.0-trunk Ubuntu Noble edge version from Maxim Medvedev.

[https://github.com/redrathnure/armbian-mkspi](https://github.com/redrathnure/armbian-mkspi)

Ubuntu Noble is an LTS (Long Time Support) that will get update till year 2034.

Shell user `mks` password `makerbase` is already configured and home directory is `/home/mks`
It's possible to enter using also `root` password `makerbase`

The firmware has Klipper 0.13 and Kiauh software already installed. Use this tool to update Klipper.

The main interface is Mainsail, use Kiauh to install FLUIDD.

Crowsnest is already installed and configured for my inexpensive camera module.

Feel free to navigate into the `macro.cfg` file to see macros, modify, add your own macros.

When the filament touch filament runout sensor get grabbed by extruder gear, ready for run `LOAD_FILAMENT` macro.

It receives an IP address thru the ethernet port. So you can enter using an SSH client like Putty.
The firmware has Avahi daemon already installed and the hostname you'll use on the network is `twotrees.local`
So if your computer has Avahi client installed you can use URL `http://twotrees.local` to access the web interface.

Built-in Wifi card works out-of-the-box no driver needed. Use this command via shell to configure wifi:

`sudo nmcli dev wifi connect "YOUR_SSID" password "YOUR_PASSWORD"`

Using gcodes on USB pendrive is supported, just plug an USB pendrive formatted in FAT32 (not bigger than 32GB), and an sda1 or sda2 (for two pendrives) will appear into gcodes section of Mainsail/FLUIDD.

The screen works with Tortillery project for Artillery Sidewinder X4 printer and is in vertical position, sorry but I'm still dealing to make one specific for SK1.
**THIS TOOL HAS SOME BUGS: few gcode files are shown in the screen. Use web interface for full gcode view.**

- There's not option to start/stop blower.
- Anyway Z-offset, moving, temperature work good.
- There's also a terminal and if you remember the name of your macros you can write directly like: LOAD_FILAMENT, UNLOAD_FILAMENT.

[https://github.com/CiareCw455/Tortillery](https://github.com/CiareCw455/Tortillery)

If you don't like the vertical screen , don't use it and revert to other projects like the CYD-Klipper screen.

[https://github.com/suchmememanyskill/CYD-Klipper](https://github.com/suchmememanyskill/CYD-Klipper)

<img width="721" height="1278" alt="image" src="https://github.com/user-attachments/assets/f35b6304-99bf-4041-a7f9-aae076a0a004" />

Flash MCU and THR following the tutorial of "tomsbasement" on Github.

[https://github.com/tomsbasement/twotrees-sk1?tab=readme-ov-file#upgrade-the-th-board](https://github.com/tomsbasement/twotrees-sk1?tab=readme-ov-file#upgrade-the-th-board)

It's necessary to solder an header (Dupont or better JST X2.54) and build a cable using an old USB cable adapter, where cut the micro USB part.

Using command `make menuconfig` you have to set this parameters for THR with chip RP2040 and MCU with ST32F401 (Follow the tutorial).

<img width="832" height="172" alt="Schermata da 2025-01-09 23-04-46" src="https://github.com/user-attachments/assets/58ca33de-00c8-4d04-8d3c-63fc80ded199" />

<img width="910" height="475" alt="Schermata da 2025-03-01 11-20-39" src="https://github.com/user-attachments/assets/29e138e1-c40a-47a1-953f-d2f628d8081f" />

Useful pics of mainboard pinouts:

![sk1-pinout-diagrams-mcu](https://github.com/user-attachments/assets/8af735ca-3220-4c45-96fe-e3291a56c518)

![sk1-pinout-diagrams-thr](https://github.com/user-attachments/assets/ceb6e370-5755-4d33-96b4-e930fce04d35)

Firmware is ready with scripts to create belt tension and X/Y input shaper graphs.
You'll find them into `config/input_shaper` folder.

<img width="800" height="600" alt="belt-tension-resonances-2024-12-24-204011" src="https://github.com/user-attachments/assets/2fa57fa5-072c-4c8d-9423-875b77851bba" />

<img width="800" height="600" alt="resonances_x_2024-12-24-205740" src="https://github.com/user-attachments/assets/af9c8f22-370b-470f-a103-97794325708b" />

<img width="800" height="600" alt="resonances_y_2024-12-24-205803" src="https://github.com/user-attachments/assets/a0cf7d80-ffeb-4c38-b43e-458ed38655e4" />

