# Wanhao-D6-Marlin-2.0.x
This is a repository for my Marlin 2.0.x config files for the Wanhao D6+ (Bondtech &amp; Microswiss)

Wanhao D6 BMG Upgrade
https://www.bondtech.se/product/wanhao-d6-kit/

All Metal Hotend with SLOTTED Cooling Block for Duplicator 6 
https://store.micro-swiss.com/products/all-metal-hotend-with-slotted-cooling-block-for-duplicator-6

**Installing AVRDUDE**

Make sure your USBASP is plugged into the Raspberry PI and the the cable is plugged into the ICSP port.

**SSH Into your Raspberry PI running Octoprint using Bitvise SSH:**

![image](https://user-images.githubusercontent.com/6380390/112827353-d7138c80-9053-11eb-9850-021c386bb6d3.png)

https://www.bitvise.com/ssh-client-download

**Via the Terminal enter the following lines one at a time:**

sudo apt-get update
sudo apt-get upgrade
sudo apt-get install avrdude

**Verify the avrdude installation location by entering:**

which avrdude

![image](https://user-images.githubusercontent.com/6380390/112827188-9e73b300-9053-11eb-8a39-c129c97be8e1.png)

**Copy the firmware to your /home/pi directory Raspberry PI using Bitvise:**

![image](https://user-images.githubusercontent.com/6380390/112827082-7dab5d80-9053-11eb-9d5b-6decff96024d.png)


**Enter the follow command to flash the firmware to the Wanhao D6:**

root@octopi:/home/pi# avrdude -c usbasp -p m2560 -u -U flash:w:firmware.hex

**Once the flashing is finished the printer will restart.**

**Tweaking your settings. 3D Printers are not tools you can set it and forget it.** 

1. My print environment will not be the same as yours and this is true for any printer settings you obtain online. 
You will need to make sure to PID Autotune for the bed and the extruder. My hotend is wrapped in fiberglass shield heat tape. I have a printer room and I enclosed the sides of my printer so there is no air conditioning interfering with my prints. 
2. You will need to goto your slicer of choice and adjust your retraction settings. I print mainly ABS on this printer.
3. You will need to save your firmware settings via m500.
4. When using a Microswiss Hotend you will need to do Temperature tests with every filament you use. The temp needed to print could be +/- 10-15 degrees and this is normal.
5. Dry your filaments before use. Don't assume any filament you use is dry. It can be wet from the day it was made, plastic allows moisture through it over time. New filament only means New to You. It doesn't mean that it hasn't been sitting on a dock or in a wharehouse somewhere for months.

**Octoprint**
I use Octoprint with this printer. You will want to make sure to download any plugins you need to control the printer.
https://octoprint.org/download/
