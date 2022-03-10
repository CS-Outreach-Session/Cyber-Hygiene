# Keystroke logging attacks 
  Keystroke logging, often called keylogging or keyboard capturing, is a common computer-based social engineering attack of recording the keys struck while a person using the keyboard is unaware that their actions are being monitored. 

Keyloggers are often used for nefarious means, like spying on a user to steal sensitive data such as their usernames and passwords by seeing the target type it themselves. Data such as user password, login, or bank details can then be retrieved by the person operating the logging program.
We will see how easy it is to record users’ keystrokes in these exercises.
	 
 ## AirDrive Forensic Keylogger Pro – USB
 The AirDrive Forensic Keylogger pack contains just the Keylogger itself (shown below), which has a male and female USB port. A female port is the receiver side, and the male side is the connector. The device acts as a WiFi access point you can connect to, with either a computer, smartphone, laptop, etc.
 
 While connected, you will receive a constant live stream of strokes the keyboard is typing. The device only works with external USB keyboards as the device has to be plugged inline between the keyboard and PC; hence it does not work with inbuilt keyboards like laptops or a computer desktop. 
 
 ![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/AirDrive_Forensic_Keylogger%20Pro_USB.PNG)
 
  ## Setup
  
  Installation of the KeyGrabber USB is quick and easy. Simply plug it in between the USB keyboard and the USB port. The port can be loose, so make sure the keyboard is still working, and you can type.

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Setup_AirDrive_Forensic_Keylogger%20Pro_USB.PNG)

## Configurations 
* Once connected, open a web-browser and type in 192.168.4.1. The device will respond with a webpage presenting the data log, settings, and configuration options.

* To begin monitoring the strokes of the keyboard, connect to the air drive Wi-Fi network on another device from which you wish to monitor from.

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Configuring_AirDrive_Forensic_Keylogger%20Pro_USB.PNG)

* Open the settings of the AirDrive. You will be presented with a menu similar to the one below.

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Configuring2_AirDrive_Forensic_Keylogger%20Pro_USB.PNG)

* You may change the access point security so you can give the access point a password from an open network to a WPA2-PSK and give the device a password (also make note of the password).
*  Scroll down to the Key Logging section and set the keyboard layout to be English (UK) rather than US.
* If need be, you can also reset the data log here with the delete log button. 

* Now after changing the settings, see if you can try accessing the keylogger on a different device such as your phone or other desktops so you can monitor what the user us typing. 


## Viewing recorded data

To view recorded data, plug the device in-between the keyboard and USB port, and press the 3-key combination simultaneously (by default K, B, S

* Once keystroke data has been recorded, it may be viewed or downloaded on any personal device equipped with Wi-Fi, such as smartphone, tablet, laptop or desktop computer.
* Each device has a built-in 3-key combination (by default K, B, S). Press these 3 magic keys simultaneously to trigger flash drive mode. 

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/KeyGrabber_Keybord.PNG)


![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/KeyLogger_protection.png)


## Scanning a Keylogger Output File

Below is a text file (log.txt) containing what a data sample from a keylogger output file may look like.

Your task is to scan the recorded data for potentially useful information a hacker would be interested in. 

Try to infer what the context of each piece of data is used for.  

[log.txt](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/Keystroke%20logging%20attacks/log.txt) 

[https://docs.google.com/forms/d/e/1FAIpQLScFbEfwsCB-WjsGxUKjNdSYSF9o3Ec9FEd5WFJeEjQ9B_v-UA/viewform?usp=sf_link]

