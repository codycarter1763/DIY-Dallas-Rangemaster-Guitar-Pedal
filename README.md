# DIY Dallas Rangemaster Guitar Pedal
![IMG_4138](https://github.com/user-attachments/assets/5cd5cbef-1e8d-4e6e-90aa-cd2f16a68fe5)

<br/>
<h1>About</h1>
 <h6> 
   &emsp;    The Dallas Rangemaster Treble Booster pedal was a pedal first produced in 1965 by Dallas Musical Ltd. The intended purpose of this pedal is to add treble back to amps popular amps the time including the Vox AC30 or Marshall JTM45 that is lost due to overdrive or humbuckers. The result was a characteristic distortion and color change that suited the likes of Black Sabbath, Eric Clapton, Ritchie Blackmore, and countless more guitarists through the decades. 
<br/>   
<br/> 
   &emsp;    The Dallas Rangemaster was originally designed with germanium PNP transistors because that was most used at the time. Though these germaniums are sensitive to heat, humidity, and other issues that made the pedal sound different or not work altogether. Also, the original Dallas Rangemaster is considered one of the rarest pedals due to high demand and the very limited production. As a result, many modern clones were made of this pedal with more modern components that are cheaper and more reliable. Germanium tends to have a warmer rounder tone with less aggressive fuzz, with silicon having a more aggressive fuzz sound with higher gain. Both transistor materials have their pros and cons and are sought after for a certain desired tone, though may require slightly different circuits for best performance.
<br/>
<br/>
<p align="left">
  <img src="https://github.com/user-attachments/assets/313209ba-0c4c-4134-864c-9760012ef0a2" width="40%" height="40%" alt="Left Image">
  
  <img src="https://github.com/user-attachments/assets/9181d1ac-e5f4-493a-a49b-45c346b536e8" width="48%" height="48%" alt="Right Image">
</p>

 &emsp;  <h6>

<h1>Quick Thanks To PCBWay</h1>
<h6> &emsp;My project was gladly sponsored by PCBWay. PCBWay has provided professional solutions to students and electronics enthusiasts, and I believe that their sponsorship would be essential to easy and reliable construction of Dallas Rangemaster PCBs. Such boards will allow for removability in case of failure or modification. It’s an honor to share the results with the PCBWay community and contribute our project to their platform.  <br>
 <br><h6>

![image](https://github.com/user-attachments/assets/3253581c-9c10-4329-aa81-215169151ca1)



 <h1>Parts List</h1>
 <h6> &emsp;Originally the Dallas Rangemaster incorporated PNP germanium transistors. This was because PNP germanium transistors were easier to make consistently and didn’t have any major leakage current like their NPN germanium counterpart. PNP was not an issue back then, since the pedal ran off a 9V battery. The problem comes from the standard center negative power supplies used for guitar pedals not being able to work with PNP without a major redesign of the circuit. This issue was fixed with NPN transistors being put in the circuit, making no difference sonically.
<br/>
<br/>
 &emsp; The design implemented in this repository is made with silicon NPN transistors as I wouldn’t have to worry about inconsistent germanium transistors and anything power supply wise to be able to run the pedal. If you swapped power polarity on a PNP circuit to work with common pedal power supplies, it causes more noise, hiss, motorboating, and more issues. In the circuit design section there will be a additional MAX1044 circuit listed that will provide clean negative ground power for use with the original circuit.<h6>

## Parts List:
This list is for the design I am going with for this pedal with pull down resistors, fuzz switch, and NPN silicon transistors

- 1 BC109C NPN Transistor (BC108C, BC109, BC183L, BC209C, 2n2222, 2n3904 are also commonly used)
- 2 5nF capacitor
- 1 10nF capacitor
- 2 47µF electrolytic capacitors
- 1 470KΩ resistor
- 1 68kΩ resistor
- 1 3.9KΩ resistor
- 2 1MΩ resitors
- 1 10kΩ Logarithmic Potentiometer
- 2 1/4" female guitar jacks

# Circuit Diagrams and Common Mods
## NPN Dallas Rangemaster 
# Original circuit with NPN transistors
![NPN Rangemaster Photo Schematic](https://github.com/user-attachments/assets/274c27b1-f66e-4340-8639-237044abe555)

## NPN Dallas Rangemaster with Pull Down Resistors and Fuzz Switch
- Added pull down resistors and input capacitor switch
- Pull down resistors added for reduced electric noise and useability with other 
  pedals
- The switching of input capacitors changes the frequency response of the pedal, 
  making the Rangemaster more versatile. This is the same mod used in Tony Iommi of 
  Black Sabbath's Rangemaster pedal 
![NPN Rangemaster With Pull Down Resistors and Fuzz Switch](https://github.com/user-attachments/assets/7ab12ce3-b1fd-4c44-8157-ac07448587ef)

## PNP Dallas Rangemaster Circuit
- Original circuit with PNP Transistors running off of a 9V battery
![PNP Rangemaster](https://github.com/user-attachments/assets/35b2ca86-ea64-477c-9f12-6d42cde43ddf)

## MAX1044 Power Supply Mod
- If wanting to use the PNP circuit with a modern pedal power supply, use this mod to 
  supply clean isolated power needed for this circuit to run properly
  <br/>
  ![MAX1044 Power Supply Mod](https://github.com/user-attachments/assets/54b3af85-1719-47b3-8c6f-930616138a26)

# Circuit Analysis
For my analysis, I calculated these values based on the NPN version of the Dallas Rangemaster. The PNP version of this circuit will have different values but will effectively produce a similar output. <br/>

## Input Impedance 
For input impedance, consider the voltage divider into the base of the transistor and transistor impedance. <br/>
R1 // 68k // NPN Impedance (40,625) = 24kΩ input impedance
<br/>
<br/>
NPN Impedance calculated using <br/>
rπ = β / gm where β = 200 (BC109) and gm = Icollector / Vthermal <br/>
<br/>
To calculate Ic, <br/>
Vb = Vin(R2 / R2 + R1) = 9(68k / 470k + 68k) = 1.2V <br/>
<br/>
With silicon transistors, Vbe = 0.7 <br/>
So Ve = Vb - Vbe = 1.2 - 0.7 = 0.5V <br/>
Ie = Ve / Re = 0.5 / 3.9k = 128μA which approximetly equals Ic <br/>
<br/>
With Ic, NPN impedance can finally be calculated below <br/>
rπ = β / gm = β(Vt) / Ic = 0.026(200) / 128μA = 40,625Ω
<br/>
<br/> 
Such low input impedance loads the guitar pickups and draws more current from the guitar pickups. This leads to less sensitivity, more compression, and bass frequencies attenuated. Hence, where the Dallas Rangemaster gets its signiture treble boosted sound.
<br/>
<br/> 
## Frequency Response and Gain
The frequency response is influenced with three different capacitor resistor networks, with the input network being the one that affects the tone the most.
<br/> 
<br/> 
### Input Network C2
Fc = 1 / 2π(C2)(Input Impedance) = 1 / 2π(5nF)(24000) = 1326Hz
<br/> 
### Emitter Network C3
Fc = 1 / 2π(C3)(R3) = 1 / 2π(47μ)(3.9k) = 0.86Hz
<br/> 
### Output Network C6
Fc = 1 / 2π(C6)(1Meg Load) = 1 / 2π(10nF)(1Meg) = 15.9Hz
<br/> 
### Gain
At full volume, the Dallas Rangemaster with BC109 silicon transistors has a max gain of about 34dB
![Dallas Rangemaster Gain Response](https://github.com/user-attachments/assets/b34e59cd-6f28-4b85-b234-595f3b7e4ea3)
<br/> 
<br/> 
## Output Waveform
Below is the output waveform of the Dallas Rangemaster at various volume levels. Assymetrical clipping is observed through the unequal waveforms peak to peak, such clipping leads to a more dynamic, harmonic rich, and presence. 
<br/> 
Interestingly enough, if a PNP transistor was used instead of an NPN visualized below, the waveforms would be flipped where the upper half is clipped and the bottom is sine.
![Dallas Rangemaster Output Waveform](https://github.com/user-attachments/assets/b4437083-9850-4b0a-a525-fd96129d74d1)

# Effect of Mods
## Input Capacitor Switch
A common mod used by Tony Iommi of Black Sabbath is to add a switch to add capacitors in parallel to the 5nF capacitor. This effectively allows more bass to enter the amplifier and leads to a warmer tone similar to a fuzz pedal depending on components. 
<br/> 
As shown below comparing three different capacitor values, you can see the varying response.
### 5nF
1 / 2π(5nF)(24000) = 1326Hz
<br/> 
### 10nF
1 / 2π(10nF)(24000) = 663Hz
<br/> 
### 15nF
1 / 2π(15nF)(24000) = 442Hz
<br/> 
![Dallas Rangemaster Input Capacitor Mod](https://github.com/user-attachments/assets/3dd741f9-918b-4cd2-a2e0-4d43c38e1190)

# Circuit Board Design
- Fully rendered 3D model of the circuit board to be installed in the Rangemaster pedal
- Check in the file storage above for the attached gerber files for reproduction

![Dallas Rangemaster NPN v2](https://github.com/user-attachments/assets/dd32d197-6259-4e2d-a18c-268e5f16a3e6) 


# Closing Remarks
As you can see, the Rangemaster's iconic tone can be created and modified with a very simple circuit without paying a huge premium for an original model. There are countless more mods out there on the internet done by different companies and guitarists alike to add something new to it's sound. As I test and discover new mods, I will update the repository as nessesary.
