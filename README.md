# Digital Audio Switching Product Design
#### Client Name: Junaid Alam

## Project Requirements
The circuit will accept a Digital Audio signal coming from a TV (for example) via the TV optical output (Toslink SPDIF). It will then be able to put that audio output to 1 of the 4 Toslink digital audio outputs. The outputs will be controlled by GPIO on the MCU (pushbuttons). The pushbuttons will turn the outputs ON and OFF. The pushbuttons will also control the volume of each output volume up and volume down:
Some core points to consider:
- The receivers are very sensitive for the photo diode, good filtering of the power supply is critical.
- Use a higher voltage to reduce the chance of noise and increase transmission (speed).
- For the transmitter this is also the case just the other way around.  A good supply with lots of local decoupling because switching the optical diode element fast enough and hard enough for the sharp edges generates a lot of electrical noise that can affect other circuits on the same network.
- Power the transmitter from 5V even if the logic levels are 3V can greatly improve reliability.
- It is recommended to use a separate power supply derived off the 5V supply to drive the Toslink as that’s the only way to reach the 96K specification.
- Put some small resistance in series and just route as a microstrip network.  On 2layer FR4, 62mil/1.6mm that's like 50ohms, 33ohms on a 4layer.  But it's not critical.  It just has something there to absorb any reflections.  The clock for SPDIF is embedded in the signal, so no need for anything special for matching trace lengths.
- Suggestion for [switching IC](https://www.analog.com/media/en/technical-documentation/data-sheets/MAX4781-MAX4783.pdf) (not final).

### Concept Diagram
![image](https://github.com/eSpark-Consultants/junaidalam-audioswitch/assets/76909080/e410e988-97c0-4639-99cf-3aef5f5c43f1)
