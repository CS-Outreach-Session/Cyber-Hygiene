# Keystroke Injection attacks - 30 minutes
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
* 1. Open the [Duck code encoder page](https://ducktoolkit.com/encode)
* 2. Type or copy the script 1 into the box and then press encode the payload  as indicated in the Figure below and click on encode payload. You can copy the script from this [file](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyScript%20Script%201%20%E2%80%93%20Printing%20Hello%20World!!!)

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Duck_toolkit.PNG)

* 3. Download the inject.bin file. You will notice that you cannot open or read the Bin file, but the Rubber Ducky uses this file type to execute payloads. Although this is the easiest way to encode your files, there are other ways, such as for example via the command console by downloading the standard encoder at usbrubberducky.com.
* 5. Once you’ve downloaded the inject.bin file, copy it into the SD card via the Micro SD card reader. 
* 6. Place the SD card into the Rubber Ducky and then insert it into a USB slot on a computer. If the script is executing correctly the light should flash green and the computer will open a new notepad and type Hello World.


Congratulations! You have just executed your first script.

Repeat the above 1 - 6 steps to execute script 2 as illustrated in the following Figure. You can copy the script from this [file.](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyScript2-%20Printing%20you%20have%20been%20hacked') 

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Duck_toolkitscript2.PNG)

# Exercises
Penetration testers use more complex scripts to explore (reconnaissance) or perform Keystroke Injection attacks to test a target's security posture. Use the following scripts to observe and comment on the effects of the attacks.

## Reconnaissance Scripts
* In the context of cyber security, reconnaissance is the practice of covertly discovering and collecting information about a system. This method is often used in ethical hacking or penetration testing. Repeat the above 1 - 6 steps to execute the following scripts:

  * What kind of information about a user can you gather by executing the [duckyscript3](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyScript3) ?
  * What kind of infromation about a network can you gather by executing the [duckyscript4](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyScript4) ?
## Exploit Scripts -  Malicious code injection attack 
* A malicious code attack is a foundational tool used to carry out most cybersecurity attacks to create or exploit computer vulnerabilities. Hackers use this attack method to cause unwanted changes, damage, or spread malware into the computer system. In this exercise, you will practice executing code injection attacks by plugging a USB into a computer system. The script you are to run is safe, thus, no need to panic.  Repeat the above 1 - 6 steps to execute the following scripts:
  * What can you observe by executing the [duckyscript5](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/duckyscript5-Malicious%20code%20injection%20attack) ?
# Take home
Suppose you allow an attacker access to your computer system or network or allow them to install or execute programs on your network. In that case, they may spread malware, disable or modify your computer or network system applications, firewalls to bypass controls limiting network usage, and successfully launch sophisticated attacks. Changes or modifying your Firewall rules or computer configurations could undermine the entire security posture of a network or computer system.  A typical example is if an attacker has access to your computer or server and plugin their USB, an attacker can cause enormous damages to your network system. 



