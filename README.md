# DC-Regulated-Power-Supply

Electronic Internship Program

@Author: J. X. PENG (Alreitetrs Pourton)

Basic requirements:
Power transformer only for theoretical design (actual purchase according to the need), reasonable choice of integrated regulator and rectifier diodes.
Main technical index requirements:
Output voltage: Uo=+3V~+9V continuously adjustable
Output current: less than or equal to 800mA      
RMS value of ripple voltage: less than or equal to 5mV  
Voltage stabilization factor: less than or equal to 0.003

# I. Design program (including the necessary theoretical calculations)
1. The requirements of this experiment is to design a DC regulated adjustable power supply, the function is to realize the conversion of 220V, 50HZ alternating current into 3 - 9V adjustable DC voltage, the maximum value of the output current does not exceed 800mA, the RMS value of the ripple voltage, the regulator coefficient; the performance indexes are the output voltage, the output current, the regulator coefficient (indicating that the circuit's regulator performance when the voltage of the grid fluctuates), the output resistance (indicating that the circuit's regulator performance when the load current changes), the ripple voltage (AC component of the DC voltage). The performance indicators are output voltage, output current, voltage regulation coefficient (indicating the voltage regulation performance of the circuit when the grid voltage fluctuates), output resistance (indicating the voltage regulation performance of the circuit when the load current varies), ripple voltage (the AC component of the DC voltage).

2. The composition of a DC power supply consists of four parts:

![51093cc8fd720f0e042ff5450ed5b3cb](https://github.com/user-attachments/assets/19c3cc98-d8d1-456d-8e80-ce5e5c115c44)
Power transformer: play the role of voltage reduction
Rectifier circuit: to change the AC voltage into pulsating DC voltage, divided into half-wave rectification and full-wave rectification 

![image](https://github.com/user-attachments/assets/1ec0cb08-6de5-4304-a011-00c1ab1ce3ad)
(Half-wave rectifier on top, full-wave rectifier on bottom)

Filter circuit: reduce pulsation
Voltage regulator circuit: voltage stabilization
Note: The grid voltage will have ± 10% fluctuations, and the load has a certain range of changes.
Circuit design rectifier part of the choice of single-phase bridge full-wave rectifier circuit, using four IN4007 such as the simulation diagram connection, filtering circuit using capacitor filtering, voltage regulator circuit using series-type regulator circuit, that is, the integrated regulator LM317 to expand.
The simulation diagram is as follows:

![image](https://github.com/user-attachments/assets/952c204c-0d6b-4430-8c0a-5c9a49025c36)

![image](https://github.com/user-attachments/assets/26f9e655-274b-4684-997f-5054d857f3d7)


3. Calculate the value of each component: 

R2 (1kΩ): R2 = 1kΩ, LM317 voltage on both sides of the 1.25V, then the LM317 output current = 1.25V/1kΩ = 1mA. Because the load will also bear part of the current, the actual current out of the LM317 will certainly be greater than 1mA.

R1, R3 (10kΩ, 11.2Ω): Calculation formula U0 = (1 + R / R2) * Uref, Uref for the LM317 voltage that is 1.25V, the requirements of the U0 change of 3 - 9V, if you select the R2 to take 1kΩ, the final selection of R1 for 10kΩ, R3 for 11.2Ω.

C1, C2, C3, C4 (330uF, 470uF, 0.33uF): capacitance for the elimination of high-frequency noise, reduce ripple voltage, eliminate self-excited oscillation.

D (are selected IN4004): D role is to make C2 does not discharge through the regulator, you can protect the LM317, its withstand voltage value of 400v to meet the requirements.

D (IN4007): single-phase bridge rectifier, check the information selected IN4007, withstand voltage value of 1000V, to meet the requirements.

Transformer: 220v to 12v AC, power 10w. ignored UI = (2~3) Uo, the actual should choose a larger output voltage that the power of the transformer.


# II. Each part of the unit circuit design
1. Power transformer:

![image](https://github.com/user-attachments/assets/f79f812f-1e5f-40ea-aca8-b84706a29b8e)


2. Rectifier circuit: (single-phase bridge rectifier circuit)

![image](https://github.com/user-attachments/assets/9e7819d2-3870-4aa5-b337-d247d883337f)


3. Filter circuit (capacitor filter):

![image](https://github.com/user-attachments/assets/f360a1af-2f2d-483f-a3fc-4dd044f0f5e5)
After filtering, the average value of output voltage increases and the pulsation becomes smaller.


# III. System simulation

![image](https://github.com/user-attachments/assets/66344552-7510-4c2a-b491-30a85c92fa6d)


# IV.System debugging 

When the slide resistor is slid to the rightmost end, the output voltage is 9.17V and the output current is 0.82A;

When the slide resistor slides to the leftmost, the output voltage is 1.25V, the output current is 0.11A;

And when the slide varistor slides to the middle of any position, the output voltage can be taken as any value of 3 - 9V, the output current also meets the requirements.


# V. Measured results

![image](https://github.com/user-attachments/assets/e09f582c-1d77-40f6-b720-90961332ac70)

![image](https://github.com/user-attachments/assets/cc626fae-34fd-4993-87e9-c258ff2ed561)


# VI. Photographs of the real thing

![image](https://github.com/user-attachments/assets/55277db9-087e-4bb9-a89e-159ae76bfb1a)

![image](https://github.com/user-attachments/assets/1d42cb16-06ff-40b9-aaef-ca8336a449cc)

