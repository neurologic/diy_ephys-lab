# Syllabus

*Title*: **Biology of Electricity**

Alternative titles:
- **Harnessing Bioelectricity**
- **Neuromorphic Design**
- **Building the Brain**
- **Excitable Networks**

Target:
- 20 students? (Start with 10 for first pilot of class?)
- NSB, IDEAS, PHYS, BIOL, CIS (, MATH?)

## Aims

- Integrate computational modeling with biological experimentation
- Integrate neurobiology, electronics theory, and math (and computer science?)
- Provide more math and physics for biologists
- Provide more biology for mathematicians and physicists
- Access to lower footprint neurophysiology experiments

## Schedule

With each topic aim for: 1) one shorter day of introducing concepts and computational modeling and 2) one longer day of experiments with circuits and living tissue (students pair up for experiments). The actual scripting of the computational models could be included or provided. Use of the computational models for simulations of neural physiology would be used to supplement experiments on biological tissue.

### 0: Introduction to BioElectricity

::::{admonition} Electric Fish Demo
:::{image} /images/weakly-electric-fish-Efields-locate-communicate.jpeg
:width: 600
:align: center
:::

Discussion of "excitable" membranes and "excitable" networks
::::

### 1: Passive Spread (and differential measurement)

- space constant
- resistors in series and parallel
- spatial summation at synapses
- axon diameter and myelination

::::{admonition} Models
:::{image} /images/circuit-model-passive-spread.png
:width: 400
:align: center
:::
$$
\frac{\partial{V}}{\partial{t}} = - \lambda * V
$$
::::

::::{admonition} Experiments
:::{image} /images/space-constant.png
:width: 700
:align: center
:::
Measure a membrane polarization from different distances. Compare effect of electrode configurations.  

Combine circuits to examine spatial summation. 
::::

### 2: Ionic Basis of Membrane Potential

- ohmic conductance (V=IR)
- current-limiting resistors
- Kirchoff's laws
- resistance and *conductance*

::::{admonition} Models
:::{image} /images/circuit-model-active.png
:width: 300
:align: center
:::
$$
\frac{\frac{E1}{R1} + \frac{E2}{R2}}{\frac{1}{R1} + \frac{1}{R2}}
$$
::::

::::{admonition} Experiments
:::{image} /images/plant-membrane-potential.png
:width: 400
:align: center
:::
Just resting potential (no spiking yet). Test the effect of ion concentration on resting membrane potential.
::::

### 3: Responses to input and Filtering

- time constant
- resistors and capacitors in parallel
- current application and voltage measurement
- linear differential equations

::::{admonition} Models
:::{image} /images/circuit-task_RC-simple.png
:width: 300
:align: center
:::
$$
\partial{V} = (Iapp - \frac{V-E}{R}) * (\frac{\partial{t}}{C})
$$
::::

::::{admonition} Experiments
:::{image} /images/rc-circuit.png
:width: 800
:align: center
:::
::::

### 4: HH action potential and Non-Ohmic Conductances

- negative resistance (voltage-gated sodium conductance)
- summation of dynamic conductances
- non-linear differential equations

::::{admonition} Models
:::{image} /images/HH-circuit-model.png
:width: 300
:align: center
:::
:::{image} /images/HH-model.png
:width: 400
:align: center
:::
::::

::::{admonition} Experiments
:::{image} /images/plant-membrane-potential.png
:width: 500
:align: center
:::
Test the effect of ion concentration on action potential shape (and/or pharma to block Ca2+ channels)
::::

### 5: Amplification and Transistor Logic

- analogy between transistor logic and action potentials
- basic amplification principles for recording most biological signals
- implementation of RC circuits for signal processing

::::{admonition} Models
:::{image} /images/transistor-logic.png
:width: 500
:align: center
:::
::::

::::{admonition} Experiments
Building an analog circuit of an action potential 
:::{image} /images/analog-spiking-model.png
:width: 500
:align: center
:::

Building an amplifier to measure action potentials in biological tissue.
:::{image} /images/two-stage-amp.png
:width: 600
:align: center
:::

::::

### 6: Neural Circuits/Networks

- circuits underlying behavior: sensory stimulus --> decision --> motor response
- stimulus-specificity for different circuits
- behavioral strength as a function of stimulus strength (via spike rate)

:::{admonition} Models
Network models: synaptically-connected neurons of the basic RC circuit type (even if it is just pre-scripted simulations, would still be instructive). Change the synaptic weights or connectivity and investigate how it changes what the network "does": ie. brain oscillations from reciprocally-connected networks.
:::

::::{admonition} Experiments
:::{image} /images/earthworm-giant-fiber-system.jpeg
:width: 400
:align: center
:::

:::{image} /images/LGF-and-MGF-action-potentials-and-the-corresponding-electrode-placement-Channel-1-and.png
:width: 600
:align: center
:::

Two distinct Giant Fibers with different morphology are activated by touch to separate pools of sensory receptors
::::


### 7: Conduction Velocity

- reinforcing connections between anatomy and physiology
- the difference between electrical transmission in passive circuits versus biological membrane propogation of action potentials
- conduction velocity fasciliation

::::{admonition} Models
:::{image} /images/Byb_mgnlgn_pic17.png
:width: 500
:align: center
:::

$$
\lambda = \sqrt{\frac{r_m}{r_i}}  

r_m = \frac{R_m}{2 * \pi * radius}

r_i = \frac{R_i}{\pi * radius^{2}}
$$
::::

::::{admonition} Experiments
:::{image} /images/earthworm-conduction-velocity.jpeg
:width: 400
:align: center
:::

:::{image} /images/earthworm-conduction-velocity-temperature.jpeg
:width: 300
:align: center
:::
::::

### 8: Excitability

- interaction between resistance and capacitance
- short versus long square-wave stimulation of neural membranes
- ion channel density

:::{admonition} Models
Can use RC model of the membrane. Could also add a parameter in the model for density of voltage-gated sodium channels?
:::

::::{admonition} Experiments
:::{image} /images/strength-duration_Lapicque.png
:width: 300
:align: center
:::
Caveat: if using earthworm, requires precise stimulation and readout of that stimulation (duration with resolution in the 10microsecond range and amplitude).  
Alternative: Simulation of computational model from RC circuits (with spiking added or spike threshold marker). *Benefit* of this alternative is that 
::::

### 9: Sensory Physiology

- graded sensory receptor potentials
- temporal summation
- short-term plasticity

:::{admonition} Models
Add in a time and/or voltage-dependent change in excitability.
:::

::::{admonition} Experiments
:::{image} /images/crayfish-erg.png
:width: 500
:align: center
:::
Amplitude and flicker-frequency tungin.
::::

### 10: Motor Coordination 

- Patterns across time in high dimensional space
- Dimensionality reduction (PCA)
- Matrix transformations
- Brain Computer Interfaces (BCI)

:::{admonition} Models
:::{image} /images/network-model-cpg.png
:width: 600
:align: center
:::

::::{admonition} Experiments
:::{image} /images/kriti-violin.png
:width: 400
:align: center
:::
Simultaneous multi-channel recordings of movement. Optional: video-tracking.
::::

### 11-13: "Capstone" Project Ideas

:::{admonition} A Musical Instrument BCI
Mapping muscle activity onto musical notes (could even be physical oscillator circuits). Divergence and convergence from muscles to notes would combine the muscles in different ways to produce different "songs" from the same movement. The loudness of the notes would be controlled by the spike rate of the motor neurons. 
:::

::::{admonition} Retinal Receptive fields
:::{image} /images/retina.png
:width: 600
:align: center
:::

Analog circuit or even photodiode inputs to a network of arduino-based LIF model neurons for a combo analog and digital model of the circuit.
::::

::::{admonition} Central Pattern Generators
:::{image} /images/spikeling.png
:width: 500
:align: center
:::

The outputs can then convergently and divergently synapse onto an array of actuators with different synaptic weights to generate antagonistic muscle control. 
::::


::::{admonition} Olfaction
Odor Discrimination using Insect Electroantennogram Responses from an Insect Antennal Array. Comparison of EAG profiles across various insect species:
:::{image} /images/eag-odor-discrimination.png
:width: 700
:align: center
:::

Odor plume following (if have working mobile robot to send the control signals to):
:::{image} /images/olfactory-robot.jpeg
:width: 500
:align: center
:::
::::


<!-- 
## Back-Burner modules

### TBD: "Catching" an action potential

- interaction between space constant and time constant
- reinforce/review understanding of differential measurement of electrical events
- reinforce/review understanding of action potential polarity across membrane and location along membrane

::::{admonition} Experiments
:::{image} /images/Kladt_earthworm-CAP-geometry.png
:width: 800
:align: center
:::
Use differential amplification techniques to trap an action potential between the electrodes. Does not require electrical stimulation, though that can make it easier. 
:::: -->

## Materials

- 10x magnifying? monofocal? simple magnifying glass?
- manipulators (there are 3D print designs available with enough precision for these experiments)
- PC computer per pair of students
- differential amplifiers (have 20, need 20 more for 20 total students - $60 each)
- high resistance DC amplifier (might not need if use NiDAQ ADC with 1V range). [Circuit Plans for a good one at low cost](https://neurologic.github.io/diy_ephys-lab/intracellular-amp.html)
- bright illumination (can be LED unless too much electrical noise)
- lots of pins to make earthworm recording chamber
- 3D print (or acrylic?) plant recording chamber
- **ADC** 
	- audio input for 2 channels if enough amplification
	- arduino if slow enough (and enough amplificiation)
	- serial oscilloscope
	- **NiDaq**, but most expensive
	- Teensy should work great, but don't have it tested yet



