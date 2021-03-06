# Weaponized USB devices- Keystroke Injection attacks 
* A Keystroke Injection Attack has been an issue for computer users for a long time, and it is problematic due to the affordability and availability of keystroke injection tools.


* With the use of a specially designed USB device (the Rubber Ducky), often disguised as a thumb drive, that automatically runs code on any host computer into which it is plugged. 
Hackers commonly use a keystroke injection attack to execute malicious commands via a USB drive connected to a host computer. 

* A malicious code attack is a foundational tool used to carry out most cybersecurity attacks to create or exploit computer vulnerabilities.

* In prticular, USB devices are the main source of malware for industrial control systems - inlcuding nuclear control system.

* Hackers use this attack method to cause unwanted changes, damage, or spread malware into the computer system.

*  In this activity, you will implement a simple form of USB keystroke injection attacks. The Rubber Ducky uses a simple coding language called Ducky Script language, that when inserted into a computer, acts as a programmable keyboard executing a payload script that has been programmed into the device. 

## Hardware for the activity - USB Rubber Ducky
![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/rubber-ducky-usb-full-kit.jpg)

## Rubber Ducky Parts

There are three main parts that come with the Rubber Ducky that you’ll be using to create, test and launch exploits.
* The mini “keyboard” adapter.  This a silicon chip with a CPU and a slot for inserting the microSD card – the card comes mounted inside the keyboard adapter when you order it. 
* The microSD card. This is a pretty standard piece of hardware. You’ll receive a fairly small 12MB microSD card, but it has more than enough space for running most payloads. 
* The microSD-to-USB adapter. This is the smaller plastic USB dongle that slides into a case. You’ll use this adapter to mount the microSD card on your machine as a normal USB storage device so that you can transfer your payload to it.
* A compiled version of the file can then be stored on a Micro SD card that is seated in the Rubber Ducky as shown below. When plugged into a USB port, the Ducky will execute the script.

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/usbRubberD.PNG)
To utilise the USB Rubber Ducky, you need to assemble the Ducky pack a Miro SD Card reader as indicated in the above Figure.

# Writing your duckyScript #
## Using rubber ducky to display "  You have been hacked " on a victims' computer ##
The sduckyScript is a simple scripting language for automating keypresses. It was originally developed for USB Rubber Ducky. It can be programmed in any ASCII text editor such as notepad, gedit nano, vo, emacs etc. Each command resides on a new line and may have the following options. Commands are written in ALL CAPS.


To begin coding writing your script complete the following tasks:
* 1. Open the [Duck code encoder page](https://ducktoolkit.com/encode)
* 2. Type or copy the script 1 into the box and then press encode the payload  as indicated in the Figure below and click on encode payload. You can copy the script from this [file](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyScript%20Script%201%20%E2%80%93%20Printing%20Hello%20World!!!)

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Screenshot_rubber_duccky%20.png)

* 3. Download the inject.bin file. You will notice that you cannot open or read the Bin file, but the Rubber Ducky uses this file type to execute payloads. Although this is the easiest way to encode your files, there are other ways, such as for example via the command console by downloading the standard encoder at usbrubberducky.com.
* 5. Once you’ve downloaded the inject.bin file, copy it into the SD card via the Micro SD card reader. 
* 6. Place the SD card into the Rubber Ducky and then insert it into a USB slot on a computer. If the script is executing correctly the light should flash green and the computer will open a new notepad and type Hello World.


Congratulations! You have just executed your first script.

# Exercise
Penetration testers use more complex scripts to explore (reconnaissance) or perform Keystroke Injection attacks to test a target's security posture. Use the following scripts to observe and comment on the effects of the attacks. Repeat the above i - vi steps to execute the following scripts.
  1. What can you observe by executing the [duckyscript3](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyScript3) ?
  2. What can you observe by executing the [duckyscript4](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyScript4) ?
  3. What can you observe by executing the [duckyscript5](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyscript5-Malicious%20code%20injection%20attack) ?
  4. What can you observe by executing the [duckyscript6](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyScript6) ? 
  
# You dont' have to try this - Example Reverse-Shell #

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Dont%20try%20this%20.png)

# How to protect systems against weaponized USB devices
![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/How_to_protect_system_Gainst_Keystroke.png)

# Excercise

Can you think of any other way of preventing automated keystroke injection attacks? 

Use this [Paddlet link](https://yorksj.padlet.org/ausman3/zksusqedk08y1ran) to write your answers for the questions. The password for the link is mYdOGISBigenough@89. To write on the paddlet you may need to click on the + button or double click anywhere on the screen.

# Take home #
The USB Rubber Ducky can be used to infect any computer it's plugged into with ransomware once the SD card is loaded. While this is a simulation, identical approaches might be used by a real attack# er. You prevent yourself from these types of attacks by always taking reasonable precautions when leaving your computer unattended. Never leave your computer unattended without first securing it, and never use USB drives that you don't recognise.

Many businesses expose USB ports to clients and visitors, and receptionists and other office workers frequently leave their workstations unattended. These kinds of errors might result in crucial corporate data being destroyed or held hostage. It's crucial to keep in mind.

Suppose you allow an attacker access to your computer system or network. In that case, they may spread malware, disable or modify your computer or network system applications, firewalls to bypass controls limiting network usage, and successfully launch sophisticated attacks.

A typical example is if an attacker has access to your computer or server and plugin their USB, an attacker can cause enormous damages to your network system. 



