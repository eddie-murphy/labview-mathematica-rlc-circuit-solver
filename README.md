# labview-mathematica-rlc
## LabVIEW 2018/2019 program that solves for the values of each component in a physical Resistor, Inductor, and Capacitor (RLC) circuit by analyzing the frequency response of the circuit.
* Each Call to Mathematica is done by programmatically creating a batch file (that overwrites the previous batch file, unless a new name is specified) that calls on a wolfram script. The wolfram script performs non-linear regression on data saved as a .csv by the labview program. The wolfram script outputs the results in a .csv that is then read back in by labVIEW.
  * This implementation (and therefore this program) was designed to run on Windows 10 , however, I imagine a similar work around could be created for macOS. 
  * LabVIEW contains the ability to perform nonlinear regression, however, I am more familiar with Mathematica's tools
* Included is the main program vi, along with all the other sub vi's. Programs contain comments for understanding. 

## Necessary Equipment: 
* 1 Function Waveform Generator (Agilent 33120A), 
* 2 Digital Multimeters (Agilent 34401A),
* 2 Decade Resistors (General Radio 1443-J),
* 1 Decade Capacitor (General Radio 1419-B),
* 1 Decade Inductor (General Radio 1491-D), 
* 9 Banana cables,
* 2 usb to serial converters,
* 3 serial cables,
* 1 BNC to Banana Cable Converter,
* 3 null modem adapters,
* 1 Windows 10 computer with LabVIEW 2019 (or LabVIEW 2018) and with Mathematica 12

## Drawing of Setup (also located in root directory as *setup.png*)
![setup](https://github.com/eddie-murphy/labview-mathematica-rlc-circuit-solver/blob/master/setup.png)

## Steps to Follow Once you have the Equipment Set Up:
I have created these ranges because with certain configurations the frequency response is either too wide or too peaked to perform timely analysis on. 

1: Choose Capacitor Value:

  * Capacitor Range: (2.7 ≤ C ≤ 1,000) x 10^(-9)  F

2: Choose Inductor Value: 

  * Inductor Range: (0.027 ≤ L ≤10)  H

3: Choose Resistor Value:

  * If L ≤ 0.16 H : 

    * Then (1 < R < 3000)  Ω

  * If (0.16 < L ≤5) H : 

    * Then R > 3000 Ω

  * If L > 5 H : 

    * Then R > 6000 Ω
