This is the Official Repo for Project Blue OS for the Milk V Duo S
This iso is Alpha Release V1.0
Because Milk V Duio S hardware and acceleration blocks are proprietary and locked down but they provide the Linux drivers - I am using 
Linux as a tiny driver level with Project Blue OS riding on top of that.

Instructions:
------------
Flash the iso onto a SD card
Plug into the milk V duo S board
ensure your networking is using the following (hard coded):
Milk V Duo S: Always 192.168.42.1
*The actual board uses the USB RNDIS interface — no WiFi hardware exists on my development board so I had to do this.
SSH root@192.168.42.1  pw: milkv

