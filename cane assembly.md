# Assembly instructions for the Augmented Cane:

See the components in the bill of materials listed in the repository to ensureyou purchase the correct components.

## Setting up software on the Raspberry Pi: 

The open-source software uses aRaspberry Pi image which can be downloaded from our repository. 
This image contains the operating system and code that will run on the Rasberry Pi. Once downloaded, 
unzip the image file(approximately 32 GB in size). Insert your microSD card into your computer using the SD card adapter. 
We will transfer the image to the microSD card using a free program called balenaEtcher. 

Install this software and open it. Select the image location that you downloaded,
select the microSD card as the drive to install to, and click “Flash!”. 
Once this has completed, you can eject the microSD card and insert it into the Raspberry Pi. 
You have finished installing the software and are ready to assemble the hardware.

Due to a [bug](https://github.com/SkoltechRobotics/rplidar/issues/36#issuecomment-787668203) in the Lidar software, install 

`$ sudo pip3 install rplidar-roboticia` 

## Building thehardware:

1.To connect the camera to the Raspberry Pi, please see the Raspberry Pi Foundationinstructions: 
https://projects.raspberrypi.org/en/projects/getting-started-with-picamera

2.To connect the RPLIDAR to the Raspberry Pi, simply plug theUSB connector into the Raspberry Pi as shown in the image below.

3.To connect the GPS breakout board to the Raspberry Pi, you will need to solder the VIN, GND, TX, RXpins on theGPS board to the 5V, GND, RX, 
TXpins on the Adafruit protohat board that will be connected to the Raspberry PI.
The RX and TX should be connected to the opposite pins(RX is receive for GPS board, but TX (transmit) for the Pi). 
See example wiring info here: https://learn.adafruit.com/adafruit-ultimate-gps/circuitpython-parsinga.
To see an example of hot the protohat can be used with the Raspberry Pi, check out this Adafruit project: https://learn.adafruit.com/reef-pi-power-controller

4.To connect the IMU breakout boardyou will need tosolder the VIN, GND, SCL, SDA pins on the IMU board to the 5V, GND, SCL, SDA pins on the Adafruit protohat.

5. DO NOT CONNECT THE Vm & GND from the motor controller to the arduinio
The motor controller should be soldered following these instructions: 
https://learn.adafruit.com/adafruit-drv8871-brushed-dc-motor-driver-breakout/a.
Please note that the power for the motor will be supplied from the LiPo battery on the bill of materials. 
DO NOT DIRECTLY SOLDER THE BATTERY TO THE POWER PINS. Solder a connector to the power pins so the battery can be disconnected.

6.The pushbutton used to turn off the motor during operation (option for use) should have one end soldered to the #18 pin on the Adafruit 
protohatand the other pin soldered to 3.3V.

7.The Raspberry Pi will be powered by the rechargeable batteryconnected into the RaspberryPi USB-C port. 

8.The Raspberry Pi should be protected with the provided casein the bill of materials. 
The cobbler breakout allows the Adafruit protohat board to be attached to the Raspberry Pi while it is in the case. 
For attaching all the sensors to the cane you can 3D print the shell housing(STL file in the repository) 
either with a local 3D printer or using an online service such as Protolabs.
I have uploaded the shell file to Shapeways to make it easy to order directly to your house: 
https://www.shapeways.com/product/CSHCYNAWM/augmented-cane-3d-printed-shella.The components that do not mount to the 3D 
printed shell (batteries, etc) can be attached to theRaspberry Pi case inside the shell with tape or Velcro.
I’ve attached additional imagesof the assembly to help with this process.

9.Assembling the omniwheel and motor assembly will require a hand drill. 
Drill a hole in theend of the cane.Assemble the motor, two aluminum mounting hubs, omniwheel, 
and 4mm shaft as shownin the image below.

10.You can run the different programs already installed by 
using thecommand line to navigate to the correct directory and entering the following commands:
```
a.sudo python3 obstacle_avoidance.py
b.sudo python3gps_navigation.py
```
