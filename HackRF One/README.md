# HackRF One
The purpose of this activity is to provide a basic understanding of the HackRF One device and the GNU Radio Companion software to demonstrate the process of receiving, broadcasting, retransmitting, and live transmitting signals.

The HackRF One is a wide band software defined radio that is able to receive and transmit a frequency range of 1MHz to 6GHz. 

To program the HackRF One, we use a software known as GNU radio companion which is a front-end graphical user interface that allows us to create python programs simply by using blocks to create flowcharts.

## Installing GNU Radio Companion and Setting up the work environment

Begin by downloading the [zip file](https://drive.google.com/file/d/1E-fl3C55wpAZyqESjt1S5UyDY5Q_1sy2/view) for gnu radio components and extract the folder. Placed the extracted folder in the C:drive and install the following packages in the gnu folder.

* vc_redist.x86 – double click file and follow the installer. 
* python-2.7.15.amd64 – double click and follow the installer, probably should install for all users.

At this point we need to check our environment variables. In file browser, right click ‘This PC’. Properties. Advanced System Settings. Environment Variables. Under System Variables. Double click the ‘Path’ and check for the following two paths:

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnu_pathh.PNG)

If they do not exist, simply create them manually by selecting new and typing the path as above, make sure to change the C:\ drive to the same drive you installed Python27 as indicated above.

* Next, download get-pip.py from the webpage, under the section ‘installing with get-pip.py’, follow the link and place the file on the desktop: Installation - pip documentation v21.0 (pypa.io)
* Open up the command prompt from the windows menu, check python is working by typing: python
*	Now change your current directory to desktop with: cd Desktop
*	Now type: python get-pip.py

* After pip has installed, we can continue to install gnu components. Still in the command prompt, we want to change directory to the gnuradio_components folder. Type cd .. to go back from the desktop directory and navigate to the gnuradio_components folder by following the file path using the cd command.
* To install the components type in the command prompt we will use: pip install filename (best to copy and paste the exact file names) in the following order:
* pip install lxml-3.5.0-cp27-cp27m-win_amd64.Release.whl
* pip install numpy-1.10.4-cp27-cp27m-win_amd64.ReleaseDLL.whl
* pip install PyQt4-4.11.4-cp27-cp27m-win_amd64.whl

* Our next install is done by doubling clicking: PyQwt-5.2.1.win-amd64.ReleaseDLL and following the wizard.

* Return to the command prompt and install the following 3:

* pip install Cheetah-2.4.4-cp27-cp27m-win_amd64.ReleaseDLL.whl
* pip install PyOpenGL-3.1.0-py2-none-any.whl
* pip install pygtk-2.22.0-cp27-none-win_amd64.whl

* gtk2-runtime-2.24.10-2012-10-10-ash is installed by doubling clicking the file and doing a normal installation.

* pip install wx-3.0-cp27-none-win_amd64.ReleaseDLL.whl

* wxPython-common-3.0.2.0.win-amd64.ReleaseDLL is installed by doubling clicking the file and doing a normal installation.

* Double click uhd_3.9.6-release_x64_VS2015. Again, probably should install for all users.

* Now to download GNU Radio from the following link and execute the file to install. www.gcndevelopment.com/gnuradio/downloads.htm

* Finally, we need to check the environment variables again. In file browser, right click ‘This PC’. Properties -> Advanced System Settings. Under System Variables, last of all, under system variables there should be the following path: as indicated in the following Figure:

 ![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnu_path2.PNG)

You can now run GNU Radio Command Prompt, which should be in your windows search bar. The errors should not matter.
Make sure to save GNU radio files to a place such as desktop, rather than in the default bin.

## Hardware Setup
* To begin, we will need the HackRF itself, the micro-USB to USB cable and the antenna.

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Hack_RF.PNG)

* Screw the antenna onto the screw labelled antenna and on the opposite end plug the micro-USB in and connect the USB port to your computer. 
* To check that the device is working, open a command prompt/terminal window. Type in the window ‘hackrf_info’ as shown below. This will let you know that the computer is seeing the HackRF board as well as give you some information such as the serial number of your board, what firmware version you are running etc. You will also see 4 LED lights on the side of the HackRF board next to the antenna which will be 3v3 = green, 1v8 = orange, RF = red and USB = green. This let’s us know that our board is running and we are good to begin coding.

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/Hack_RF_test.PNG)


## Visualising FM Radio using HackRF One

To begin your first HackRF program, open GNU radio companion. You will be presented with mostly a blank page and these two blocks as indicated in the Figure below: 

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnu_radio_companion.PNG)

The options block gives us information about the program. The variable block is something that will come into play later. For now, you will notice that the options block is currently highlighted in red. A block being coloured red is GNU’s way of telling us that there is an error with our code, and it will not run – in this case the issue is our program doesn’t have an ID. 

Double click the options block and you will be presented with A menu. Simply give the program an ID such as ‘Fmradio’ making sure to capitalise the first letter like so:

Now save the program to your file space or preferably the desktop.

Now to start programming we need to grab our first block. On the right-hand side there will be a large list of categories, near the bottom expand the OsmoSDR category and drag over an osmocom Source block.  An osmocom source is an extraction block that allows us to communicate with different hardware devices for software radio. It being a ‘Source’ block means it is producing a signal in this case a digital signal (a stream of numbers) which will be indicated later on, when different signals come into play, by it being coloured blue. 
![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnu_Properties_option.PNG)

For now, however, we need to grab our next block which is under instrumentation -> QT and we want a QT GUI Frequency Sink. Once again drag it over to the canvas. As a GUI block (graphical user interface) this allows us to visualise the frequency components from our signal. 
We now need to connect these two together by dragging from the out of the osmocom source to the in of the QT frequency sink. Which will satisfy the error of our osmocom source as it now has somewhere to go. At this point our program should look similar to this: 

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example.png)

Now we need to change our sample rate. This is where the variable block comes into play. A variable block allows us to have a value we can always reference, so if we ever need to change that value we only have to change it in one place. Under our variable block we need to change the same_rate. 32k isn’t very many so we’ll change that to 10 million. To do this double click or right click properties of the variable and in the value box we can type 10 million which we can do easily by typing 10e6 to denote 10 with 6 zeroes (10x10 to the 6th power):

You will notice that now under our osmocom source block that the sample rate has also changed to be 10 million. If you double click on the osmocom source you will notice that under sample rate rather than there being a specific value it shows samp_rate which is referring to the variable block with the ID samp_rate. 
While in the properties of our osmocom source block we also can change the Ch0: Frequency to 97.9e6 to be closer to the middle of the FM broadcast range. We also want to change the RF Gain to 0.
In our frequency Sink properties we want to turn averaging on to medium to make it easier to see radio stations individually in the graph. 
At this point we have a functioning program that will visualise the FM radio signals in our area. Make sure to save the file.
We can now use the play button to execute and compile our program. To stop the program we should use the stop button to stop running the program safely so the HackRF is clean. 

By running our program our current output should look like the diagram below. The major peaks we see are FM radio stations that our HackRF is seeing with the middle 0 being our 97.9 million frequency. 

[](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example2.PNG)

To make the 0 on the graph display 97.9 million, we could change the centre frequency of our frequency sink, but instead I’m going to create a new variable for whenever we need to refer to 97.9 million. To do this I can copy and paste our other samp_rate variable, rename it to centre_freq and give it a value of 97.9e6. Now under the frequency sink block, we can change the centre frequency to be the ID of our new variable, in this case centre_freq like so:

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example3.PNG)

We should also go back to our osmocom Source block and change the CH0: frequency to instead refer to centre_freq, so whenever we want to change our centre_freq we only need to change one variable rather than several, making it less likely for us to have an error in the future. 

