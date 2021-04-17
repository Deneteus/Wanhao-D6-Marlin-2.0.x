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
