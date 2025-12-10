---
layout: project
title: MAE 3260 Final Report- Biology’s Beating Block Diagram
 
description: Just a spaceship that I designed
technologies: 
image: /assets/images/blockdiagram.png
---
Abstract

This report models the human heart as a feedback-controlled system using a Windkessel equation for arterial pressure, which models the heart as a circuit, along with a heart-rate regulation model. We selected the heart because it clearly connects biological function with system dynamics and control principles. The model uses arterial pressure and heart rate as states, nervous-system drive as the input, and average pressure and heart rate as outputs. We analyze how changes in key parameters represent cardiovascular diseases such as hypertension, heart failure, and diabetes, and examine how these conditions alter the system’s ability to regulate blood pressure and maintain effective cardiac output.

ODE and State-Space Representation
 
To simplify the state-space representation of the heart, we chose to analyze just one chamber of the heart- the left aorta. The 4-Module Windkessel Model maps the complexities of the cardiovascular system to components of a simplified electrical circuit. It provides an electrical representation of the volumetric flow and pressure behavior in the left aorta. This model makes the lumped parameter assumption that there is uniform pressure and uniform flow. It also assumes a linear relation between pressure and the arterial resistance, compliance, and blood mass. These main assumptions informed the development of the circuit analogy below.

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/Circuit.png" alt="4-Module Windkessel Model" width="500">
</p>

P in the circuit represents the pressure coming from the left ventricle after the valve is opened. The valve is not modeled. The details of this electrical analogy are outlined in the table below. 

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/state-space-table.png" alt="Cardiovascual-Electrical analogy table" width="500">
</p>

Component Relations: 

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/comps.png" alt="Electrical and cardiovascular equations" width="500">
</p>

From applying Kirchoff’s Current Law to the node: 

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/flow-equation.png" alt="Kirchoff's current law" width="500">
</p>

From applying Kirchoff’s Voltage Law: 

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/kirchoffs.png" alt="Electrical and cardiovascular equations" width="500">
</p>

We will choose a 2-state space representation:

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/state-choice.png" alt="2-State decision" width="500">
</p>

We will choose our output to be the arterial pressure for the sake of modeling this problem, but volumetric flow is also another possible output. 

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/ouput.png" alt="Output equation" width="500">
</p>

This yields the state representation below: 

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/state-rep.png" alt="State space representation" width="500">
</p>

**Diseases**

Introduction

There are many cardiovascular diseases out there that affect how the human heart maintains homeostasis through regulating heart rate and blood pressure. They often disrupt finely tuned mechanisms that keep the human body stable. Such cardiovascular diseases, such as high blood pressure, coronary artery disease, and Arrhythmias, change the mechanical and physiological properties of the heart and its blood vessels, leading to a variety of problems, including reduced pumping efficiency, increased vascular resistance, and problems with autonomic regulation. 

These changes can be understood through a systems perspective, where small changes in parameters such as arterial capacitance, stroke volume, and baroreflex sensitivity produce meaningful shifts in system behavior. By examining these diseases through a dynamical model, we can quantify how pathological conditions modify the heart’s response to disturbances and weaken overall cardiovascular performance.

Coronary Heart Disease

This is one of the most common cardiovascular diseases present throughout the world. It occurs when your arteries cannot supply enough oxygen to the heart, causing a variety of problems. This usually occurs when plaque, otherwise known as fatty deposits, literally builds up in the artery, reducing the amount of area that the blood can flow through. If left untreated, this can lead to serious health implications such as heart pain or, in the worst case, cardiac arrest and even death.

Relating this to our model, coronary heart disease can be represented through changes in parameters that reduce the total blood supply and impaired cardiac performance. Plaque buildup in the arteries essentially narrows the path that the blood flows in, effectively increasing the resistance, R, making it harder for blood to leave the arteries, which also increases the pressure needed to maintain flow. Reduced oxygen delivery to the heart muscle also weakens its ability to contract, which decreases the volume, V. Combining all these parameters reduced how much blood flows in, Qin. This can create unstable or delayed responses after disturbances. By examining how the pressure and heart rate trajectories change when the Volume decreases and Resistance increases, the model predicts that there will be a reduction in pumping efficiency and heightened workload on the heart/arteries associated with coronary heart disease.

High Blood Pressure

High Blood Pressure, also known as Hypertension, is one of the cardiovascular conditions that affects how your heart functions. It occurs when the force of the blood against the arterial walls is way too high, which can lead to damage in the blood vessels and lead to other serious cardiovascular diseases.

Relating this to our model, high blood pressure is captured through parameters in our Windkessel equation of the cardiovascular system. The Windkessel equation is as follows dPdt=Q-PC, where Q is blood flow, P is blood pressure, and C is the capacitance. In our case, capacitance describes how easily the arteries expand when blood flows through them. It is modeled as C = VP, so having a higher capacitance means that the arteries expand quickly while the pressure rises more slowly.  Having higher pressure in the arteries increases what P is, and also decreases what the Capacitance is. Having a lower capacitance results in the same flow, resulting in a much larger rise in pressure, leading to an elevated arterial pressure. Often, having higher pressure also increases resistance, making it harder for blood to leave the arteries.

Arrhythmias

Arrhythmias are abnormal heart rhythms where the heart beats irregularly, either too fast, too slow, or a mix of both, due to a problem with the heart’s electrical system. Some possible symptoms include dizziness and shortness of breath, which can be treated with devices such as medications or a pacemaker to control this rhythm.

Relating this to our model: 

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/hr-eq.png" alt="Material properties table" width="600">
</p>

We can see how arrhythmias change how the system behaves in several ways. First of all, they alter the baseline heart rate and heart rate in general, changing the HR value and can slow down the heart’s response to certain triggers, effectively increasing the time constant 𝜏HR.  Also, they weaken the baroreflex recoupling, meaning Kb it becomes smaller, and thus the pressure of the artery will have a lesser influence on correcting the heart rate.

Arrhythmias make the overall heart rate irregular, adding disturbance noise that is not represented in the normal linear equation. This overall makes the heart rate, HR, unpredictable and fluctuates despite the feedback control. Overall, arrhythmias reduce the model’s ability to regulate heart rate smoothly and weaken the connection between pressure regulation and autonomic control.

Conclusion

Cardiovascular diseases fundamentally alter how the heart and the overall system maintain stability, and these effects become clearer when interpreted through a systems-modeling framework with equations. 

**Devices: Pacemaker**

Original ODE

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/originalode.png" alt="Original ODE" width="600">
</p>

Pacemaker ODE:

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/pacemaker.png" alt="Pacemaker ODE" width="600">
</p>

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/equationrelations.png" alt="Pacemaker ODE" width="600">
</p>

With the addition of a pacemaker, our model of the heart has an extra component added:

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/addedcomp.png" alt="Pacemaker ODE" width="600">
</p>

**Performance Metric**

All values listed below are average values for a healthy 25-year-old male.

Resting Heart Rate: 60 < HR < 80 BPM
Resting Blood Pressure: 119/70 mmHg
Resting Volumetric Flow Rate: 5 < Q < 6 Liters/Minute 

Block Diagram:
State Variables: [P(t)=Arterial Blood Pressure; HR(t) = Heart Rate]
Input u(t)= Pacemaker Stimulation
Output: [P(t)=Arterial Blood Pressure; HR(t) = Heart Rate]

For this block diagram we will utilize a PI controller in a closed-loop system. By utilizing a PI controller, we create a feedback loop that works to eliminate the effect of any disease or stimulation. This is done through the initial input of a pacemaker and then utilizes the feedback loop to ensure a quick response time to steady state, as well as no steady state error. This is extremely important when looking at a response to stimulation in the human heart, as sudden jumps in blood pressure and heart rate pose dangerous implications to the person and must be corrected before any permanent damage occurs. 

<p align="center">
  <img src="{{ site.baseurl }}/assets/images/blockdiagram.png" alt="Pacemaker ODE" width="600">
</p>

In utilizing a PI response, we will determine the parameters in order to determine a proper controller. The step response time of a pacemaker is around 1 second, and the steady-state error needs to be zero in order to have a precise correction (Fearnot). With these parameters set we can now determine the controller. K(S)=​​Kp+Ki/s
Ts=1.8n This leads to a natural frequency of 1.8 radians per second. If we assume a settling time of 3 seconds, we can determine the damping coefficient using Tr=4n* which leads to a damping coefficient of 0.75. Finally we are going to determine Kp and Ki using the equation s2+2.7s+3.24=s2+(1+Kp)s+Ki. Therefore, the design controller is Ki=3.24 and Kp=1.7.

**Sources**

Creigen, V., Ferracina, L., Hlod, A., Van Mourik, S., Sjauw, K., Rottschäfer, V., Vellekoop, M., Zegeling, P., CWI, Technische Universiteit Eindhoven, Technische Universiteit Twente, AMC, Universiteit Leiden, & Universiteit Utrecht. (2019). Modeling a heart pump [Journal-article].

FEARNOT, NEAL E., and MERRY LEE EVANS. “Heart Rate Correlation, Response Time and Effect of Previous Exercise Using an Advanced Pacing Rate Algorithm for Temperature-Based Rate Modulation.” Pacing and Clinical Electrophysiology, vol. 11, no. 11, Nov. 1988, pp. 1846–52, https://doi.org/10.1111/j.1540-8159.1988.tb06319.x.
