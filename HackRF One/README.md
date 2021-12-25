# HackRF One
The purpose of this activity is to provide a basic understanding of the HackRF One device and the GNU Radio Companion software to demonstrate the process of receiving, broadcasting, retransmitting, and live transmitting signals.

The HackRF One is a wide band software defined radio that is able to receive and transmit a frequency range of 1MHz to 6GHz. 

To program the HackRF One, we use a software known as GNU radio companion which is a front-end graphical user interface that allows us to create python programs simply by using blocks to create flowcharts.

## Installing GNU Radio Companion
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

* If it does not exists create a new system variable, as shown above and select the path from where GNU Radio was installed.
With the variable created. Now click the PATH variable again and check for the following variables:

You can now run GNU Radio Command Prompt, which should be in your windows search bar. The errors should not matter.
Make sure to save GNU radio files to a place such as desktop, rather than in the default bin.




## Setting up the work environment
Before getting started, the HackRF One libraries must be installed on the computer to start using the device
