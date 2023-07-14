# Precision Voltage-Controlled Oscillator (VCO)

This circuit is a precision voltage-controlled oscillator (VCO), where the frequency of oscillation is determined by a control voltage. It consists of an integrator and a Schmitt trigger.

### Integrator
The first op-amp in the circuit acts as an integrator. The control voltage is divided using a voltage divider and applied to the positive input of the op-amp. The op-amp strives to keep its negative input at the same voltage level. This requires a current to flow through a resistor to maintain a specific voltage drop.

When a switch, such as a MOSFET, is on, the current from the resistor passes through the switch. Another resistor, connected in parallel with the switch, has a different resistance but the same voltage drop. As a result, it carries a different amount of current. This additional current either charges or discharges a capacitor, depending on the state of the switch. The integrator adjusts its output voltage to accommodate this current flow, resulting in a steadily rising or falling output voltage.

### Schmitt Trigger
The second op-amp in the circuit functions as a Schmitt trigger. It receives the output from the integrator as its input. The Schmitt trigger compares the input voltage with two threshold levels. When the input voltage rises above the upper threshold, the output switches to a high state. Conversely, when the input voltage falls below the lower threshold, the output switches to a low state. This behavior generates a square wave output.

The square wave output from the Schmitt trigger is connected to the switch (e.g., MOSFET) in the circuit. The switch controls the charging and discharging of the capacitor in the integrator circuit. As the square wave switches between its high and low states, it causes the integrator to adjust its output voltage accordingly, resulting in the generation of a triangle wave.



<!-- # aoe-precision-vco
Art of Electronics (AOE) Precision VCO

This circuit is based off of an AOE (Art of Electronics, 3rd Edition) circuit example found on page 267 (Figure 4.83). This circuit outputs triangle and square waves with frequencies equal to 200 * Vin Hz where Vin is from 0 to 2*Vref. In this circuit Vref is 5 V so we have a frequency range of 0 to 2 kHz -->
