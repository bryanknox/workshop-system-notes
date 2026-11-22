# VCO module tests

Physical Module: VCO

Sources:

- Build Guide: https://www.musicthing.co.uk/Workshop_System_Build_Guide/
- Quick Start: https://www.musicthing.co.uk/Workshop_Quick_Start/
- Calibration: https://www.musicthing.co.uk/Workshop_System_Calibration/

This note answers one question: can a builder test the VCO module before the other modules are complete?

## Summary

The official pages give no test for the VCO module alone.
The Build Guide says that a Eurorack power cable can supply power to one module at a time.
The official sound test uses the Mix module.
A multimeter gives a partial test without the Mix module.
See [Multimeter test without the Mix module (not official)](#multimeter-test-without-the-mix-module-not-official).

## What the official pages state

### Build sequence

https://www.musicthing.co.uk/Workshop_System_Build_Guide/#starting-to-build

The Build Guide says "Build your boards in this order:" and lists four boards:

1. VCO / Oscillator
2. Computer
3. VCF / Filters
4. Mix

The "Building the VCO" section gives assembly steps only.
It has no step to connect power and no test step.

### When the guide does the test

https://www.musicthing.co.uk/Workshop_System_Build_Guide/#putting-it-all-together

The test is in the "Putting it all together" section, after the four boards are complete.
The guide says "loosely assemble and test the board before putting on all the nuts and knobs".
The guide then says "Connect power and test the board."
The guide refers to the Quick Start for the test details.

### Power

The system uses USB-C PD power at 15 Volts.<br>
https://www.musicthing.co.uk/Workshop_Quick_Start/#power-supply

The PSU has four amber LEDs that show if the power is correct.<br>
https://www.musicthing.co.uk/Workshop_System_Build_Guide/#assemble-the-power-supply

The guide says "There are 4 x power headers, one for each PCB".
The power headers come out of the back of each module.<br>
https://www.musicthing.co.uk/Workshop_System_Build_Guide/#understanding-power-headers

### Power for one module

https://www.musicthing.co.uk/Workshop_System_Build_Guide/#troubleshooting

The guide gives this procedure only to find a fault.
The symptom is a whining noise from the PSU.
The guide says "If you have a eurorack power cable, you can power up each module individually, to identify the culprit."

### Official oscillator test

https://www.musicthing.co.uk/Workshop_Quick_Start/#your-first-patch

1. Connect the power and set the switch on the back to on.
2. Connect headphones or a speaker to the headphone out.
3. Turn the big volume knob down.
4. "Plug one cable from the Oscillator, the top sine wave output (↓) to Mix input 1 (↑)."
5. Slowly turn up the headphone volume knob until you hear a sound.
6. "Wiggle the top knob on the oscillator and the sound should wiggle".

This test uses Mix input 1 and the headphone out, which are on the Mix module.

### Calibration

https://www.musicthing.co.uk/Workshop_System_Calibration/#how-to-calibrate-the-sinesquare-oscillators

The Build Guide says to calibrate the system after the build is complete.
Oscillator calibration is necessary only with external equipment, for example a CV keyboard or a sequencer.
The calibration needs a tuner and a small flat head screwdriver.

### Warning

https://www.musicthing.co.uk/Workshop_System_Build_Guide/#troubleshooting

The guide says "Do not poke anything metal onto powered PCBs".
The guide also says "If you try to test the boards with multimeter probes while the system is powered up, there is a significant risk you'll destroy components and/or the power supply board."

## Inferences (not stated on the official pages)

The official pages do not give the statements in this section.
No test confirms them.

- A Eurorack power supply and cable can supply power to a completed VCO board alone.
- An oscilloscope or an external amplifier can then show or play an oscillator output.
- The oscillator signal is possibly much higher than line level. Keep the amplifier volume low.
- If you build the Mix board second, the official oscillator test is possible earlier. This is not the sequence in the Build Guide.
- The Build Guide does not permit or prohibit operation of the PSU with only the VCO board connected.

## Multimeter test without the Mix module (not official)

This procedure comes from general electronics practice, not from Music Thing.
No test confirms it on a Workshop System VCO.
The official pages give no frequency range and no output voltage level for the oscillators.
The Quick Start says only "Two wide range, volt per octave analogue oscillators."<br>
https://www.musicthing.co.uk/Workshop_Quick_Start/

### Before you connect power

Do these steps on a board that has no power.
Metal probes are safe on a board without power.

1. Examine the solder joints for "blobby or missing" joints, as the Build Guide says.<br>
   https://www.musicthing.co.uk/Workshop_System_Build_Guide/
2. Set the multimeter to resistance (ohms).
3. Measure between the `+` and `GND` pins of the 10-pin power header.
4. Measure between the `-` and `GND` pins.
5. Measure between the `+` and `-` pins.

A reading near 0 ohms shows a short circuit.
Do not connect power if you find a short circuit.

### Power

Use a Eurorack power supply and a 10-pin power cable.
Put the red stripe on the side with the `-` and `RED>RED` labels.
See [Eurorack power](../Eurorack/eurorack-power.md).

### Connect the meter through a patch cable

Do not touch the powered board with the meter probes.
Connect the meter to the free end of a patch cable.
Then no metal touches the board.

1. Disconnect the power.
2. Plug a 3.5 mm patch cable into the top sine output (↓).
3. Attach crocodile clips to the meter leads.
4. Clip the red lead to the tip of the free plug. The tip carries the signal.
5. Clip the black lead to the sleeve of the free plug. The sleeve is ground.
6. Connect the power.

Do not let the tip touch the sleeve.
This connects the output to ground.
The output protection of the VCO is [value missing], for example a series resistor.

A digital multimeter has a high input impedance, typically about 10 MΩ.
So the meter takes almost no current from the output.

### Read the meter

- **Frequency (Hz) mode.** Use this mode if the meter has it. Turn the top oscillator knob. The frequency reading changes if the oscillator operates.
- **AC volts mode.** A reading above 0 V shows that a signal is present. Many meters are accurate only at low audio frequencies. Compare the readings, but do not trust the values.
- **DC volts mode.** The meter shows the average voltage. For a waveform centered on 0 V, the average is near 0 V. At a very low frequency, the reading possibly moves up and down. The lowest frequency of the oscillator is [value missing].

Do the same steps on the square output and on the second oscillator.

### Limits

A multimeter does not show these items:

- The shape of the waveform
- The tuning accuracy
- The operation of Ring Mod, Stompbox, and Stereo In

For these items, use an oscilloscope or an external amplifier at low volume.
Or do the official test when the Mix module is complete.

## Missing data

- Pin count of the VCO power header: [value missing]
- Polarity or keying of the VCO power header: [value missing]
- Official test for Stereo In: [value missing]
- Official test for Ring Mod: [value missing]
- Official test for Stompbox: [value missing]
- Output voltage level of the sine and square outputs: [value missing]
- Frequency range of the oscillators: [value missing]
- Output protection of the oscillator outputs: [value missing]
