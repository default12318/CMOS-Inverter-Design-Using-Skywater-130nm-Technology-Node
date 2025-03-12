
# CMOS Inverter Design Using Skywater 130nm Technology Node

This project demonstrates the design and analysis of a CMOS inverter using the Skywater 130nm technology node. The project includes the creation of NMOS and PMOS devices, generation of I-V curves, voltage transfer characteristics (VTC) analysis, and analog layout using Magic VLSI. Below is a detailed explanation of each step.

---

## **1. NMOS (NFET) Characterization**

### **Schematic Design**
- The NMOS transistor was designed in Xschem with a testbench for sweeping \( V_{DS} \) and \( V_{GS} \).
- The `.dc` sweep command was used to analyze the current-voltage relationship: .dc Vds 0 1.8 0.2 Vgs 0 1.8 0.1

- ### **I-V Curve Results**
- The resulting I-V curves were plotted, showing the drain current (\( I_D \)) versus \( V_{DS} \) for different values of \( V_{GS} \).
- **Attached Image**: ![nfet schematic](https://github.com/user-attachments/assets/5ed5f24c-2848-4a96-8c0d-81c5bdfea56e)
- **Attached Graph**: ![Vds vs Vgs](https://github.com/user-attachments/assets/3a1924bf-8a6a-4295-bd92-65f02bf0b417)

---

## **2. PMOS (PFET) Characterization**

### **Schematic Design**
- Similarly, a PMOS transistor was designed in Xschem with its own testbench.
- The `.dc` sweep command was configured to analyze \( V_{DS} \) and \( V_{GS} \):.dc Vds 0 1.8 0.2 Vgs 0 1.8 0.01
- ### **I-V Curve Results**
- The I-V curves for the PMOS transistor were obtained, illustrating the behavior of \( I_D \) versus \( V_{DS} \) for various \( V_{GS} \) values.
- **Attached Image**:![pfet](https://github.com/user-attachments/assets/c2eefc22-387a-427c-b089-7caeb461c483)



---

## **3. CMOS Inverter Voltage Transfer Characteristics (VTC)**

### **Testbench Setup**
- A CMOS inverter was constructed by combining the NMOS and PMOS transistors.
- A testbench was created to sweep the input voltage (\( V_{in} \)) from 0V to \( V_{DD} \), while observing the output voltage (\( V_{out} \)).
- The SPICE code used for the simulation:.dc Vin 0 2 1m
- ### **Simulation Results**
- The voltage transfer characteristics (VTC) curve was generated, showing the transition region where the inverter switches from logic high to logic low.
- Noise margin analysis was also performed to determine the inverter's performance.

#### **Attached Images**
1. **SPICE Output**:![VTC spice code](https://github.com/user-attachments/assets/0da64f81-2329-4ecb-99c3-5bb0abf42b7b)

2. **Inverter Testbench Schematic**:![VTC inverter test bench](https://github.com/user-attachments/assets/b868578b-22fd-465f-9853-e1100f389b42)

3. **VTC Curve (Gain Analysis)**:![VTC gain](https://github.com/user-attachments/assets/0d6f92c0-7be7-4741-b586-67bfd40a81af)

---

## **4. Analog Layout Design Using Magic**

### **Layout Creation**
- The analog layout for the CMOS inverter was created using Magic VLSI.
- The layout includes both NMOS and PMOS transistors, with proper connections for \( V_{DD} \), ground, input, and output.

### **Post-Layout Simulation**
- SPICE netlists were extracted from the layout.
- Delay analysis and inverter output waveforms were simulated using these netlists.

#### **Attached Images**
1. **Analog Layout in Magic**:![Screenshot 2025-02-08 203317](https://github.com/user-attachments/assets/8953b3c6-79ca-410c-b602-b2485ce6e756)

2. **Analog Layout in Magic Redrraw to BUffer connections** : ![Screenshot 2025-03-12 164453](https://github.com/user-attachments/assets/ddde3fca-28a9-40d5-afc7-dbf77669e02e)

3. **Delay Analysis from Layout**:![Layout delay analysis](https://github.com/user-attachments/assets/f2f35d82-6458-4784-9b31-aeee87b2a7b0)

4. **Spice Output**:![Analog layout spice](https://github.com/user-attachments/assets/77c8a1c5-aeb9-4b64-ae74-594e434aff6f)


---

## **5. Tools Used**
- **Xschem**: For schematic entry and SPICE simulation.
- **Ngspice**: To simulate I-V curves, voltage transfer characteristics, and post-layout performance.
- 
- **Magic VLSI**: For creating analog layouts and extracting SPICE netlists.

---

## **6. Key Outputs**

| Step                     | Output Description                                
|--------------------------|--------------------------------------------------|
| NMOS I-V Curves          | Drain current vs \( V_{DS} \) for varying \( V_{GS} \). |  
| PMOS I-V Curves          | Drain current vs \( V_{DS} \) for varying \( V_{GS} \). |                     
| Voltage Transfer Curve   | Transition characteristics of CMOS inverter.     |  
| Post-Layout Simulation   | Delay analysis and output waveforms from layout. |  

---

## **7. Conclusion**

This project successfully demonstrates the design flow for a CMOS inverter using Skywater's 130nm technology node, from transistor characterization to layout design and post-layout simulation. The results validate the expected behavior of both individual transistors and the CMOS inverter as a whole.
