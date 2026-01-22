## Project Overview:

A Colpitts Oscillator is a circuit capable of producing its own signal with an amplifier and LC Feedback Network. It uses 2 capacitors and an inductor for feedback. In order for the oscillation to sustain itself, the amplifier has to produce a high enough voltage gain to make up for losses in the LC Tank as well as inverting the phase of the signal 180 degrees(makes it able to be further amplified). This circuit is key to many devices such as transmitters and recievers. My Colpitts oscillator uses a Common Emitter Amplifier and 1nf,1nF, 47uH feedback loop which operates at 1MHz. I buffed the output and performed a FFT (Fast Fourier Transform) to analyze the 1MHz signal and made a comparison between the breadboarded version and the protyped version.

## System Architecture, Prototype, and Details:
- Common Emitter Amplifier
-  1nf, 1nf, 47uH (Resonant Frequency 1MHz
![Resume explanation](https://github.com/user-attachments/assets/66734221-39c8-4951-bbdb-06c428d8cef5)
![IMG_8077](https://github.com/user-attachments/assets/97146a0a-adcd-4190-857d-9e357d9db261)
![Resume explanation-3](https://github.com/user-attachments/assets/48581dd7-fa4f-4765-b07b-c5fcf06fa12d)

*Yellow = Output of Tank*

*Blue = Output of Common Emitter Amplifier*



## FFT(Fast Fourier Transform):
- Sampling rate 1 GSa/s, Nyquist Frequency 500 MHz
- 12M Points
- Major spike at 100MHz (Oscillator operating frequency)
- Harmonics Present
- Noise Floor(Thermal, Transistor noise)

Nyquist frequency is 500MHz( Max frequency for accurate capturing) This means the FFT X axis just scales to 0-500MHz, which doesnt effect our data.
- Our operating Frequency is the biggest spike at 100MHz or (1Mhz)
- Harmonics at integer multiples (200MHz, 300MHz, 400Mhz)
- Second biggest spike 400MHz. May be caused by transistor switching or loading effects from oscilloscope measurement probes, components,


![Resume explanation-2](https://github.com/user-attachments/assets/5979b280-c03e-4983-81c6-dbd08b949f12)

## Results
- Oscillator have some drift causing frequency to shift. (Suspecting old capacitors in LC Tank)
- Parasitics (stray capacitance, long wire leads) artificially raised the LC tank Amplitude on the breadboard. (Common Emitter has to work harder to sustain Oscillation
- Loading effects minimized with common emitter buffer controlled loading through 1k Ohm resistor.

*Colpitts Oscillator build on Breadboard*
  ![Resume explanation-4](https://github.com/user-attachments/assets/8e0b4dde-1992-41c6-80ff-901e64bffc1e)

## What I'd Improve
- Use new components
- Design an RF amplifier that takes the oscillator as an input
- Design Oscillator for a higher frequency



  



