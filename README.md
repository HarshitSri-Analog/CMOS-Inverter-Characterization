# CMOS Inverter Characterization  

## Overview  
This repository focuses on the detailed characterization of a CMOS inverter. The study includes:  
1. **Switching Threshold Point** analysis using the Voltage Transfer Characteristics (VTC).  
2. **Noise Margin** measurement.
3.  **Propagation Delay** calculation.  
4. Evaluation of **dynamic and static power consumption** in CMOS inverters.  

## Table of Contents  
1. [Introduction to CMOS Inverter](#introduction-to-cmos-inverter)  
2. [Pull-Up and Pull-Down Networks](#pull-up-and-pull-down-networks)  
3. [Significance of CMOS Circuits in VLSI](#significance-of-cmos-circuits-in-vlsi)
4. [Tools and Technology](#tools-and-technology)  
5. [Key Areas of Characterization](#key-areas-of-characterization)  
    - [Voltage Transfer Characteristics (Switching Threshold)](#voltage-transfer-characteristics-switching-threshold)
    - [Noise Margin](#Noise-Margin) 
    - [Propagation Delay](#propagation-delay)  
    - [Power Consumption](#power-consumption)
6. [Observation](#Observation)
7. [Key Results](#key-results)  
8. [Conclusion](#conclusion)  

## Introduction to CMOS Inverter  
A CMOS (Complementary Metal-Oxide-Semiconductor) inverter is a fundamental digital circuit that inverts the input signal. It is composed of two complementary transistors:  
- **PMOS**: A p-type MOSFET that operates as the pull-up network.  
- **NMOS**: An n-type MOSFET that operates as the pull-down network.  

The complementary action ensures efficient switching between logic levels while consuming minimal power in steady states.  

## Pull-Up and Pull-Down Networks  
- **Pull-Up Network (PUN):**  
  - Formed by the PMOS transistor.  
  - Responsible for pulling the output voltage to the supply voltage (Vdd) when the input is LOW.  
  - The PMOS conducts when the gate-to-source voltage (*Vgs*) is less than the threshold voltage (*Vth*).  

- **Pull-Down Network (PDN):**  
  - Formed by the NMOS transistor.  
  - Responsible for pulling the output voltage to ground (*GND*) when the input is HIGH.  
  - The NMOS conducts when *Vgs > Vth*.  

- **Importance of PUN and PDN:**  
  - Ensure full rail-to-rail output swing, providing robust logic levels.  
  - Control the switching dynamics and propagation delay of the inverter.  
  - Maintain low static power consumption during steady states due to the absence of a direct path between *Vdd* and *GND*.
 
| ![CMOS Inv](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter%20DC%20Schematic%20TB.png) | 
| :---: | 
| Fig 1: CMOS Inverter schematic |


## Significance of CMOS Circuits in VLSI  
1. **High Efficiency:** CMOS circuits consume negligible power in steady states, making them ideal for low-power applications.  
2. **Scalability:** CMOS technology scales well with shrinking technology nodes, enabling high-density integration.  
3. **High Speed:** The complementary design ensures fast switching and high operational frequency.  
4. **Low Cost:** CMOS fabrication processes are cost-effective and widely adopted in the industry.  
5. **Wide Applications:** CMOS circuits are foundational in digital electronics, including processors, memory, and IoT devices.

| ![CMOS Inv](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter%20DC%20Schematic.png) | 
| :---: | 
| Fig 2: CMOS Inverter TestBench Used | 

## Tools and Technology  
- **Simulation Software:** Cadence Virtuoso/SPICE simulator  
- **Technology Node:** 180nm  

## Key Areas of Characterization  

### Voltage Transfer Characteristics (Switching Threshold)  
- **Definition:** The Voltage Transfer Characteristics (VTC) plot illustrates the output voltage as a function of input voltage. This curve provides insights into the transition region, logic levels, and stability of the CMOS inverter.  
- **Switching Threshold:** The switching threshold is the input voltage where the output voltage equals the input voltage (*V<sub>in</sub> = V<sub>out</sub>*). It reflects the point of equilibrium between the pull-up and pull-down networks.  
  - **Importance:**  
    - A well-defined switching threshold ensures balanced noise margins, which are critical for reliable digital logic operations.  
    - The threshold point also impacts the inverter’s susceptibility to noise and its ability to drive subsequent stages.  

**Simulation Result:**  
The VTC curve for the CMOS inverter has been simulated and plotted using Cadence Virtuoso. The switching threshold point and also the parametric analysis have been done and are as shown:

| ![CMOS Inv VTC](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter_VTC.png) | 
| :---: | 
| Fig 3: Voltage Transfer Characteristics | 

| ![CMOS Inv Vm](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter_VmFinal.png) | 
| :---: | 
| Fig 4: Switching Threshold parametric Analysis |

### Noise Margin   
- **Definition:** Noise margin quantifies the tolerance of a digital circuit to noise, ensuring proper logic level interpretation. It is defined as the difference between the logic levels that the inverter can reliably output and the levels it can correctly interpret as input.  
- **Key Parameters:**  
  - **Noise Margin High (NM<sub>H</sub>):** The difference between the minimum output high voltage (*V<sub>OH</sub>*) and the minimum input high voltage (*V<sub>IH</sub>*).  
    \[ NM<sub>H</sub> = V<sub>OH</sub> - V<sub>IH</sub> \]  
  - **Noise Margin Low (NM<sub>L</sub>):** The difference between the maximum input low voltage (*V<sub>IL</sub>*) and the maximum output low voltage (*V<sub>OL</sub>*).  
    \[ NM<sub>L</sub> = V<sub>IL</sub> - V<sub>OL</sub> \]  
- **Significance:**  
  - Higher noise margins indicate better immunity to noise and more robust circuit operation.  
  - Noise margins depend on the steepness of the VTC curve near the switching threshold and the voltage levels defined by the logic family.  

**Simulation Result:**  
The noise margin characteristics have been extracted from the VTC curve and calculated as NM<sub>H</sub> and NM<sub>L</sub>. Results are displayed alongside graphical interpretations of the VTC plot.  

| ![CMOS Inv NM](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter_VTC_NoiseMarginFinal.png) | 
| :---: | 
| Fig 5: Noise Margin of CMOS Inverter |

### Propagation Delay  
- **Definition:** Propagation delay measures the time taken for the output to respond to a change in input. It consists of two components:  
  - **t<sub>plh</sub>:** Delay during the LOW-to-HIGH transition of the output.  
  - **t<sub>phl</sub>:** Delay during the HIGH-to-LOW transition of the output.  
- **Significance:**  
  - A lower propagation delay ensures faster circuit operation, which is essential for high-speed digital systems.  
  - t<sub>plh</sub> and t<sub>phl</sub> can be used to calculate the average delay, giving an overall measure of the inverter’s speed.  
- **Factors Affecting Delay:**  
  - Load capacitance (*C<sub>load</sub>*): Larger capacitance increases delay.  
  - Supply voltage (*V<sub>dd</sub>*): A higher supply voltage typically reduces delay.  
  - Drive strength of transistors: Stronger transistors reduce delay.  

**Simulation Result:**  
Propagation delay components (t<sub>plh</sub> and t<sub>phl</sub>) have been simulated under different load conditions. Results, including plots and delay values, are provided for better understanding and design optimization:

| ![CMOS Inv tplh](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter_tplh_4um.png) | 
| :---: | 
| Fig 6: t<sub>plh</sub> delay of CMOS Inverter |

| ![CMOS Inv tphl](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter_tphl_4um.png) | 
| :---: | 
| Fig 7: t<sub>phl</sub> delay of CMOS Inverter |

| ![CMOS Inv tpd](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter_tpd%20parametric.png) | 
| :---: | 
| Fig 8: t<sub>pd</sub> delay of CMOS Inverter (Paramteric Analysis) |

### Power Consumption  

#### Static Power Consumption  
- **Definition:** Power dissipated when the inverter is in a steady state and not switching.  
- **Key Factors:**  
  - Ideally, CMOS inverters exhibit negligible static power consumption due to the absence of a direct path between *V<sub>dd</sub>* and *GND* in steady states.  
  - Leakage currents, particularly in modern technology nodes, contribute to small static power losses.  
- **Observation:**  
  - Static power is minimized in this design, as leakage currents are negligible in the 180nm technology node.  

**Simulation Result:**  
The static power dissipation of the inverter has been simulated with results shown below:

| ![CMOS Inv Pstatic](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter_power%20static%204u.png) | 
| :---: | 
| Fig 9: CMOS Inverter-Static power Consumption |

#### Dynamic Power Consumption  
- **Definition:** Power dissipated during switching due to charging and discharging of load capacitance.  
- **Formula:**  
   P<sub>dynamic</sub> = a\*C<sub>load</sub>\*V<sub>dd</sub>^2\*f  
  Where:  
  - *a*: Activity factor (probability of switching)  
  - *C<sub>load</sub>*: Load capacitance  
  - V<sub>dd</sub>: Supply voltage  
  - f: Frequency of operation 
- **Key Observations:**  
  - Dynamic power dominates overall power consumption in CMOS circuits.  
  - It is influenced significantly by the load capacitance and operating frequency.  
  - Reducing activity factor and supply voltage are effective strategies to lower dynamic power.  

**Simulation Result:**  
Dynamic power consumption has been quantified for various load capacitances and sizes. Results are presented alongside a discussion on how the parameters influence power dissipation:

| ![CMOS Inv Pdynamic](https://github.com/HarshitSri-Analog/CMOS-Inverter-Characterization/blob/main/CMOS%20Inverter/CMOS%20Inverter_power%20dynamic%20parametric.png) | 
| :---: | 
| Fig 10: P<sub>dynamic</sub> of CMOS Inverter |

## Observation  

1. **Switching Threshold Calculation:**  
   - To determine the switching threshold, I plotted the Voltage Transfer Characteristics (VTC) curve.  
   - The size of the PMOS transistor was varied while keeping the size of the NMOS transistor fixed.  
   - I aimed to achieve the most symmetric VTC, where the switching threshold (*V<sub>m</sub>*) equals 900mV.  
   - This was achieved at a PMOS width of 4µm.  

2. **Noise Margin Calculation:**  
   - Using the PMOS width of 4µm, I calculated the noise margins.  
   - The results of the noise margin analysis are discussed in the results section.  

3. **Propagation Delay Analysis:**  
   - The width of the PMOS transistor was varied to determine the size at which the propagation delay is minimized.  
   - I found that at a PMOS width of 2.74µm, the propagation delay was at its minimum.  

4. **Power Consumption Analysis:**  
   - Using the PMOS width of 4µm, I calculated both dynamic and static power consumption.  
   - **Dynamic Power Consumption:**  
     - I observed that as the size of the PMOS transistor decreases, the dynamic power consumption also decreases.  
   - **Static Power Consumption:**  
     - During the static power analysis, I observed that the maximum current flows through the CMOS inverter during the transition period.  

 ## Key Results  

| Parameter                     | Value                  | Notes                                   |
|-------------------------------|------------------------|-----------------------------------------|
| Switching Threshold (*V<sub>m</sub>*) | 900mV                | Achieved at PMOS width (*W<sub>p</sub>*) = 4µm. |
| Output Voltage Levels (Noise Margin)         |                        |                                         |
| - *V<sub>OH</sub>*            | 1.6806V               |                                         |
| - *V<sub>IH</sub>*            | 1.0033V               |                                         |
| - *V<sub>OL</sub>*            | 85.7682mV             |                                         |
| - *V<sub>IL</sub>*            | 829.221mV             |                                         |
| - Noise Margins (*NM<sub>H</sub>* and *NM<sub>L</sub>*) | 677.3mV and 743.45mV respectively | Calculated based on *V<sub>OH</sub>*, *V<sub>IH</sub>*, *V<sub>OL</sub>*, and *V<sub>IL</sub>*. |
| Propagation Delay (*t<sub>pd</sub>*) | 1.256ns (at *W<sub>p</sub>* = 4µm) | Minimum delay = 1.229ns at *W<sub>p</sub>* = 2.743µm. |
| Dynamic Power Consumption     | 242.6nW               | Calculated at *W<sub>p</sub>* = 4µm.   |
| Static Power Consumption      | 10.29µW               | Observed maximum current during transition period. |


## Conclusion  
This study emphasizes the characterization of a CMOS inverter, providing critical insights into its performance and efficiency. These findings are essential for designing robust and high-performance digital circuits in VLSI systems.  

## Acknowledgements
Special thanks to [Cadence Virtuoso](https://www.cadence.com/en_US/home/tools/custom-ic-analog-rf-design/virtuoso-studio.html) team for providing an advanced platform for analog design & simulation. Additionally, gratitude is extended to [IIT Roorkee July 2018](https://youtube.com/@iitroorkeejuly?si=aMPGdDgZXCj2mn84) channel for providing such an informative lecture on [CMOS Digital VLSI Design](https://youtube.com/playlist?list=PLLy_2iUCG87Bdulp9brz9AcvW_TnFCUmM&si=zkWH74foxKOikoun). 

Feel free to explore the repository for insights into the design and characterization of CMOS Inverter. Contributions and feedback are welcome!

***If you find this repository helpful, please consider giving it a ⭐!***
