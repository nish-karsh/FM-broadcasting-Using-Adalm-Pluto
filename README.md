# FM-broadcasting & FM-Radio Using Adalm Pluto
1. In FM broadcasting, the frequency of the carrier wave is modulated to encode the audio signal that is being transmitted. A radio receiver (in this project, our mobile phone) extracts the original audio sound from the modulated radio signal and reproduces the audio in a loudspeaker.
2. In FM Radio Receiver, music from an existing Radio Station is received through Adalm-Pluto-SDR and processed to get the audio output from the speaker. 


### MATERIALS REQUIRED

1.	Adalm Pluto SDR (along with its USB cable and antennas)
2.	Phone with radio application and earphones (earphones act as receiver antenna)
3. Dipole Antenna with tripod stand 

### SOFTWARES REQUIRED

1.	MATLAB Simulink
2.	Any built-in or installed radio application on your mobile

### SETUP of FM Broadcasting:

#### HARDWARE SETUP:

![image](https://i.postimg.cc/xjzcSZwy/Whats-App-Image-2024-08-17-at-15-12-21-1ebea232.jpg)
* STEP 1: Connect the antennas to the ADALM PLUTO SDR
* STEP 2: Connect the PLUTO SDR to your computer using the USB Cable
* STEP 3: Connect your earphones to your mobile to act as a receiver Antenna and place the phone near your hardware.

The Hardware setup is done.

#### SOFTWARE SETUP:

In case you don’t already have the “Communications Toolbox Support Package for Analog Devices ADALM-Pluto Radio” package in your MATLAB, go to “Get Hardware Support Packages” in the Add-Ons drop box and install and setup the package.

![image](https://user-images.githubusercontent.com/59824729/119100624-c5d47400-ba35-11eb-82c0-c051b479b5ed.png)


* STEP 1: Once the package has been installed and set up, open a new blank model on your Simulink. 
* STEP 2: Add the following blocks and connect them in the same order
1.	“From Multimedia File” block from the Audio Toolbox 
2.	“FM Broadcast Modulator Baseband” 
3.	“Adalm Pluto Radio Transmitter”

* STEP 3:  Browse and select your multimedia or audio file that you want  to transmit in the “From Multimedia File” block 

![image](https://user-images.githubusercontent.com/59824729/119101451-9ffb9f00-ba36-11eb-94a4-1d3b6857051f.png)

* STEP 4: In the block parameters pop-up for FM Broadcast block, make sure the settings are as follows and the stereo audio box is selected.

![image](https://user-images.githubusercontent.com/59824729/119101491-abe76100-ba36-11eb-869f-c76ce2741c0a.png)

* STEP 5: In the pop-up settings for the ADALM PLUTO receiver, make sure that the “Enable output port got underflow indicator” box is deselected. And under the Center Frequency (Hz) choose a frequency that is not available/taken by any radio stations near your area. 



I have chosen the center frequency of 108 MHz (or 108.0e6 Hz). 

![image](https://i.postimg.cc/9MHswrff/image.png)

* STEP 6: Give the stop time as infinity (inf).

![image](https://user-images.githubusercontent.com/59824729/119101671-dd602c80-ba36-11eb-8137-f5681969c965.png)
 
Now the Simulink set-up is done. Let us now look at how we should set up our phone.

##### SETTING UP OUR PHONE

* STEP 1: Go to your built-in radio application or install a FM radio application.
* STEP 2: Select the radio station frequency that you have given in your Simulink, here, 108 MHz

![image](https://i.postimg.cc/x1CQ9JkD/Whats-App-Image-2024-08-17-at-17-13-12-30da5079.jpg)

* STEP 3: Connect your earphones to your phone to act as a receiver antenna. 

### Now that the setup is done, run the Simulink code and then turn on the radio, and we can hear the audio that we had transmitted using your Pluto SDR. 

***** 

### GNU Radio-SETUP of FM Radio Receiving:
![image](https://i.postimg.cc/1RdkfYFC/Screenshot-2024-08-19-145630.png)

