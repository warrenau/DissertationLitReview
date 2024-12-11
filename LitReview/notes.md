# Digital Twins

## Experimental Validation

---
**Digital twin-enabled autonomous fault mitigation in diesel engines: An experimental validation**

*Khawale et. al.*

- validation used model-in-loop (MIL) and hardware-in-loop (HIL) simulations
- paper 'focuses on creating an online fault mitigation framework for marine diesel engines' for autonomous surface vessels
- HIL code is available at: [HIL-FaultMitigation](https://github.com/Rajk-hawale/HIL-FaultMitigation)
- lots of neural network use in the models of the subsystems
- MIL testing is used for failure modes that are difficult to reproduce experimentally (fuel injector nozzle erosion/clogging and intake manifold leakage)
- validated neural network cylinder model against real data from engine
- hybrid model is validated by averaging (mean value) the operating conditions for steady state, then validated over the entire dataset to see transient response
- claims that the method can be extended to other engines with retuning of hybrid model parameters and appropriate calibration


---

---
**A Standards-Based Digital Twin of an Experiment with a Scale Modle Ship**

*Fonseca et. al.*

- as the title suggests, this work wishes to use data standards to allow models to work with varying proprietary software used in the maritime industry
- used a small experiment ship in a wave tank and created a digital twin for it leveraging existing instrumentation and such at the facility
- wrote dynamic positioning control module in Matlab -- might be worth looking at (reference 30 in this work)
- source code for digital twin is available at [htts://github.com/shiplab/dt_cv](https://github.com/shiplab/dt_cv)

---


---
**Monitoring and control of air filtration systems: Digital twin based on 1D computational fluid dynamics simulation and experimental data**

*Solari et. al.*

- this study uses 1D CFD for real time control, but cites other studies that have combined 3D CFD with reduced order models to acheive results in real time
- has citation for DIgital Twin definition (Grieves 2014) "When a virtual model receives input from the real system and uses its results to provide feedback and maintain control over the real system, it is referred to as 'Digital Twin' "
- data acquisition in LabVIEW, digital model in Flownext (1D lumped parameter fluid dynamics)
- 
---