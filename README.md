## CinePi Frame8 Build Guide

### Introduction
The CinePi project can be found at https://github.com/schoolpost/CinePI
The Frame8 Model can be found at https://makerworld.com/en/models/1438499-cinepi-frame8-raspberry-pi-box-camera-v1?from=search#profileId-1496822

I made a video on this project and it can be found [here](https://youtu.be/cIMDtogM464)

The makers of the software and the 3D models have put in an incredible amount of effort, so I want to give back a tiny bit by documenting the build process as best I can. The end goal of this guide is to walk you through how to build the DIY cinema project built on the projects linked above. While the Frame8 project has a guide, I feel that pictures and thorough explanations may help more people build the project.

### Materials
The materials are linked in the makerworld project, so I won’t copy them here. There were a few links that weren’t linked properly so I have added those below:

- 1/4"-20x5mm Heat Inserts (Recommended to buy 2 packs in build, 1 should do here since there are 60 pieces): https://amzn.to/4tsb1fE
- M2.5 Standoffs: https://amzn.to/3ZgyZwl
- Dupont Wires: https://amzn.to/4rtTvWg

### CinePi installation
Note that this project is made for a Raspberry Pi 4 Model B. I went with the 8GB version and the project recommends at least 4GB. 

- Download a Raspberry Pi imager if you haven't already: https://www.raspberrypi.com/software/ (balenaEtcher is another one I use)
- Download the CinePi-V2-alpha.zip file located here: https://github.com/schoolpost/CinePI/releases/tag/v0.0.1-alpha
- Unzip the file to get the .img file
- Flash this img to your SD card and install it into the Raspberry Pi

### 3D Printing
Using the makerworld project, print out the parts. Note that there is a multi-color frame and a single color frame, so it isn’t going to take as long as makerworld reports.

### The Build
The author of the CinePi Frame8 project has a guide with all the information you'll need, but everything wasn’t clear to me upon reading it. It was designed so no soldering was needed, but there are some important things to keep in mind:

⚠️ Always power off the device using the touchscreen interface, not the physical power button. Once the system is shut down, then remove USB-C power. Improper shutdown via the physical button may damage the camera.
⚠️ When connecting the SmallRig battery, ONLY use the USB-C output

##### Outside of the Case
I wanted to connect all the parts outside of the case so I had more room to work. In my case, my display was bad and it saved a lot of time since I had everything easily accessible. If you’d like, you can skip to [The Case](#the-case)

- Connect the camera module to the pi. Note that the blue side of the cable goes towards the USB/ethernet ports. Now is also a good time to put the lens on the camera module.
- Place 20mm standoffs on the pi as seen in the image. Note that these will be taken out later.
  
  ![alt text](imgs/IMG_0809.jpeg)
  
- Add a 40 pin spacer onto the pi for the incoming Geekworm board

  ![alt text](imgs/IMG_0808.jpeg)
  
- Place the Geekworm board onto the pi

  ![alt text](imgs/IMG_0810.jpeg)
  
- Connect a 40 pin spacer to the HyperPixel display. Attach the FPC board to the display.

  ![alt text](imgs/IMG_0807.jpeg)
  
- Connect the ribbon cable between the FPC boards (make sure the blue is facing the same way as the picture)

  ![alt text](imgs/IMG_0814.jpeg)
  
- Place the free FPC board onto the Geekworm board

  ![alt text](imgs/IMG_0817.jpeg)
  
- At this point, everything should be connected and you can connect the USB-C port on the Smallrig battery to the GEEKWORM USB-C port. If everything is connected properly, the HyperPixel display should come on.

##### The Case
First, we need to add all the heat inserts. Heat inserts can be pushed into the holes with a soldering iron (and probably pliers to keep the insert in place when removing the iron). The M2.5 inserts go into the inside of the camera to attach the pi (4), the body for the camera module (4), on the top for the lid (4), and onto the lid (4). The author recommends to attach the 5mm standoffs to the inserts for the inside of the camera. Tip: the knurled side faces out, the other side usually helps you guide the piece in. It’s also recommended to leave the piece sticking out slightly and finishing the insertion with a flat piece of metal or a rod of some sort for a clean finish. 

![alt text](imgs/IMG_0834.jpeg)
![alt text](imgs/IMG_0835.jpeg)

Similarly, we can add 35 1/4”-20 heat inserts all over for accessories like the battery pack, the SSD holder, and the grip. These are not necessary if you don’t want to use these accessories.

![alt text](imgs/IMG_0881.jpeg)
![alt text](imgs/IMG_0883.jpeg)
![alt text](imgs/IMG_0885.jpeg)
![alt text](imgs/IMG_0886.jpeg)
![alt text](imgs/IMG_0887.jpeg)

Now, we can place the pi in the case onto the 5mm standoffs previously added and secure it with 20mm standoffs. In this image I also fed the camera wire through the opening.

![alt text](imgs/IMG_0860.jpeg)

My camera module came with a tripod mount that needed to be removed before putting the printed cover pieces on top and securing the camera with 12mm 2.5 hex screws. Be sure to not over-tighten. After the camera is in place, connect the ribbon cable back to the pi (blue facing towards USB/ethernet ports). This is a little difficult so it might be better to do it before securing the pi, but it’s doable.

![alt text](imgs/IMG_0869.jpeg)
![alt text](imgs/IMG_0877.jpeg)

Remove the fan from the Geekworm board. If you’d like to switch it to a Noctua fan, the makerworld write up had details to do it with Dupont wires, but I felt it was easier with crimping a JST-PH 4 pin connector. With this approach, the wires are in the order of Black-Yellow-Green-Blue when looking at the board the same way as the picture below. You will then secure the fan to the case with the screws that came with the fan. I decided to orient the fan so it blows the hot air out (fan label touching the case), but it might be a better idea to use it to cool things down (label facing inward).

![alt text](imgs/IMG_0867.jpeg)
![alt text](imgs/IMG_0864.jpeg)

Next, attach the USB-C mount to the case.

![alt text](imgs/IMG_0871.jpeg)

Attach the Geekworm board to the pi on the pins/standoffs. Tip: plug in the USB-C right angle cord before doing this, or else you’ll probably be taking it back out. Secure the board with 4mm 2.5 hex screws.

![alt text](imgs/IMG_0875.jpeg)

Next up is the power button. The pins on the Geekworm board map like this to the button wires:

1: Power on/off -> Black wire 1 (I chose the one to the left of the + red)
2: Ground -> Black wire 2
3: Ground -> Red Wire -
4: LED -> Red Wire +

The wires from the button are a bit thick so it is a little tricky and the Dupont wires might be a better option. I did manage to get it to work, though so it is an option. Note that the Geekworm board pins are in numerical order as seen in the image below.

![alt text](imgs/IMG_0888.jpeg)

Place the FPC board onto the Geekworm board.

![alt text](imgs/IMG_0889.jpeg)

Now it’s all done and you can secure the lid with 4 6 (or 8)mm M2.5 hex screws. To me, the screen goes on the opposite way than I expected because you twist the ribbon cable.

![alt text](imgs/IMG_0891.jpeg)
![alt text](imgs/IMG_0904.jpeg)

Attach the screen with the screen mounts and screw the display frame onto the lid with 10 12mm M2.5 hex screws. To me, the screen goes on the opposite way than I expected because you twist the ribbon cable.

![alt text](imgs/IMG_0893.jpeg)

Mount the battery mount to the back of the camera so you can attach your battery.

![alt text](imgs/IMG_0895.jpeg)

### Accessories
Storfis made some accessories that can be attached with the 1/4"-20 Slotted Screws. There’s a handle mount, side handle, external SSD holder, 15mm bar holder, and a 15mm bar cheese plate. You may want to get 5 packs of the slotted screws to attach all of these (or more if you have plans for adding more accessories or things to the cheeseboard).

![alt text](imgs/IMG_0897.jpeg)
![alt text](imgs/IMG_0898.jpeg)
![alt text](imgs/IMG_0902.jpeg)
