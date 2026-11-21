# Eurorack power

This note describes Eurorack power cables and the cables that fit the Workshop System.
The reference for the power bus is the Doepfer A-100 technical page.
The Doepfer pages use the name "A-100", not "Eurorack".

Doepfer technical details: https://www.doepfer.de/a100_man/a100t_e.htm

## Power rails

All modules use +12V, -12V and GND.
Some older modules also use +5V.
The 16-pin bus also has two optional signals: CV and Gate.
Source: https://www.doepfer.de/a100_man/a100t_e.htm

Doepfer gives this caution for the CV and Gate lines on the bus:
"only ONE transmitter for CV and only ONE transmitter for Gate are allowed".
Source: https://www.doepfer.de/a100_man/a100t_e.htm

## Connectors

There are two connector sizes: 16-pin (2 rows of 8) and 10-pin (2 rows of 5).
Each row in the table has two pins with the same signal.
Row 1 is at the red stripe (-12V) end.

| Row | 16-pin | 10-pin |
| --- | --- | --- |
| 1 | -12V | -12V |
| 2 | GND | GND |
| 3 | GND | GND |
| 4 | GND | GND |
| 5 | +12V | +12V |
| 6 | +5V | not present |
| 7 | CV | not present |
| 8 | Gate | not present |

Source: the "bus connectors of A-100 modules" diagram on https://www.doepfer.de/a100_man/a100t_e.htm

The 10-pin connector has the same layout as rows 1 to 5 of the 16-pin connector.
Doepfer says that modules that do not use +5V, CV or Gate "normally use only the 10 pin version".
Source: https://www.doepfer.de/a100_man/a100t_e.htm

The pin pitch is 0.1 inch (2.54 mm).
This value comes from Adafruit, not from Doepfer.
Source: https://learn.adafruit.com/usb-to-eurorack-power-supply/overview

Headers are boxed (keyed) or unboxed (not keyed).
A keyed header accepts the plug in one direction only.
An unboxed header accepts the plug in both directions.
Sources: https://www.noiseengineering.us/blog/power, https://www.doepfer.de/a100z_e.htm

## Orientation

Do not connect a cable before you find the -12V side on both ends.

- The red stripe on the ribbon cable is the -12V wire. Doepfer's rule for the bus is "red strip down".
- Doepfer says that reversed polarity "will result in the module's instant destruction !"
- Some cables have a blue stripe. Cwejman modules put the red stripe on +12V. Read the label on each module.
- Turn off the power before you connect or move a module.

Sources: https://www.doepfer.de/a100_man/a100t_e.htm, https://www.noiseengineering.us/blog/power

## Cable types

| Cable | Use | Examples |
| --- | --- | --- |
| 10-to-16 | Connects a module with a 10-pin header (+12V and -12V only) to a 16-pin bus board. | [Doepfer A-100BM10](https://www.doepfer.de/a100z_e.htm) (20cm), [LMNTL](https://www.perfectcircuit.com/lmntl-eurorack-power-cable-10-to-16-pin.html), [Tiptop Audio](https://www.perfectcircuit.com/tiptop-audio-10-to-16-pin-power-cable.html), [Thonk](https://www.thonk.co.uk/shop/16-16-pin/) (8, 15, 25, 50cm) |
| 16-to-16 | Connects a module that needs +5V, CV or Gate to a 16-pin bus board. | [Doepfer A-100BM16](https://www.doepfer.de/a100z_e.htm) (20cm), [LMNTL](https://www.perfectcircuit.com/lmntl-eurorack-power-cable-16-to-16-pin.html), [Tiptop Audio](https://www.perfectcircuit.com/tiptop-audio-16-to-16-pin-power-cable.html), [Thonk](https://www.thonk.co.uk/shop/16-16-pin/) (8, 17, 30, 50cm, 1m) |
| 10-to-10 | Connects a module to a module (Thonk calls these module-to-module cables). | [Thonk](https://www.thonk.co.uk/shop/16-16-pin/) (17, 30cm) |
| Flying bus | A ribbon cable with a row of power headers. Only one end attaches to the power supply. | [4MS Flying Bus](https://www.perfectcircuit.com/4ms-flying-bus-cable.html) (for 4MS Row Power), [Thonk](https://www.thonk.co.uk/shop/16-16-pin/) (30cm with 7 headers, 60cm with 12 headers) |

On a 10-to-16 cable, align the red stripe on both ends.
Sources: the linked product pages, https://www.noiseengineering.us/blog/power

Perfect Circuit search for power supplies and cables:
https://www.perfectcircuit.com/catalogsearch/result/?q=Eurorack%20power%20supply%20and%20cable
The Perfect Circuit pages block automated reading.
So this note links to single product pages that a web search found.

## Workshop System

The Workshop System has "4 x power headers, one for each PCB".
The four PCBs are VCO, Computer, VCF and Mix.
The headers point out of the back of each module.
Sources: https://www.musicthing.co.uk/Workshop_System_Build_Guide/#understanding-power-headers, https://www.musicthing.co.uk/Workshop_System_Build_Guide/#starting-to-build

The photo in that section shows an unboxed 2x5 (10-pin) header.
The board labels next to the pins are `+`, `GND`, `GND`, `GND`, `-` and `RED>RED`.
This layout agrees with the Doepfer 10-pin connector.
The guide text does not give the pin count.
The photo shows one header, so the header type of the other three PCBs is [value missing].
Photo: https://www.musicthing.co.uk/images/WS_Power_header.jpg

In normal use, the modules connect directly to the PSU board behind the panel.
The Workshop System does not use ribbon cables for power.
Source: https://www.musicthing.co.uk/Workshop_System_Build_Guide/#putting-it-all-together

The PSU board uses USB-C PD power at 15 Volts, about 1.0 amps.
Source: https://www.musicthing.co.uk/Workshop_Quick_Start/#power-supply

### Cables that fit the Workshop System

Use a cable with a 10-pin plug at the module end.

- **10-to-16**: connects one Workshop module to a standard 16-pin bus board.
- **10-to-10**: connects one Workshop module to a 10-pin header.

The headers are unboxed, so they do not prevent a reversed plug.
Put the red stripe on the side with the `-` and `RED>RED` labels.

Use a cable to find a short circuit.
The Build Guide says: "If you have a eurorack power cable, you can power up each module individually".
Source: https://www.musicthing.co.uk/Workshop_System_Build_Guide/#troubleshooting

Use cables to put the Workshop System in a Eurorack case.
The product FAQ says that you can remove the back panel PSU and put the system in a Euro case.
The system is 42hp and needs "around 250mA".
The split of this current between +12V and -12V is [value missing].
You need one cable for each of the 4 PCBs.
Source: https://www.musicthing.co.uk/workshopsystem/

## Sources

- Doepfer A-100 technical details: https://www.doepfer.de/a100_man/a100t_e.htm
- Doepfer A-100 accessories (bus boards, cables): https://www.doepfer.de/a100z_e.htm
- Noise Engineering, "How to plug in a module" (not official Music Thing): https://www.noiseengineering.us/blog/power
- Adafruit, USB to Eurorack Power Supply (not official Music Thing): https://learn.adafruit.com/usb-to-eurorack-power-supply/overview
- Thonk power cables (not official Music Thing): https://www.thonk.co.uk/shop/16-16-pin/
- Perfect Circuit search (not official Music Thing): https://www.perfectcircuit.com/catalogsearch/result/?q=Eurorack%20power%20supply%20and%20cable
- Workshop System Build Guide: https://www.musicthing.co.uk/Workshop_System_Build_Guide/
- Workshop Quick Start: https://www.musicthing.co.uk/Workshop_Quick_Start/
- Workshop System product page: https://www.musicthing.co.uk/workshopsystem/
