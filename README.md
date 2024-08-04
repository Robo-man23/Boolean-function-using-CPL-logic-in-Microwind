<div align="center">
  <h1>Boolean function using CPL logic in Microwind</h1>
  <a href="https://sites.google.com/view/rhythmshah/implemented-boolean-function-using-cpl-logic-in-microwind"><b>Visit my website</b></a>
</div>


## **What is CPL Logic ?**

Complementary-pass-transistor logic which is abbreviated as CPL is an integral part of pass-transistor logic (PTL). Unlike CMOS where for pull-up or pull-down networks different MOS is used, in CPL either PMOS or NMOS is used. Control signals are applied in the gate and another set of signals are applied to the sources. As the mobility of holes is lesser than that of electrons, so PMOS is not preferred. Another advantage of the NMOS PTL logic style is low input load. In the CPL style, complementary inputs/outputs are obtained by using NMOS PTL with CMOS output inverters. However main disadvantages are threshold voltage drop (VDD – Vth) at the output and high static power dissipation. So, it uses external circuitry for good voltage swing restoration. The increased switching activity in the intermediary nodes is what causes the high static power. Future CPL stages must be able to receive all input signals, their inverses, and complementary outputs from the circuit. As a result, the core components of the CPL circuit are complimentary inputs, an NMOS pass transistor logic network for producing complementary outputs, and CMOS output inverters for restoring the output signals. The parasitic capacitances connected to each node in the circuit are significantly reduced when PMOS transistors are removed from the pass-gate network, and the operating speed is often faster than a full-CMOS equivalent. However, the improved transient qualities are sacrificed for the increased process complexity. To lessen the threshold-voltage drop in CPL circuits, the threshold voltages of the NMOS transistors in the pass-gate network must be lowered via threshold adjustment implantation to roughly 0V. This lessens overall noise immunity though and makes transistors more sensitive to off-mode subthreshold conduction.  

## **Implementation-**

For a given Boolean equation (A+B’)(C+D’)E, a CPL layout was created and simulated in Microwind for this task. Since CPL logic consists of 2 MOSFETs (NMOS and PMOS) per logic (AND, OR) the design has been tested and optimized to use minimum possible transistors for a given boolean expression while considering each transistor’s aspect ratio (w/L) to be 4λ/2λ. Calculation of, delay, and noise margin is done to have an effective output voltage level while considering the strong and weak logic of MOSFETs. Here, all the PMOS transistors share a common n-type substrate which is connected to Vdc to avoid the substrate bias effect. As we know, PMOS passes strong logic '1' and weak logic '0' while NMOS passes strong logic '0' and weak logic '1' so the output voltage is clipped off at 2.6V for logic '1'. This can be compensated by using another pair of NMOS and PMOS transistors which is not mentioned here. All the inputs - A, B, C, D, and E are provided as clock inputs with Vdc and VSS  as biasing voltage connections. Moreover, it was discovered that the lowest output voltage logic '0' is observed at the combination of inputs when: A is '0', B' is '1', C' is '0', D' is '1', and E' is '0' and produces high output logic '1' when: A is '1', B' is '0', C' is '1', D' is '0', and E' is '1'. 

## **Features-**

1. Each transistor's aspect ratio (w/L) is to be 4λ/2λ.
2. The average propagation delay is 36 ps.
3. The propagation delay from low to high is 58 ps. 
4. The rising time is 0.025 ns. 
5. High output voltage VOH is 2.5V, and low output voltage VOL is 0V. 
6. The threshold voltage is 1.35V. 
7. The low input voltage VIL is 0.53V.
8. The high input voltage VIH is 0.60V.
9. The noise margin low NMIL is 0.53V, and the noise margin high NMIH is 0.6V.
    
<table align="center">
  <tr>
    <th><h2><b>Pros</b></h2></th>
    <th><h2><b>Cons</b></h2></th>
  </tr>
  <tr>
    <td>Low dynamic Power consumption </td>
    <td>Output voltage logic '1' is clipped off at 2.5V</td>
  <tr>
    <td>Approx 0 steady state power consumption.</td>
    <td>Requires another compensating circuit</td>
  </tr>
  <tr>
    <td>Less Delay</td>
    <td>That increases the number of transistors</td>
  </tr>
  <tr>
    <td>Good Noise margin</td>
    <td>No full output voltage swing is available</td>
  </tr>
  <tr>
    <td>Less number of transistors compared to CMOS logic</td>
    <td>The effect of parasitic capacitance causes switching delays</td>
  </tr>
  <tr>
    <td>Stong Logic '0 is available at output</td>
    <td>Charge Feedthrough effect can be observed</td>
  </tr>
  <tr>
    <td>Works well in low frequency as power is directly proportional to frequency</td>
    <td>Complex to design compared to CMOS logic circuits</td>
  </tr>
</table>

## **Key Skills-**

- ➤ VLSI  
- ➤ Delay calculation
- ➤ Improving noise margin and output voltage degradation
- ➤ Microwind tool
- ➤ Fundamentals of digital logic circuits
- ➤ MOSFETs working in CPL logic




