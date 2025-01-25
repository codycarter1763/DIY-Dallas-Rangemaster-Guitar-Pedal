# DIY Dallas Rangemaster Guitar Pedal
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
- Added pull down resitors and input capacitor switch
- Pull down resistors added for reduced electric noise and useability with other 
  pedals
- The switching of input capacitors changes the frequency response of the pedal, 
  making the Rangemaster more versitile. This is the same mod used in Tony Iommi of 
  Black Sabbath's Rangemaster pedal 
![NPN Rangemaster With Pull Down Resistors and Fuzz Switch](https://github.com/user-attachments/assets/7ab12ce3-b1fd-4c44-8157-ac07448587ef)

## PNP Dallas Rangemaster Circuit
- Original circuit with PNP Transistors running off of a 9V battery
![PNP Rangemaster](https://github.com/user-attachments/assets/35b2ca86-ea64-477c-9f12-6d42cde43ddf)

## MAX1044 Power Supply Mod
- If wanting to use the PNP circuit with a modern pedal power supply, use this mod to 
  supply clean isolated power needed for this circuit to run properly
  ![MAX1044 Power Supply Mod](https://github.com/user-attachments/assets/54b3af85-1719-47b3-8c6f-930616138a26)
