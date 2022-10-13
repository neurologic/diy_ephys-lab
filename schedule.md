# Syllabus

Target:
- 20 students? (Start with 10 for first pilot of class?)
- NSB, PHYS, BIOL (, MATH?)

## Aims

- Integrate computational modeling with biological experimentation
- Integrate neurobiology, electronics theory, and math (and computer science?)
- Provide more math and physics for biologists
- Provide more biology for mathematicians and physicists
- Access to lower footprint neurophysiology experiments

## Schedule

With each topic aim for: 1) one shorter day of introducing concepts and computational modeling and 2) one longer day of experiments with circuits and living tissue (students pair up for experiments). The actual scripting of the computational models could be included or provided. Use of the computational models for simulations of neural physiology would be used to supplement experiments on biological tissue.

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
:width: 800
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
:width: 500
:align: center
:::
Test the effect of ion concentration on resting membrane potential
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
:width: 500
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

### 5: Circuits

- circuits underlying behavior: sensory stimulus --> decision --> motor response
- stimulus-specificity for different circuits
- behavioral strength as a function of stimulus strength (via spike rate)

:::{admonition} Models
Computational models of synaptically-connected neurons (even if it is just pre-scripted simulations, would still be instructive). For example, brain oscillations from reciprocally-connected networks.
:::

::::{admonition} Experiments
:::{image} /images/earthworm-giant-fiber-system.jpeg
:width: 400
:align: center
:::

Two distinct Giant Fibers with different morphology are activated by touch to separate pools of sensory receptors
::::


### 6: Conduction Velocity

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
:width: 500
:align: center
:::

:::{image} /images/earthworm-conduction-velocity-temperature.jpeg
:width: 300
:align: center
:::
::::

### 7: Excitability

- interaction between resistance and capacitance
- short versus long square-wave stimulation of neural membranes
- ion channel density

:::{admonition} Models
Can use RC model of the membrane. Could also add a parameter in the model for density of voltage-gated sodium channels?
:::

::::{admonition} Experiments
:::{image} /images/strength-duration_Lapicque.png
:width: 400
:align: center
:::
Caveat: if using earthworm, requires precise stimulation and readout of that stimulation (duration with resolution in the 10microsecond range and amplitude).  
Alternative: Simulation of computational model from RC circuits (with spiking added or spike threshold marker). *Benefit* of this alternative is that 
::::

### 8: "Catching" an action potential

- interaction between space constant and time constant
- reinforce/review understanding of differential measurement of electrical events
- reinforce/review understanding of action potential polarity across membrane and location along membrane

::::{admonition} Experiments
:::{image} /images/Kladt_earthworm-CAP-geometry.png
:width: 800
:align: center
:::
Use differential amplification techniques to trap an action potential between the electrodes. Does not require electrical stimulation, though that can make it easier. 
::::

### 9: Sensory Physiology

- graded sensory receptor potentials
- temporal summation
- short-term plasticity

### 10: Motor Coordination 

- Patterns across time in high dimensional space
- Dimensionality reduction (PCA)
- Matrix transformations
- Brain Computer Interfaces (BCI)

## Materials

- 10x magnifying? monofocal? simple magnifying glass?
- manipulators (there are 3D print designs available with enough precision for these experiments)
- PC computer per pair of students
- differential amplifiers (have 20, need 20 more for 20 total students - $60 each)
- high resistance DC amplifier (might not need if use NiDAQ ADC with 1V range). [Circuit Plans for a good one at low cost](https://neurologic.github.io/diy_ephys-lab/intracellular-amp.html)
- bright illumination (can be LED unless too much electrical noise)
- lots of pins to make earthworm recording chamber
- 3D print (or acrylic?) plant recording chamber
