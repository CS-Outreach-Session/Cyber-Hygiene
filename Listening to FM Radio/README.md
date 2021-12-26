# Listening to FM Radio
To begin listening to FM radio we might need to shift one of those large peaks we saw in the graph to the centre. We could do this by changing our centre_freq, but to demonstrate, we can also do this through software instead of tuning the hardware.

To do this we begin with a new block from the math operators called multiply, this block performs a regular math multiplication.  The next block we need is a singal source block from waveform generators, which rather than taking a signal from our HackRF like the osmocom source, we instead are making a synthesised signal from our CPU and we’re going to multiply these 2 signals together to shift the graph along. 

Draw lines from both the osmocom source out and signal source out to the two ins of the multiply block and make a new variable called channel_freq and set the value to be one of the peaks you see on your graph that you want to tune to. I have selected 96.0 million. Now for the frequency of the signal source block we are going to use centrer_freq – channel_freq like so.

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example4.PNG)

Now copy and paste the frequency sink block we had ealier and send the out of the multiply into the in of the new frequency sink, but change the centre frequency of this new sink to be channel_freq variable we created:

 ![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example5.PNG)

Now if we execute this script, we will have two graphs, with the bottom graph being our unshifted graph and the top being our new shifted graph. 
To listen to FM radio, we’ll need to demodulate this digital signal and turn it into an audio signal. First, we need to filter this. Under filters drag a new low pass filter onto the canvas connecting the out from our multiply block to the in of the low pass filter. 

Currently we’re picking up a lot more bandwidth than we need, as we’re picking up multiple radio stations and we want just want one. So create a new variable called channel_width and set the value to be 200e3 or 200 kilohertz – the width of an fm radio station. Set the decimation of the low pass filter to be samp_rate/channel_width, the cutoff freq to be 75e3 and the transition width to be 25e3.

This will produce an error as this particular block only knows how to decimate an integer number (aka a whole number). We can restrict to only integer values by putting it into an int function like so: int(samp_rate/channel_width): 

 ![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example6.PNG)

We’ve just changed the sample_rate in our filter and we now need to do that again. So we want to connect our filter to a resampler, which can be found under resampler -> rational resample. Set the interpolation to be 12 and the decimation to be 5. This is because our low pass filter could only handle integer numbers and we need to change it back to be rational relation like so: 

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example7.PNG)
                                       
Now to add the demodulator. The demodulator is the block that actually turns the digital signal we’re receiving from our GNU radio to an audio signal we can listen to. With this we want the WBFM receive block which can be found under Modulators. Connect the rational resample out to the in of the WBFM receive (wide-band-fm). You may notice the in of the WBFM is blue like the other blocks, but the out of the WBFM receive is orange, signifying that this is accepting a digital signal and turning it to an audio signal. Set the quadrature rate to be 480e3 and the audio decimation to be 10 like so:

 ![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example8.PNG)
 
Next we want an Audio sink, which can be found under Audio, which we connect to our WBFM receive. We then want to change the sample rate to be 48 thousand or 48 KHz.

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example9.PNG)

Our flow graph should now produce audio. Before running however, we only really need one of our graphs to be displayed at this point. We could delete the graph, but in case we want to see it again in the future we can instead just right click one of our frequency sinks and select disable, like so: 

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example10.PNG)

At this point if you run the program, you should be able to hear a radio station. If not, you can try changing around your centre_freq or the frequency in your signal source block, it depends on what FM frequencies are strongest in your area. I was able to hear audio with a centre_freq of 98M and a signal source frequency of 1.4M but again, these will vary depending on your area. 

If you’re hearing audio, but also getting a lot of static, try adjusting the antenna a bit on your HackRF or slightly changing frequency. It can also help to follow the next step. 

We can also try adjusting the audio by adding in a GUI widget to our program that will allow us to change the volume of our audio. To do this we first need to add a multiply between our WBFM receive and audio sink. This time using a multiply constant from the math operators. 

You will notice that we currently have a type mismatch, as the multiply constant block wants a digital signal, not an audio signal. We can fix this by changing the IO type to a float. This allows us to connect the WBFM Receive out to the multiply constant in and the out of the multiply to the audio sink in.

Now we need to add in our GUI element. Which we will find in GUI Widgets -> QT and GUI Range. Call the slider audio_gain. Set the default to be 1, the maximum to be 10 and the step to either be 0.25 or 0.5. We then need to change the multiply constant by changing its constant to audio_gain like so:

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example11.PNG)

The final flow diagram should look something like this:

![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example12.PNG)

Feel free to now create your own payloads for any of the devices. 


