# Keystroke Injection attacks
A Keystroke Injection Attack has been an issue for computer users for a long time, and it is problematic due to the affordability and availability of keystroke injection tools.

With the use of a specially designed USB device (the Rubber Ducky), often disguised as a thumb drive, that automatically runs code on any host computer into which it is plugged. 
Hackers commonly use a keystroke injection attack to execute malicious commands via a USB drive connected to a host computer. 

In this activity, you will implement a simple form of USB keystroke injection attacks. The Rubber Ducky uses a simple coding language called Ducky Script language, that when inserted into a computer, acts as a programmable keyboard executing a payload script that has been programmed into the device. 
## Hardware for the activity - USB Rubber Ducky
![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/rubber-ducky-usb-full-kit.jpg)
## Rubber Ducky Parts

There are three main parts that come with the Rubber Ducky that you’ll be using to create, test and launch exploits.
* The mini “keyboard” adapter.  This a silicon chip with a CPU and a slot for inserting the microSD card – the card comes mounted inside the keyboard adapter when you order it. 
* The microSD card. This is a pretty standard piece of hardware. You’ll receive a fairly small 12MB microSD card, but it has more than enough space for running most payloads. 
* The microSD-to-USB adapter. This is the smaller plastic USB dongle that slides into a case. You’ll use this adapter to mount the microSD card on your machine as a normal USB storage device so that you can transfer your payload to it.
* A compiled version of the file can then be stored on a Micro SD card that is seated in the Rubber Ducky as shown below. When plugged into a USB port, the Ducky will execute the script.

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/usbRubberD.PNG)
To utilise the USB Rubber Ducky, you will need the Ducky pack and a Miro SD Card reader and writer.

## Writing your duckyScript
The sduckyScript is a simple scripting language for automating keypresses. It was originally developed for USB Rubber Ducky. It can be programmed in any ASCII text editor such as notepad, gedit nano, vo, emacs etc. Each command resides on a new line and may have the following options. Commands are written in ALL CAPS.


To begin coding writing your script complete the following tasks:
* Open the [Duck code encoder page](https://ducktoolkit.com/encode)
* Type or copy the script 1 into the box and then press encode the payload  as indicated in the Figure below

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Duck_toolkit.PNG)

*
[^note]:
    Named No responsibility is taken for any damage, harm or legal actions caused by misuse of this tutorial. The user should follow the guidelines contained in this document only for the purpose of education, otherwise no liability will be assumed. It is the user's responsibility to obey all effective laws in country, which may prohibit usage of this product.

