# Intracellular Amplifier

All you need to build is the head stage in Figure 2 of the report for testing, and basic operation.
The design files were not loaded to our server. The Author is copied to see if he still has a copy.

[Bruce R. Land](mailto:bruce.land@cornell.edu), Sr. Lecturer, ECE
214 Phillips Hall GPS: 42.444781, -76.482163

http://people.ece.cornell.edu/land/


From: [Yu Gan](mailto:yg477@cornell.edu)

Resting potentials are about 0 to 100
millivolts, and the cell impedance can be as high as 10Mega-Ohms, so to observe these
signals better, we want to build a device to buffer the very small current from the cell
and to amplify those signals.

## Specific Issues
For measuring the membrane potential, we need to connect the measuring electrode to
an amplifier to amplify the potential. However, there are many constraints.
Neuronal cells are very small. Usually, they are only a few micrometers in diameter,
usually around 1 to 60 micrometers (“Neuron electrophysiology data values,” n.d.). This
means that they imply a high source impedance for the op-amp. Therefore the amplifier
must deal with limited bandwidth and noise. In order to deal with this, the designed
circuit needs to have a negative capacitance bootstrap system to null the source
capacitance to get better performance. In order to send the stimulus (pulse) signal to
the cell and test its behavior, the circuit must be able to inject current through the
electrode. This injected pulse will be then measured with the electrode and be amplified
by the amplifier, therefore, a voltage cancellation system needs to be included in the
system to cancel out the injected pulse.

## Approach
Since the cell has a high source impedance, the front-stage amplifier we pick needs to
have a high input impedance. This ensures the maximum amount of voltage can be
transferred to the amplifier. In order to cancel out the input capacitance and get better
performance, we attached a feedback system onto the op-amp to null the input
capacitance. The feedback system is connected to a potentiometer. The user can
change the feedback capacitance by adjusting the potentiometer and observe the
desired output signals with faster rise time. Since we are injecting current into the cell,
we want to cancel out the voltage artifact. Therefore a pulse cancellation stage (op-amp
adder) is implemented to cancel out the injected current.
We divided the project into three parts:
The first part would be the design and implementation of the front-stage of the amplifier.
The front-stage of the amplifier is going to be a small PCB with surface mounted
components for minimizing space.
The second part would be setting up the back-stage, connecting the whole system, and
testing it in the ECE lab. The back-stage will be a bigger PCB board with through-hole
components. Then the back-stage will be connected with the front-stage and tested with
the simulated cell in the ECE lab. If the circuit functions properly, then we might proceed to the packaging part. If the circuit is not functioning correctly, then we will have to
debug the circuit and fix it.
The third part would be packaging and testing the circuit in the biology lab. The
front-stage will be packed into a small box and connected to an electrode mounted on a
clamp stand for stability. It will also have connections to the back-stage PCB packed in
a surface-mount box with analog user controls. The whole system will then be delivered
to the bio lab and tested with the real membrane cell.

## Schematics

land_meng-complete-schematic




:::{figure-md} land_meng-fig2-front-stage
:class: figure

<img src='/images/land_meng-fig2-front-stage.png' width="300" alt='fishy'>


Figure 2. Schematic of front-stage circuit
The op-amp u1 is connected to the electrode (Vin on the schematic). Two resistors with
10KOhm and 2.5KOhm make the gain of the op-amp equal to 5. There is a feedback
resistor R5 on the top connecting to the pulse injecting system, and a negative
capacitance bootstrap system. The bootstrap system consists of resistors R3 and R4, a
potentiometer of 10KOhm, and a positive feedback capacitor of 10pF. By changing the
value of the potentiometer, we can null the input capacitance and hence improve the
rise time of the signal. For minimizing space, we only placed the feedback capacitor on the front-stage PCB. The two resistors and the connection to the potentiometer are
placed on the back-stage PCB.
:::

:::{figure-md} land_meng-fig3-pulse-injection
:class: figure

<img src='/images/land_meng-fig3-pulse-injection.png' width="300" alt='fishy'>

Figure 3. Pulse injection system
A clamping circuit (two diodes) is connected at the input for limiting the input voltage.
The input pulse is connected to a low pass filter and sent to the front end.
:::

land_meng-fig4-pulse-cancellation.png
The 2KOhm potentiometer is connected to the output of the low pass filter for the input
pulse. The 50KOhm resistor is connected to the output of the front end. By adjusting the
value of the potentiometer, the adder can cancel out the pulse from the output of the
front end and present only the amplified cell potential at the output.

land_meng-fig5-input-r-test
Figure 5. R in testing circuit
By turning off the input pulse, closing the switch at the top, and measuring the voltage
level at the bottom of the 90KOhm resistor (The output voltage of the front-stage
op-amp. Let’s call it V test ), we can calculate the input resistance of the cell. The R in can
be derived by $R_{in} = (4RfV_{test} )/(1-4V_{test}$ ).

land_meng-fig6-output-filter-offset
Figure 6. Output filtering and offsetting circuit.
9
This is the output stage of the system. It consists of a low-pass filter selection circuit and
an output voltage offset circuit. The user can choose either two filtered signals at
different frequencies or an unfiltered signal. By adjusting the potentiometer at the
positive input of the op-amp, we can adjust the output voltage level.

## Components

Because of the internal resistance of the cell and the
electrode, we picked the critical op-amp with high input impedance and low DC offset
such that the voltage can be transferred more efficiently to the op-amp.

an ideal op-amp for our circuit. After careful selection, we
decided to use TLC2274 from Texas Instrument. It has a maximum  8V supply voltage,
an input resistance of 10TOhm, an input offset voltage of about 300uV, UGBW of about
2.18MHz, and a CMRR of 75dB.


PCB layout for the front-stage circuit.
The PCB includes our TLC2274, 2 bypass capacitors, feedback resistor, feedback
capacitor, the 2.5KOhm, and the 10KOhm resistors on it. All the components we used
are 1206 surface mount components.
After that, we ordered the board and soldered the components onto the board. Since we
do not have any 1206 2.5KOhm resistors, we decided to use 10KOhm and 39KOhm
resistors instead, which gave us a gain of 4.9.

PCB layout for the back-stage circuit
The back-stage can pick the
gain between 10 and 1, apply filters of 1.6kHz and 160Hz, and set output offset voltage.
The back-stage PCB includes the rest of the circuit - the pulse injecting circuit, input
resistance measuring circuit, gain multiplying and cell cancellation circuit, and the output
filtering voltage offsetting circuit. We made some adjustments to the circuit such that the
user can pick between an overall gain of 20dB or 0dB (10 or 1 numerically). We used
0.1u and 0.01u capacitors with 10KOhm resistors at the output such that it can provide
LPF operating at 160Hz and 1.6KHz.