---
layout: project
title: MAE 3270 Final Assignment
description: CAD and FEM Project
technologies: [Matlab, Autodesk Fusion, ANSYS]
image: /assets/images/cover.png


---

For my Mechanics of Materials course we were asked to design a non-ratcheting, **3/8 inch** drive instrumented torque wrench rated for **600 in-lbf**. The torque was transduced by strain gauges on the sides of the torque wrench. The design goal was to maximize the voltage output of the wrench (mV/V) at the rated torque while designing for a safety factor of **Xo = 4** for yield, **Xk = 2** for crack growth and ****Xs = 1.5** for fatigue stress.


I chose to make my wrench out of the titanium alloy **Ti-3Al-2.5V**. I then performed iterative calculations in Matlab to determine the proper geometry to ensure these design requirements were meant. Once I found the correct geometry, I created the design in Autodesk Fusion. I simulated the force and boundary conditions in ANSYS to determine how my hand calculations held up against results from the finite element method.    

<u>Image(s) of CAD model.</u> 

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/wrenchlength.png" alt="Side view of wrench CAD model" width="500">
</p>

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/wrenchhead.png" alt="Wrench head close-up" width="450">
</p>


<u>Describe material used and its relevant mechanical properties.</u>

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/table.png" alt="Material properties table" width="600">
</p>


<u>Diagram communicating how loads and boundary conditions were applied to your FEM Model.</u>

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/loaddiagram.png" alt="Load and boundary condition diagram" width="600">
</p>


<u>Normal strain contours (in the strain gauge direction) from FEM </u>

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/strain.png" alt="Strain contour plot" width="600">
</p>


<u>Contour plot of maximum principal stress from FEM</u>

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/maxprincipal.png" alt="Maximum principal stress plot" width="600">
</p>

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/maxclose.png" alt="Maximum principal stress close-up" width="500">
</p>


<u>Summarize results from FEM calculation showing maximum normal stress, load point deflection, strains at the strain gauge locations </u>

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/results.png" alt="FEM results summary" width="600">
</p>


<u>Torque wrench sensitivity in mV/V using strains from the FEM analysis </u>

From FEM analysis the wrench sensitivity is **1.46 mV/V**.  
From hand calculations the wrench sensitivity was **1.30 mV/V**.


<u> Strain gauge selected.</u>

I chose the BF(BA/BE)350-2BB. This model is a half-bridge strain gauge with 90° rosettes. They are used in problems where the direction of the principal stress is known.  
The dimensions were **6.3 mm × 7.6 mm**, which fit on the side of my wrench design.

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/straingauge.png" alt="Selected strain gauge" width="350">
</p>
