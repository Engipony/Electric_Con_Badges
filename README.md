# Electric_Con_Badges
This is just an instruction set, files, and generally everything you need to make your own electronic convention badge that looks... ok and functions sometimes.

First off is the required items and software. You will need:
  One of the PCBs this project is based around
  A Adafruit ProTrinket 5V 16Mhz: https://www.amazon.com/gp/product/B0131VM9I0/ref=ppx_yo_dt_b_asin_title_o07_s01?ie=UTF8&psc=1
  A color TFT screen: https://www.amazon.com/gp/product/B01CZL6QIQ/ref=ppx_yo_dt_b_asin_title_o06_s00?ie=UTF8&psc=1
  Some THT 3 pin switches: https://www.amazon.com/gp/product/B007QAJUUS/ref=ppx_yo_dt_b_asin_title_o05_s00?ie=UTF8&psc=1
  Any full sized SD card that is freshly formatted (FAT32) is also needed
  And a battery charger board: https://www.adafruit.com/product/2124
    This charger board can be ordered along with a battery, I reccommend a 500mAh battery to get the most use out of this system
  
  You will also need a soldering iron and solder as well as basic soldering knowledge
    Having a helping hands can help quite a bit as well, but everything should be doable without one
  
  For software you will need the Arduino IDE asw well as any photo editing program that lets you resize and convert photos to bitmaps     you can literally just use MS Paint for this.

Making the PCB:
I recommend using JLC PCB to manufacture the boards since their prices are pretty great and their quality is pleanty good for this project.
Upload the zipfile (which contains the gerber files) to JLC PCB and select prototype board, 2 layer with 100mm X 60mm as the dimensions

Soldering:

You will need to solder on the 5 SD logic pins onto the display yourself
You will also need to short J1 on the back of the TFT board with a bead of solder to make the screen operate on 5V logic
On the "Li Battery backpack" you will need to add in all the available pins and you will ned to cut the trace between the switch pins
  The switch pins are the ones inside of the silkscren box and are connected by a copper trace visible on the top of the board
The front side of the main PCB for the project is the side with the text and with the "Engi" signature at the bottom.
  As suggested, the "Engi" signature is the botom of the PCB
 The Pro Trinket must be oriented so that the USB port is at the top of the main PCB. You do not need to solder on the FTDI pins.
 All other componants should be obvious how they are oriented (and of course switches and resistors have no specific orientation)
 DO NOT SOLDER ON THE SCRNON/OFF SWITCH. LOW QUALITY SWITCHES HAVE A GOOD CHANCE OF CAUSING A SHORT CIRCUIT. IT IS UNUSED IN THE CODE.
 
Photo Prep:
 
All photos must be no more than 320 x 240 px in size (this is the limit of the display itself)
All photos must also be saved at 24-bit bit maps since that's what the program is expecting
 
Code:
 
The code itself is pretty simple and is just a modified version of the Demo code from the Adafruit ILI9340 library (the modifications are pretty basic themselves)
Check the comments to see how to add more images/ponytown basic animations

Uploading the code is a bit harder since I will be explaining how to do it over USB. If you have a FTDI breakout, feel free just to use that though

First you will need to open up the Arduino IDE and select File>Prferences
In the "Additional Boards Manager URLs"  section enter: https://adafruit.github.io/arduino-board-index/package_adafruit_index.json
Then press "OK"
Then go to Tools>Board>Boards Manager...
Search "adafruit" and install "Adafruit AVR Boards by Adafruit version 1.4.13" it should say that it inclues the Pro Trinket
Then go to Tools>Boards and select "Pro Trinket 5V/16MHz (USB)"
Next go to Tools>Programmer and switch to USBtinyISP
Now you can "Verify" your code to make sure that it will complie without issue
To program the board make sure that you plug it in (via USB) to your PC and then press the button on the Trinket board and click "Upload" in the Arduino IDE immediatly after (you have a 5 second window to get the code to upload to the board)
