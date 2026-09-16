This is the Official Project Blue repo for the Milk-V Duo S.
**Created by Julian DeVante Feb 2026 **

Project Blue is a full-featured graphical operating system / desktop environment for the Milk-V Duo S (SG2000 RISC-V SBC with TPU).

YouTube Video: https://www.youtube.com/watch?v=wLz_8ZoN-vs



This .img.xz file is the SD Card image for Project Blue. Alpha Release Version 1.5

1. Follow the instructions to flash the img file to the SD card
2. Insert the SD card into the Milk V Duo S board and plug the USB cable into the board and connect to computer
3. Ensure your computer networking is serving DHCP to the Milk-V Duo S board
4. Enter 192.168.41.1 into the IP Box for the Project Blue COntrol Station html file - try pinging the board from the ping button
5. Click COnnect - to connect to the Milk V Duo S board - the desktop should appear and start streaming

* The Milk V Duo S board uses USB RNDIS (IP over USB)
* Username: root pw: milkv
  
* * I did not have a Wifi board for development so this is a NON-WIFI build
 
  * Report any issues to me DeVante.julian@gmail.com - Enjoy!
 
  ***Just added Alpha V1.5***
  Project Blue for the Milk V Duo S  (Aplha V1.5) to the right under Releases
  
  This is the actual Project Blue bin to be placed on the SD card in the rootfs (in root)
  
  Replace the V1.1 project_blue_linux bin in the rootfs root with this one and reboot the board 

  to unzip this file use command: xz -d project_blue_linux.xz

