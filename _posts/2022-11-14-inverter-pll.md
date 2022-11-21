---
layout: post
title: Single Phase Hybrid Power System Simulation Using SOGI PLL
subtitle: An advanced PLL algorithm with fast response for single phase systems
thumbnail-img: /assets/img/pll.jpg
---
A SOGI PLL is a PLL control algorithm for on-grid inverters that enhances the feedback loop to be similar to that of 3-phase inverters and provides high response and stability for the syncing capablities of the inverter. In addition to that, the simulated system consisted of solar panels, back-up generator and the grid all connected together. This type of system can be used in remote areas where the grid is not reliable during a full day.

Generally in most 3-phase inverters, synchronization with the grid is achieved through transofrming the voltage signal to Alpha-Beta signals *(Clarke Transformation)* then to *dq0* signals *(dq0 Transform)*, and these signals would be used to synchronize the output signal with the input using a PLL. In case of single phase systems, it can't be achieved that easily due to the presence of one signal instead of three. So, one way of acquiring the alpha and beta components is by feeding the single phase signal into a Second Order Generalized Integrator *(SOGI)*.

![image](https://user-images.githubusercontent.com/52468587/201797091-38e99dcd-3c2e-4f3c-b8c5-20b2bae5b79c.png)

The output signals of the SOGI can then be used as the Alpha and Beta components needed to apply dq0 transformation. Then, the resultant signals are used as inputs to the PLL. The PLL output signal would be used as the refernce signal for the control of the inverter gates.

![image](https://user-images.githubusercontent.com/52468587/201798377-c80dfa68-8175-4756-835b-ce4fb16488fc.png)

The system can be simulated on any simulation software and I chose PLECS since it's easy to use and convenient. The simulation was executed for multiple scenarios but I will focus on the worst case scenario because it's the main goal of the project; synchronization between the solar panels and the generator. the load chosen for this simulation is about 5kW. The block diagram of the system is as follows

![image](https://user-images.githubusercontent.com/52468587/201801645-50186e74-8905-45e6-a42a-b39d0b646774.png)

The results down below show that the system takes few cycles to stabilize and after that, it holds normal values and small phase error.

![image](https://user-images.githubusercontent.com/52468587/201802212-1f4a7458-680a-4f63-b4ed-4f33c467399c.png)

![image](https://user-images.githubusercontent.com/52468587/201802305-1faf4cd6-3216-4729-8817-eadfa5a3135d.png)


