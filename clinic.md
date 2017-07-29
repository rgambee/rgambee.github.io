# Clinic Projects

At Harvey Mudd College, the [Clinic Program](https://www.hmc.edu/clinic/) serves as the capstone project for engineering majors. Teams of typically five students work for an academic year to solve a problem for an outside company. The program gives students experience with real-world issues and can sometimes lead to job offers from the project sponsors.

## SpaceX Clinic Project (2014-2015)

### Motivation
SpaceX relies heavily on data gathered during its rocket flights, both successful and otherwise, to inform future launches. While some of this information can be streamed via telemetry, there is far more data than available bandwidth. SpaceX therefore asked us to design, build and test a recoverable data recorder that would be analogous to a black box in the aviation industry. The device needed to
1. Receive and record data via Ethernet during rocket flight
2. Survive the extreme conditions of ascent, separation, and reentry
3. Be easily recoverable even in the event of a catastrophic failure.

<figure>
    <img class="centered" src="/media/housing.jpg" alt="The housing of one of our final prototypes">
    <figcaption>The housing of one of our final prototypes, painted bright orange for visibility.</figcaption>
</figure>

### My Role
I focused on designing the recorder's housing, from selecting materials to simulating design alternatives to testing prototypes. Since the conditions of a rocket explosion are largely unknown, determining appropriate test procedures proved to be somewhat of a challenge. We were able to draw from SpaceX and Air Force protocols for vibration and temperature cycling during nominal flights. However, we needed to be a bit more creative when it came to destructive testing of mission failure scenarios. Test protocols for black boxes used in the aviation industry offered some guidance, though we had to make compromises due to our limited testing resources and number of prototypes.

<figure>
    <img class="centered" src="/media/thermalSim.png" alt="Simulation of steady-state temperature distribution">
    <figcaption>Steady-state thermal simulation showing temperature in degrees Celsius. Modeling led us to include a heatsink to lower the MCU's operating temperature.</figcaption>
</figure>

### Results
Throughout the project, we used computer simulations to validate our designs, including vibration and thermal models to evaluate performance during nominal flight conditions. Our circuit board's dimensions and mounting scheme, plus the placement of its components, were selected to maximize its natural frequency and avoid resonance. We also added a heatsink to the housing which, based on our models, lowered the microcontroller's operating temperature from 120 to 90&nbsp;°C (248 to 194&nbsp;°F), an important change considering that the chip was only rated up to 105&nbsp;°C (221&nbsp;°F).

Later, we performed destructive testing on our late-stage prototypes to approximate mission failure scenarios. One unit was blowtorched to simulate atmospheric reentry and then hit with a sledgehammer to simulate impact with the ground or ocean. We estimated that the sledgehammer exerted a force of 200&nbsp;kN (45,000&nbsp;lbf) when it collided with the prototype. Amazingly, the microSD card inside was totally unscathed, and all of its data remained intact!

<figure>
    <img class="centered" src="/media/testing.jpg" alt="Destructive testing aftermath" style="width: 80%;">
    <figcaption>This prototype was subjected to destructive testing meant to approximate atmospheric reentry and ground impact. The housing successfully protected the data on the miscroSD card (lower right).</figcaption>
</figure>

## Sandia National Laboratory Clinic Project (2013-2014)

### Motivation
Barium titanate (chemical formula BaTiO<sub>3</sub>, BTO for short) exhibits a phenomenon known as ferroelectricity, in which an external electric field induces a field in the material that remains even when the external one is removed. It is analogous to ferromagnetism, in which exposure to an external magnetic field causes some materials to become permanent magnets that retain their magnetic field in the absence of any external one. BTO's ferroelectricity gives it a large dielectric constant, making it of interest for use in high performance capacitors that can store large amounts of energy. BTO nanoparticles in particular exhibit some bizarre and poorly understood ferroelectric and structural properties. Sandia National Laboratory tasked us with measuring the dielectric constant of different sized nanoparticles and exploring their atomic structure to better understand their puzzling properties.

<figure>
    <img class="centered" src="/media/BTOmodel.png" alt="COMSOL model of BTO nanoparticle slurry">
    <figcaption>COMSOL model showing BTO particles suspended in a solvent within a coin cell battery casing.</figcaption>
</figure>

### My Role
I was responsible for using analytical and computational models to determine the dielectric constant of the BTO nanoparticles from experimental results. Directly measuring the dielectric constant of a single nanoparticle is obviously infeasible. Instead, we dispersed the nanoparticles in a liquid solvent to form a slurry and measured the effective dielectric constant using electrochemical impedance spectroscopy (EIS). I could then use the models to relate that experimental slurry dielectric constant to the underlying particle dielectric constant. The numerical model was created using COMSOL and verified with three analytical models from literature. Due to limited computational resources, I was only able to simulate a relatively small number of particles. Therefore, in order to achieve the desired concentration, the size of the particles needed to be greatly increased compared to their actual size.

<figure>
    <img class="centered" src="/media/BTOplot.png" alt="Comparison of model predictions to experimental measurement" style="width: 100%">
    <figcaption>A plot comparing the predictions of the numerical (black) and analytical (blue, green and red) models to experimental measurement (solid pink with dotted pink representing the 2% uncertainty).</figcaption>
</figure>

### Results
It turned out that both the computational and analytical models were extremely sensitive to the measured slurry dielectric constant. This meant that even small measurement errors were amplified to absurdly large uncertainties in the dielectric constant of the BTO nanoparticles. Despite varying the particle concentration, solvent type, measurement method and more, we were unable to overcome this fundamental issue. Our findings therefore cast doubt on the feasibility of this technique and call into question the results of other groups who have used it. I had the opportunity to present my results as an invited speaker at the Spring, 2014 meeting of the [Materials Research Society](http://www.mrs.org/).
