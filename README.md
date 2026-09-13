This is the Official Project Blue repo for the Milk-V Duo S.
**Created by Julian DeVante Feb 2026 **

Project Blue is a full-featured graphical operating system / desktop environment for the Milk-V Duo S (SG2000 RISC-V SBC with TPU).

YouTube Video: https://www.youtube.com/watch?v=wLz_8ZoN-vs

This .img file is the SD Card image for Project Blue. Alpha Release Version 1.1

1. Follow the instructions to flash the img file to the SD card
2. Insert the SD card into the Milk V Duo S board and plug the USB cable into the board and connect to computer
3. Ensure your computer networking is serving DHCP to the Milk-V Duo S board
4. Enter 192.168.41.1 into the IP Box for the Project Blue COntrol Station html file - try pinging the board from the ping button
5. Click COnnect - to connect to the Milk V Duo S board - the desktop should appear and start streaming

* The Milk V Duo S board uses USB RNDIS (IP over USB)
* Username: root pw: milkv
  
* * I did not have a Wifi board for development so this is a NON-WIFI build
 
  * Report any issues to me DeVante.julian@gmail.com - Enjoy!



BlueScript - A Custom Scripting Language for Project Blue
BlueScript is a BASIC-like interpreted scripting language built into the Milk-V Duo S desktop environment. It lets users write .bb scripts that run as native windows with graphics, audio, and system access.
Language Features
Feature
Variables
Conditionals
Loops
Subroutines
Goto
Comments
Expressions
Built-in Command Categories
Graphics - Rendering to the window framebuffer:
- Graphics.FillRect x, y, w, h, color
- Graphics.DrawLine x1, y1, x2, y2, color
- Graphics.DrawCircle, Graphics.FillCircle
- Graphics.DrawString x, y, "text", color
- Graphics.DrawProportional (anti-aliased scaled text)
- Graphics.DrawTriangle, Graphics.DrawRect, Graphics.DrawButton
- Graphics.DrawImage "path.png", x, y
3D Rendering:
- 3D.DrawCube cx, cy, size, angY, angX, frontCol, backCol, edgeCol - Perspective-projected wireframe cube
- 3D.MatrixRotate "Y", 45 - Build rotation matrix in m0..m8 variables
- 3D.TransformPoints - Matrix-multiply vertex arrays v0_x, v0_y, v0_z...
- 3D.ProjectPoints - Perspective projection to p0_x, p0_y...
Sprites (16 cached slots):
- Sprite.Load id, "path.png" - Load PNG to RGB565 cache
- Sprite.Draw id, x, y / Sprite.DrawScaled id, x, y, scaleX, scaleY
Collision Detection:
- Collision.Rect ax, ay, aw, ah, bx, by, bw, bh → collision_hit
- Collision.Circle ax, ay, ar, bx, by, br → collision_hit, collision_dist
Math:
- Math.Sin deg, Math.Cos deg, Math.Sqrt val, Math.Abs val → result
- Math.Random min, max → result
Audio:
- Audio.PlaySfx sfxId - Play sound effect
- Audio.StreamMp3 "path.mp3" - Open music player
System / IO:
- IO.PRINT, IO.MKDIR, IO.REMOVE, IO.RENAME, IO.EXISTS, IO.Zip, IO.Unzip
- System.GetTimezone, System.SetTimezone, System.Reset
- SYSTEM.WGET "url", "dest" - Download via curl
- SYSTEM.PING "host" - Network ping
- Network.GetIP, Network.GetRSSI, Network.IsConnected
Peripherals (IoT):
- Peripherals.SetGpio ip, pin, val - Remote GPIO via UDP to port 5001
- Peripherals.GetAdc ip, pin - Remote ADC read
Event System
Scripts define event handlers as labels:
:onUpdate          # Called every frame (~30/60fps)
:onDraw            # Called to generate draw operations
:onMouseEvent      # event_type, event_x, event_y variables set
:onKeyboardEvent   # event_type, event_value variables set
