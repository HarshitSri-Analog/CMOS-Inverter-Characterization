# CMOS Inverter Characterization  

## Overview  
This repository focuses on the detailed characterization of a CMOS inverter. The study includes:  
1. **Switching Threshold Point** analysis using the Voltage Transfer Characteristics (VTC).  
2. **Propagation Delay** calculation.  
3. Evaluation of **dynamic and static power consumption** in CMOS inverters.  

## Table of Contents  
1. [Introduction to CMOS Inverter](#introduction-to-cmos-inverter)  
2. [Pull-Up and Pull-Down Networks](#pull-up-and-pull-down-networks)  
3. [Significance of CMOS Circuits in VLSI](#significance-of-cmos-circuits-in-vlsi)  
4. [Key Areas of Characterization](#key-areas-of-characterization)  
    - [Voltage Transfer Characteristics (Switching Threshold)](#voltage-transfer-characteristics-switching-threshold)  
    - [Propagation Delay](#propagation-delay)  
    - [Power Consumption](#power-consumption)  
5. [Tools and Technology](#tools-and-technology)  
6. [Key Results](#key-results)  
7. [Conclusion](#conclusion)  

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

## Significance of CMOS Circuits in VLSI  
1. **High Efficiency:** CMOS circuits consume negligible power in steady states, making them ideal for low-power applications.  
2. **Scalability:** CMOS technology scales well with shrinking technology nodes, enabling high-density integration.  
3. **High Speed:** The complementary design ensures fast switching and high operational frequency.  
4. **Low Cost:** CMOS fabrication processes are cost-effective and widely adopted in the industry.  
5. **Wide Applications:** CMOS circuits are foundational in digital electronics, including processors, memory, and IoT devices.  

## Key Areas of Characterization  

### Voltage Transfer Characteristics (Switching Threshold)  
- **Definition:** The Voltage Transfer Characteristics (VTC) plot illustrates the relationship between input voltage and output voltage.  
- **Switching Threshold:** The point where *V_{in} = V_{out}* defines the balance between the pull-up and pull-down networks, influencing noise margin and stability.  

### Propagation Delay  
- **Definition:** The delay is the time taken for the inverter to switch its output in response to an input change. It consists of:  
  - tplh: Time for LOW-to-HIGH transition.  
  - tphl: Time for HIGH-to-LOW transition.  
- **Significance:** A smaller propagation delay ensures faster circuit operation and is crucial for high-speed applications.  

### Power Consumption  

#### Static Power Consumption  
- **Definition:** Power consumed in a steady state (when the inverter is not switching).  
- **Observation:** Ideal CMOS inverters have negligible static power due to no direct current path between supply and ground. However, leakage currents can lead to small static power dissipation.  

#### Dynamic Power Consumption  
- **Definition:** Power consumed during switching, mainly due to charging and discharging of load capacitance.  
- **Formula:**  
  P_{dynamic} = a\*Cl\*Vdd^2\*f
  Where:  
  - a: Activity factor  
  - Cl: Load capacitance  
  - Vdd: Supply voltage  
  - f: Frequency of switching  

## Tools and Technology  
- **Simulation Software:** Cadence Virtuoso/SPICE simulator  
- **Technology Node:** 180nm  

## Key Results  
1. Identified the switching threshold point from VTC for noise margin analysis.  
2. Calculated propagation delays (tplh, tphl) to evaluate inverter performance.  
3. Quantified static and dynamic power consumption under various conditions.  

## Conclusion  
This study emphasizes the characterization of a CMOS inverter, providing critical insights into its performance and efficiency. These findings are essential for designing robust and high-performance digital circuits in VLSI systems.  

**Note:** This repository's work is in progress and will be completed soon.
