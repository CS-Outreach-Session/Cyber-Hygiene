# Listening to FM Radio
To begin listening to FM radio we might need to shift one of those large peaks we saw in the graph to the centre. We could do this by changing our centre_freq, but to demonstrate, we can also do this through software instead of tuning the hardware.

To do this we begin with a new block from the math operators called multiply, this block performs a regular math multiplication.  The next block we need is a singal source block from waveform generators, which rather than taking a signal from our HackRF like the osmocom source, we instead are making a synthesised signal from our CPU and we’re going to multiply these 2 signals together to shift the graph along. 

Draw lines from both the osmocom source out and signal source out to the two ins of the multiply block and make a new variable called channel_freq and set the value to be one of the peaks you see on your graph that you want to tune to. I have selected 96.0 million. Now for the frequency of the signal source block we are going to use centrer_freq – channel_freq like so
                                            ![](https://github.com/CS-Outreach-Session/Cyber-Hygiene/blob/main/images/gnuprog_example4.PNG)
