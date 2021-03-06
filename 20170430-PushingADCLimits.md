# 20170430 - ADC

## Objectives

1. Testing the ADC08200
2. Offseting the signal
3. Processing data and FFT'ing
4. Checking the power use of the modules at large
5. Next steps

## 1. Testing the ADC08200

Just testing if we can get the noise if we listen to the Ground

![](/images/ADC08200-Noise.png)

and [getting some info/data](/ADC08200/20170430-ADC08200-FirstAcqs.ipynb)

## 2. Offsetting

The idea is to shift the signal from baseline to an average of 3.3/2V 

![](/offset/offset_good_GSmall.JPG)

Here, it's a bit bad.

Using a __OP37G__.

## 3. Processing the data

### [First acquisitions with the ADC08200](/ADC08200/20170430-ADC08200-FirstAcqs.ipynb)

![](/images/ADC08200silentADC.png)

![](/images/ADC08200silentADCfft.png)

### It should be looking like that:

![](/images/offset_good_GSmall.JPG)

### And when FFT is applied

![](/images/ADC08200piezoFFTed.png)

![](/images/20170422-detailedFFT.png)

## 4. Checking the power use

### First stats

That's 5.1V and ...
* 273 mA with OneEye, Tobo, Goblin, Croaker, Oled
* 290 mA with OneEye, Tobo, Goblin, Croaker, Oled and the [offset module](/offset/)
* 390 mA with all of this + the raspberry

### Using with the raspberry powered outside

A simple piezo plugged onto the pulser

![](/offset/20170430_175050.jpg)

* __Using: 5.1V et 278mA__

### Using a raspberry on the board

![](/offset/20170430_172456.jpg)

* __Using: 5.1V et 418mA__

## 5. Next steps & challenges

__Tomorrow__
* [ ] Update the [motherboard](https://github.com/kelu124/echomods/blob/master/doj/brief_v2.md)
* [ ] Test noise on the sequence for the emulator 
* [x] Play with the VRef - [done, and not so interesting (see Notebook)](/ADC08200/20170501-TestingVref.ipynb)
* [x] Test the enveloppe detection - done, with [Hilbert and BiVi transform](/ADC08200/20170430-ADC08200-FirstAcqs.ipynb)

__Later on__
* [CANCELLED] !! Do a small PCB for the offsetter
    * Offset by 3.3V/2
    * Gain between 0.5 and 2 with a settable potentiometer 
* Check the control of the pulser by the RPi: control sequence through the ADC module
* Check if the speed of ADC acquisition can be higher

