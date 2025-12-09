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


---
**Thermal Modeling of an eVinci-like heat pipe microreactor using OpenFOAM**

*Price et. al.*

- Serpent is used to determine power distribution to give to OpenFOAM
- focus of study is on heat pipe model: 2 different models are used, a more detailed model and a simplified model
- core design was based on eVinci, using TRISO fuel (modeled as AGR-2 UCO TRISO), 4 MWth power output, core lifetime of 4 years
- The core layout is similar to what I have modeled so far, but has a more even distribution of cooling elements (at least one in every row)
- Serpent model used 1200 K as temp for graphite
- OpenFOAM model uses 1/12 symmetry
- Exterior uses convective heat transfer coefficient of 5 W/m^2/K at 298 K
- Thermal conductivities: 15 W/m/K for graphite, 2.98 W/m/K for UCO, 4.24 W/m/K for TRISO particle, 9.92 W/m/K for homogenized fuel compact
- Math got a bit dry in section 2, might need to revisit at a later time


---

---
**Transient Analysis of a Micro-reactor using the DireWolf Code Suite**

*Roskoff et. al.*

- DireWolf uses Griffin (neutronics), Bison (thermal-mechanical), and Sockeye (heat pipe) for reactor modelling
- Details of core design and codes presented in companion paper
- eVinci inspired design
- 2 transient events: 1) Inadvertant Control Drum Rotation (IDR) and 2) Single Control Drum Rotation (SDR)
- IDR:
    - simulaneous rotation (constant speed) of all control drums from critical outward
    - maximum rotation occurs at 2 seconds, followed by rotation to shutdown
    - drum rotation speeds: 0.5, 1, 2, 3 degrees per second
    - safety limits for simulations: prompt critical (reactivity > $1.0), max fuel temp (>1600 deg C)
    - starting power: ~5.5e+06
    - max power (highest case): ~5.0e+09
    - power increases: <4x, <4x, 40x, 840x
    - highest rotation speed goes prompt critical and reaches max power before 2 seconds
- SDR:
    - sudden rotation of 1 control drum from critical to completely outward
    - 30 seconds of total time; at 2 seconds into transient, all drums are moved to shutdown, except for the drum next to the failed drum, which is stucked at critical
    - drum rotation speeds: 5, 10, 15, 20 degrees per second
    - safety limits for simulations: prompt critical (reactivity > $1.0), max fuel temp (>1600 deg C)
    - starting power: ~5.5e+06
    - max power (highest test): ~7.0e+08
    - FWHM: ~0.5 sec
    - power increases are: <5x, <5x, 20x, >200x from nominal power
    - core reaches uniform temperature around 14 seconds (15 deg/sec case)
    - 




---

---
**Modeling and Analysis of a Micro-reactor using the DireWolf Code Suite**

*Roskoff et. al.*

- DireWolf uses Griffin (neutronics), Bison (thermal-mechanical), and Sockeye (heat pipe)
- steady state results presented, along with refined model for use in transient simulations
- 6 MWth at full power
- average temp of heat pipes 800C
- average fuel temp 900C
- TRISO w/ 19.75 wt% enriched HALEU
- Graphite monolith
- control drums (B4C) for primary control, shutdown rods for redundant
- table of dimensions
- Griffin solves for flux and power; Bison solves temperature; temp fed back into Griffin for cross sections; iteration continues until temperature and power has converged
- temperature reactivity coefficient: -4.26 pcm/deg C
- delayed neutron fraction (beta_eff): 0.00712
- delayed neutron decay constant (lambda): 0.472 per second


---

---
**The Monolithic Heat Pipe Microreactor Reference Plant Model**

*Ortensi et. al.*

- DireWolf model for generic Heat Pipe Microreactor (gHPMR) design, which is similar to other work for eVinci inspired HPMR
- table of specifications and measurements for reactor
- hexagonal core block more similar to my preliminary design than other work I have seen so far
- graphite monolith, ss316 clad sodium heat pipes
- thermal model uses effective convective boundary for heat pipes
- each heat pipe gets its own Sockeye subapplication
    - initial temperature: 1073.15 K
    - condenser convection temperature: 523.15 K
    - condenser convection heat transfer coefficient: 312.4 K
    - heat pipe heat removal: 20kW
- steady state results show power peaks toward center due to control drums and reflector
- transient simulation: loss-of-heat-sink (LHS)
    - secondary stops working, heat is no longer actively removed from heat pipes
    - monolith has positive temperature reactivity coefficient
    - fuel has strong doppler effect for negative temeprature reactivity coefficient
    - power oscillates as heat is moved through heat pipes and fuel cools down again
    - total power goes from 100% to 2% in 1000 seconds, stabilizes at ~5% after 10000 seconds
    - prompt power goes from nearly 100% to 0.4% in 1000 seoncds, stabilizes at ~3% after 10000 seconds
    - average temperature spikes from ~1155 to ~1220 K in ~300 seconds
    - max temperature goes from ~1560 to ~1610 in ~200 seconds





---











