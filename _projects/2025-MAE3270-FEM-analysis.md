---
layout: project
title: MAE 3270 Final Assignment
description: CAD and FEM Project
technologies: [Matlab, Autodesk Fusion, ANSYS]
image: /assets/images/cover.png


---


For my Mechanics of Materials course we were asked to design a non-ratcheting, 3/8 inch drive instrumented torque wrench rated for 600 in-lbf. The torque was transduced by strain gauges on the sides of the torque wrench. The design goal was to maximize the voltage output of the wrench (mV/V) at the rated torque while designing for a safety factor of Xo = 4 for yield, Xk = 2 for crack growth and Xs = 1.5 for fatigue stress.


I chose to make my wrench out of the titanium alloy Ti-3Al-2.5V. I then performed iterative calculations in Matlab to determine the proper geometry to ensure these design requirements were meant. Once I found the correct geometry, I created the design in Autodesk Fusion. I simulated the force and boundary conditions in ANSYS to determine how my hand calculations held up against results from the finite element method.    


1. Image(s) of CAD model. Must show all key dimensions.
![The San Juan Mountains are beautiful](/assets/images/wrenhlength.png)
![The San Juan Mountains are beautiful](/assets/images/wrenchhead.png )


2. Describe material used and its relevant mechanical properties.
![The San Juan Mountains are beautiful](/assets/images/table.png)


3. Diagram communicating how loads and boundary conditions were applied to your FEM Model.
![The San Juan Mountains are beautiful](/assets/images/loaddiagram.png)


4. Normal strain contours (in the strain gauge direction) from FEM
![The San Juan Mountains are beautiful](/assets/images/strain.png)


5. Contour plot of maximum principal stress from FEM
![The San Juan Mountains are beautiful](/assets/images/maxprincipal.png )
![The San Juan Mountains are beautiful](/assets/images/maxclose.png
)


6. Summarize results from FEM calculation showing maximum normal stress, load point deflection, strains at the strain gauge locations
![The San Juan Mountains are beautiful](/assets/images/results.png)


7. Torque wrench sensitivity in mV/V using strains from the FEM analysis
From FEM analysis the wrench sensitivity is 1.46 mV/V. From hand calculations the wrench sensitivity was 1.30 mV/V.


8. Strain gauge selected.
I chose the BF( BA/BE)350-2BB. This model is a half-bridge strain gauge with 90 degree rosettes. They are used in problems where the direction of the principal stress is known. The dimensions were 6.3mm × 7.6mm which fit with on the side of my wrench design.
![The San Juan Mountains are beautiful](/assets/images/straingauge.png)
