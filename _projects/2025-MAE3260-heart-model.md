---
layout: project
title: MAE 3260 Final Report- Biology’s Beating Block Diagram
 
description: Just a spaceship that I designed
technologies: 
image: /assets/images/blockdiagram.png
---

Edison Chen, Emily Radzio, Fred Weintzen, Lila Tauzin-Fox

Abstract

This report models the human heart as a feedback-controlled system using a Windkessel equation for arterial pressure—representing the heart as an electrical circuit—along with a heart-rate regulation model. We selected the heart because it clearly connects biological function with system dynamics and control principles.

The model uses arterial pressure and heart rate as states, nervous-system drive as the input, and average pressure and heart rate as outputs. We analyze how changes in key parameters represent cardiovascular diseases such as hypertension, heart failure, and diabetes, and examine how these conditions alter the system’s ability to regulate blood pressure and maintain effective cardiac output.

ODE and State-Space Representation

To simplify the state-space representation of the heart, we analyze just one chamber: the left aorta. The 4-Module Windkessel Model maps cardiovascular behavior to an analogous electrical circuit using lumped-parameter assumptions:

Uniform pressure and flow

Linear relations between pressure, resistance, compliance, and blood inertia

Electrical–Physiological Correspondence
Cardiovascular Quantity	Electrical Analog
Blood volume	Electrical charge
Volumetric flow rate 
𝐹
F	Current 
𝐼
I
Pressure 
𝑃
P	Voltage 
𝑉
V
Vessel resistance (
𝑅
𝑎
,
𝑅
𝑝
R
a
	​

,R
p
	​

)	Electrical resistance 
𝑅
R
Vessel compliance 
𝐶
C	Capacitance 
𝐶
𝑒
C
e
	​


Blood inertia 
𝐿
L	Inductance 
𝐿
𝑒
L
e
	​

Key Relations
𝐿
𝑑
𝐹
𝑑
𝑡
=
𝑃
L
dt
dF
	​

=P
𝐶
𝑑
𝑃
𝑎
𝑑
𝑡
=
𝐹
C
dt
dP
a
	​

	​

=F
𝐹
=
𝑃
𝑎
𝑅
𝑝
F=
R
p
	​

P
a
	​

	​

𝑃
−
𝑃
𝑎
=
𝑅
𝑎
𝐹
+
𝐿
𝑑
𝐹
𝑑
𝑡
P−P
a
	​

=R
a
	​

F+L
dt
dF
	​

Kirchhoff’s Laws Applied

Current law at node:

𝐹
=
𝐶
𝑑
𝑃
𝑎
𝑑
𝑡
+
𝑃
𝑎
𝑅
𝑝
F=C
dt
dP
a
	​

	​

+
R
p
	​

P
a
	​

	​


Voltage law:

𝑃
−
𝑃
𝑎
=
𝑅
𝑎
𝐹
+
𝐿
𝑑
𝐹
𝑑
𝑡
P−P
a
	​

=R
a
	​

F+L
dt
dF
	​

State Selection

Let:

𝑥
1
=
𝑃
𝑎
(
𝑡
)
,
𝑥
2
=
𝐹
(
𝑡
)
x
1
	​

=P
a
	​

(t),x
2
	​

=F(t)

Output:

𝑦
(
𝑡
)
=
𝑃
𝑎
(
𝑡
)
y(t)=P
a
	​

(t)

A full state-space form can be written directly from the equations above.

Diseases
Introduction

Cardiovascular diseases disrupt the body’s ability to maintain homeostasis through pressure and heart-rate regulation. Changes in arterial compliance, stroke volume, and baroreflex sensitivity alter how the heart responds to disturbances.

Using a dynamical model reveals how pathological conditions modify stability, responsiveness, and overall cardiovascular performance.

Coronary Heart Disease

Atherosclerotic plaque buildup narrows arteries, reducing oxygen delivery and increasing resistance 
𝑅
R. In the Windkessel model:

Resistance 
𝑅
𝑎
,
𝑅
𝑝
R
a
	​

,R
p
	​

 increases

Flow 
𝑄
𝑖
𝑛
Q
in
	​

 decreases

Ventricular pressure generation weakens

This leads to delayed or unstable responses, reduced pumping efficiency, and higher workload on the heart.

High Blood Pressure (Hypertension)

Using the Windkessel differential equation:

𝑑
𝑃
𝑑
𝑡
=
𝑄
−
𝑃
𝐶
dt
dP
	​

=
C
Q−P
	​


Where 
𝐶
=
Δ
𝑉
Δ
𝑃
C=
ΔP
ΔV
	​

 is arterial compliance.

Hypertension effects:

Increased 
𝑃
P

Reduced compliance 
𝐶
C

Higher resistance → larger pressure rise for the same flow

This produces chronically elevated arterial pressure and reduced damping of pulsatile flow.

Arrhythmias

Arrhythmias arise from disruptions in the heart’s electrical rhythm.

Given the heart rate model:

𝑑
𝐻
𝑅
𝑑
𝑡
=
−
1
𝜏
𝐻
𝑅
𝐻
𝑅
+
𝐻
𝑅
0
𝜏
𝐻
𝑅
+
𝐾
𝑏
𝜏
𝐻
𝑅
(
𝑃
𝑠
𝑒
𝑡
−
𝑃
𝑎
)
+
1
𝜏
𝐻
𝑅
𝑢
𝑝
(
𝑡
)
dt
dHR
	​

=−
τ
HR
	​

1
	​

HR+
τ
HR
	​

HR
0
	​

	​

+
τ
HR
	​

K
b
	​

	​

(P
set
	​

−P
a
	​

)+
τ
HR
	​

1
	​

u
p
	​

(t)

Arrhythmias:

Alter baseline HR values

Increase time constant 
𝜏
𝐻
𝑅
τ
HR
	​

 → slower responses

Reduce baroreflex gain 
𝐾
𝑏
K
b
	​

 → weaker pressure–HR coupling

Add irregular disturbances not captured by a linear model

These effects degrade regulation and lead to unstable heart-rate dynamics.

Conclusion

Cardiovascular diseases alter key parameters of the system model—resistance, compliance, stroke volume, baroreflex gain—and therefore change the system’s ability to maintain stable blood pressure and heart rate. Modeling these effects through differential equations and feedback loops highlights their impact on the dynamics of cardiovascular regulation.

Device: Pacemaker

Original ODE:

𝑑
𝐻
𝑅
𝑑
𝑡
=
−
1
𝜏
𝐻
𝑅
𝐻
𝑅
+
𝐻
𝑅
0
𝜏
𝐻
𝑅
+
𝐾
𝑏
𝜏
𝐻
𝑅
(
𝑃
𝑠
𝑒
𝑡
−
𝑃
𝑎
)
+
1
𝜏
𝐻
𝑅
𝑢
𝑝
(
𝑡
)
dt
dHR
	​

=−
τ
HR
	​

1
	​

HR+
τ
HR
	​

HR
0
	​

	​

+
τ
HR
	​

K
b
	​

	​

(P
set
	​

−P
a
	​

)+
τ
HR
	​

1
	​

u
p
	​

(t)

With pacemaker:

𝑑
𝐻
𝑅
𝑑
𝑡
=
−
1
𝜏
𝐻
𝑅
𝐻
𝑅
+
𝐻
𝑅
0
𝜏
𝐻
𝑅
+
𝐾
𝑏
𝜏
𝐻
𝑅
(
𝑃
𝑠
𝑒
𝑡
−
𝑃
𝑎
)
+
1
𝜏
𝐻
𝑅
𝑢
𝑎
𝑢
𝑡
(
𝑡
)
+
1
𝜏
𝐻
𝑅
𝑢
𝑝
(
𝑡
)
dt
dHR
	​

=−
τ
HR
	​

1
	​

HR+
τ
HR
	​

HR
0
	​

	​

+
τ
HR
	​

K
b
	​

	​

(P
set
	​

−P
a
	​

)+
τ
HR
	​

1
	​

u
aut
	​

(t)+
τ
HR
	​

1
	​

u
p
	​

(t)

Where:

𝜏
𝐻
𝑅
τ
HR
	​

: HR time constant

𝐻
𝑅
0
HR
0
	​

: baseline heart rate

𝑃
𝑠
𝑒
𝑡
P
set
	​

: target arterial pressure

𝐾
𝑏
K
b
	​

: baroreflex gain

𝑢
(
𝑡
)
u(t): pacemaker stimulus

Adding the pacemaker adds a new control input into the feedback system.

Performance Metrics

Average healthy adult values:

Resting heart rate: 60–80 bpm

Blood pressure: 119/70 mmHg

Volumetric flow rate: 5–6 L/min

Block Diagram

States:

𝑃
(
𝑡
)
P(t): Arterial blood pressure

𝐻
𝑅
(
𝑡
)
HR(t): Heart rate

Input:

Pacemaker stimulation 
𝑢
(
𝑡
)
u(t)

Output:

𝑃
(
𝑡
)
P(t), 
𝐻
𝑅
(
𝑡
)
HR(t)

PI Controller Design

Using:

𝐾
(
𝑠
)
=
𝐾
𝑝
+
𝐾
𝑖
𝑠
K(s)=K
p
	​

+
s
K
i
	​

	​


Given:

Step-response rise time target: ~1 s

Settling time target: ~3 s

Zero steady-state error required

A natural frequency of 1.8 rad/s and damping ratio 
𝛿
=
0.75
δ=0.75 give:

𝑠
2
+
2.7
𝑠
+
3.24
=
𝑠
2
+
(
1
+
𝐾
𝑝
)
𝑠
+
𝐾
𝑖
s
2
+2.7s+3.24=s
2
+(1+K
p
	​

)s+K
i
	​


Thus:

𝐾
𝑝
=
1.7
K
p
	​

=1.7

𝐾
𝑖
=
3.24
K
i
	​

=3.24

These values ensure fast, well-damped, accurate pressure and HR regulation.

Sources

Creigen et al. Modeling a heart pump, 2019.
Fearnot & Evans. Heart Rate Correlation, Response Time and Effect of Previous Exercise…, 1988.

