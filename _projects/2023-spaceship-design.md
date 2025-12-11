---
layout: project
title: MAE 3260 Final Group Work
description: Dissecting a drill
image: /assets/images/drill.JPG
---

For my part of the final group work, I made the block diagrams for our open-loop & closed-loop models and analyzed how the drill rejects the effects of disturbance torque.

<div style="clear: both;"></div>

### Open loop block diagram
<p align="center">
  <img src="{{ '/assets/images/open_loop.png' | relative_url }}" width="800">
</p>

### Closed loop block diagram
<p align="center">
  <img src="{{ '/assets/images/closed_loop.png' | relative_url }}" width="800">
</p>

### Disturbance Analysis
In this section, I analyze how the drill responds when an external disturbance torque is applied at the chuck during drilling. The disturbance enters the system as a load torque T_L(t) acting opposite to the motor’s electromagnetic torque. Physically, T_L(t)  represents the resistance the bit experiences when it engages with a material, causing the drill speed to sag. By incorporating this disturbance into the same plant dynamics used in the open and closed loop models, I can examine how feedback alters the system’s ability to maintain a constant speed under load. This setup allows direct comparison between the uncontrolled drill, where load torque causes significant speed drops, and the controlled drill, where feedback counteracts the disturbance by increasing motor input to restore the desired speed.

### Derivation
<p align="center">
  <img src="{{ '/assets/images/derivation.jpg' | relative_url }}" width="800">
</p>

The disturbance transfer function shows that the drill behaves as a first-order system whose speed drops proportionally to the applied load torque. In an open loop, this term directly determines both the transient response and the steady-state error, meaning any increase in T_L ​ produces a persistent decrease in speed. 
<img src="images/disturbance.png"
     alt="Gd(s)/(1 + C(s)Gu(s)) TL(s)"
     style="height: 30px; vertical-align: middle;"> 
When feedback is added, the disturbance path becomes

As this loop gain increases, the disturbance sensitivity decreases, indicating that the controller should restore the speed more quickly and with smaller steady-state deviation. 

### Results
Although we did not test the closed-loop model in the lab, the disturbance effects could be evaluated using an optical tachometer to record the drill’s angular velocity over time. From this data, we could estimate the mechanical time constant tau = J / b and compare it to the model. Measuring the steady-state speed drop under a known applied torque would provide an experimental estimate of the disturbance transfer function G_d ​(s). Furthermore, observing how a controller reduces this speed drop would validate the predicted closed-loop disturbance response.


