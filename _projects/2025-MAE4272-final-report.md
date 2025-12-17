---
layout: project
title: Final Design Report 
Group: Izzy Cowan, Joseph Nadol, Joseph Rachiele, Lila Tauzin-Fox
technologies: [MATLAB, Fusionn360]
image: /assets/images/cad-model.png
---
**Executive Summary**

This project focused on the design, fabrication, and experimental evaluation of small wind-turbine blades optimized for safe operation and maximum power extraction under constrained operating conditions. The blades were designed to operate at a fixed rotational speed of 1500 RPM under a mean free-stream velocity of 4.59 m/s, while satisfying geometric and safety constraints. 

<figure align="center">
  <img src="{{ site.baseurl }}/assets/images/setup.png" alt="testing setup" width="400">
  <figcaption>
    <strong>Figure 1:</strong> Complete Test Setup Mounted to the Nacelle
  </figcaption>
</figure>

Safety considerations guided all design choices. From Lab 5 and in class analysis, the dominant failure modes were identified to be flapwise bending fracture and uncontrolled overspeeding due to torque brake failure. A blade length of 4 inches was selected to maintain acceptable factors of safety for both failure modes. At the target rate of 1500RPM and upper-bound free-stream velocity of 7.74 m/s, our length selection maintained a factor of safety of 1.24 with respect to the torque brake limit and 10 with respect to flap wise bending. While our conservative design ensured structural integrity, it severely diminished power outputs. 

We performed aerodynamic optimization calculations on the NACA 4412 airfoil at a Reynold’s number of approximately 50,000. The blade twist distribution was optimized to maintain an angle of attack of 8.5 degrees, which corresponds to the maximum lift-to-drag ratio for this airfoil. 
Experimental testing was conducted in a wind tunnel across three wind speeds: 4.3 m/s, 5.5 m/s, and 6.1 m/s. Torque and power output were measured as a function of rotational speed. Peak power occurred at approximately 800 RPM, 1100 RPM, and 1250 RPM for the three wind speeds, respectively. While the experimental power levels deviated greatly from theoretical predictions, at lower rotational speeds actual behavior trends closely matched the theoretical. No structural damage or deformation was observed during testing. The results highlight the importance of refining your engineering model to account for internal system friction. 

**Context, Objectives, and Constraints**

The objective of this project was to design wind turbine blades that maximized power output at a certain rotation rate while maintaining safe operating conditions. One of the design requirements was a maximum allowable rotational speed of 2000 RPM. Our group selected to optimize our blade design for a rotational rate of 1500 RPM because it maintained a 25% margin below the limit while ensuring a high enough tangential velocity to keep the inflow angle stable. 

We used the Weibell speed distribution bell curve to model the wind speed distribution. From this extrapolation we calculated a mean free-stream velocity of 4.59 m/s, an upper bound of 7.74 m/s and a lower bound of 1.43 m/s at three standard deviations away from our mean. These values informed the original experimental testing plan and power output expectations.

The constraints on the geometry of the blade design were minimal.  The hub radius had to be 1 inch to ensure the blades could properly attach and the maximum blade length was 6 inches which our design obliged by choosing a 4-inch blade length. 

<figure align="center">
  <img src="{{ site.baseurl }}/assets/images/cad-model.png" alt="testing setup" width="400">
  <figcaption>
    <strong>Figure 2:</strong> CAD Model of Blade (with dimensions in inches)
  </figcaption>
</figure>

**Design Process and Rationale**

Our main design concern for this experiment was safety. Given the catastrophic failure demonstrated in Lab 5, we wanted to design a blade that would remain intact, be safe, and optimize lift and power. Our group identified the two most likely failure modes to be: 1) fracture or failure due to flapwise bending and 2) torque brake failure leading to a runaway condition. 
To avoid any fracture and torque brake failure, we decided to limit the amount of torque imparted by the wing by limiting its blade length to 4 inches. The smaller blade length would not only decrease the torque but also decreases the chance of uncontrolled overspeeding of the turbine blade.

Another general aspect of the design process was picking a suitable airfoil and angle of attack. For the airfoil cross section, we decided to choose the well established NACA4412 airfoil. This design choice was made because of the extensive research done on this airfoil but also because it was used in previous labs and known to work well under this wind tunnel’s operating range. We then wanted to discover which angle of attack with our airfoil would be optimal. To do this we first calculated a Reynold’s number of our test airfoil and got a result of ~45,000. Then, we were able to reference data from studies done on NACA4412 with a Reynold’s number of 50,000:

<figure align="center">
  <img src="{{ site.baseurl }}/assets/images/cl-cd.png" alt="testing setup" width="400">
  <figcaption>
    <strong>Figure 3:</strong> CL/CD vs  (source: Airfoiltools.com) 
  </figcaption>
</figure>

As displayed on the figure above, CL/CD is optimized around 8.5 degrees angle of attack. A high CL/CD  is important because this would help our design maximize lift and power through safe methods. Thus, our group chose the 8.5 degree angle of attack.

**Experimental Methodology** 

In order to test whether our printed blades matched our performance expectations, we designed our experimental protocol with the goal of producing several power curves to represent a performance across a range of wind speeds across the Weibell speed distribution bell curve.

Although we did not expect any damage to our blades due to the safety considerations we took into account throughout the design process, we started by taking pictures to document the starting state of the blades. Next, we attached the turbine blades onto the hub, using putty to secure them, and pressed them into place as flush to the flat side of the hub as possible. The hub was then screwed onto the fixture on the interior of the wind tunnel. We also took pictures of the experimental setup so we could justify that our blades were oriented correctly.

We followed safety precautions throughout the experimental procedure by carefully monitoring telltale quantities. If at any point the blade RPM reported by the LabView Virtual Instrument (VI) went above 2500 RPM, we would immediately hit the emergency stop button to stop the wind tunnel. In addition, if at any point the reported torque produced by the blades reached 3.5 N-cm, we would immediately decrease wind speed to prevent torque brake failure and a potential runaway condition.
All equipment being used to measure turbine performance properties was zeroed using the LabView VI. We then used the wind tunnel fan frequency controls to attempt to slowly ramp up the wind speed in the tunnel, targeting a turbine RPM of 1500. We soon realized that the internal resistance of the system was greater than expected and that we would need to adjust our target wind speeds and shift the range of speeds higher in order to overcome the resistance and get the turbine to spin.

Our adjustments led us to choose target wind speeds of 4.3 m/s, 5.5 m/s, and 6.1 m/s. For each wind speed, we first set the torque brake applied voltage to 0, then carefully ramped the wind tunnel fan frequency up to reach the target speed. We allowed approximately 30 seconds to allow flow to reach a steady state before taking an initial data point. We then applied the torque brake in small increments of 0.2 V, 0.3 V, or 0.5 V for each wind speed, respectively, which allowed us to gather approximately the same number of data points for each wind speed. After each adjustment to the torque brake, we again allowed approximately 30 seconds before taking data to allow the flow to steady.

After all data was collected, we ramped the wind speed back down to 0 before removing our turbine from the wind tunnel fixture and carefully prying the blades from the hub. We took pictures of the blades again to compare with the initial photos taken.

**Results and Discussion**

Experimental testing was conducted at three free-stream wind speeds—4.3 m/s, 5.5 m/s, and 6.1 m/s—to characterize the performance of the designed wind turbine blade under controlled conditions. For each wind speed, torque and power were measured as functions of rotational speed by incrementally applying the torque brake once the turbine reached steady operation.

At a wind speed of 4.3 m/s, peak power was observed at approximately 800 RPM, as shown by the measured power–RPM curve. Both torque and power increased with decreasing RPM until reaching a maximum, after which power declined due to increased aerodynamic loading and flow separation effects. This peak occurred substantially below the originally targeted operating speed of 1500 RPM.

<figure align="center">
  <img src="{{ site.baseurl }}/assets/images/toruevr.png" alt="testing setup" width="400">
  <figcaption>
    <strong>Figure 4:</strong> Torque and power graphs at freestream of 4.3 m/s 
  </figcaption>
</figure>

At 5.5 m/s, the peak power shifted upward to approximately 1100 RPM, reflecting the increased available kinetic energy in the flow. The torque–RPM relationship exhibited a smoother increase compared to the lowest wind speed, while the power curve showed a broader maximum, indicating a wider operating range near peak efficiency.

<figure align="center">
  <img src="{{ site.baseurl }}/assets/images/torque51.png" alt="testing setup" width="400">
  <figcaption>
    <strong>Figure 5: </strong> Torque and power graphs at freestream of 5.5 m/s
  </figcaption>
</figure>

At the highest tested wind speed of 6.1 m/s, peak power occurred near 1250 RPM. While the maximum measured power increased significantly relative to the lower-speed cases, the power drop-off at reduced RPM became noticeably steeper. This trend suggests that, at higher wind speeds, deviations from the optimal tip-speed ratio more rapidly degrade aerodynamic performance.

<figure align="center">
  <img src="{{ site.baseurl }}/assets/images/torquevr2.png" alt="testing setup" width="400">
  <figcaption>
    <strong>Figure 6:</strong> Torque and power graphs at freestream of 6.1 m/s
  </figcaption>
</figure>

Across all cases, the experimental results demonstrate a consistent shift in peak power toward higher RPM as wind speed increases, which aligns with expected turbine scaling behavior. However, in all cases the measured peak RPM fell below the design target of 1500 RPM.
The blade was originally designed to achieve peak power output of approximately 0.202 W at 1500 RPM under a mean free-stream velocity of 4.59 m/s. While the experimentally measured power values were of the same order of magnitude as the theoretical predictions, the trajectories of the power curves differed substantially, particularly at higher torques and lower rotational speeds.

The theoretical model assumed a frictionless system, whereas the experimental apparatus exhibited significant internal resistance. Notably, the turbine did not begin rotating until the free-stream velocity reached approximately 7 m/s, well above the mean design velocity. This indicates that static friction and parasitic losses within the drivetrain imposed a substantial breakaway torque requirement.

At high torque and low RPM conditions, theoretical and experimental power values were relatively close, suggesting that parasitic losses are less dominant at lower rotation speeds, since most internal frictional losses have a power-law relationship with rotational velocity. Once our blade reached higher speeds however, the internal losses began to dominate and limited the amount of power our blade could output relative to the theoretical graph.

<figure align="center">
  <img src="{{ site.baseurl }}/assets/images/theoretical.png" alt="testing setup" width="400">
  <figcaption>
    <strong>Figure 7:</strong> Theoretical vs. actual power curves for two of our freestream conditions. The experimental graph stays close to the theoretical at low RPMs before ultimately diverging as frictional losses begin to dominate.
  </figcaption>
</figure>

**Reflection and Conclusion**

As reported in the results section, the power produced by our wind turbine was significantly lower than expected, which we attributed mostly to frictional losses and internal resistance of the system. This demonstrated a significant oversight in our model. If we were to redo this design project, we would attempt to model internal resistance. This could likely be accomplished using an experimental model developed using a blade whose properties are well-known. This model might involve an initial friction that must be overcome to start spinning and subsequent frictional forces as a function of key quantities such as RPM. That way, we could apply this model to our theoretical calculations for our blade and get a better idea of the power it is capable of producing and the possible operating wind speeds. It might even be possible to safely make the blade longer without overcoming the torque brake limit given the model of internal friction.

Another change we might consider if we were to do the design project again is choosing a different RPM for our peak power. Choosing a higher RPM would allow for a lower torque with the same power, which would allow for a larger blade geometry without reaching the torque brake limit. The breakaway torque in order to get the blade spinning may still be an issue in this case, but we could consider including a portion of the blade with a lower angle of attack to help the blade start spinning at a lower wind speed. The downside of this would be increased drag.

Through this project, we were able to get an idea of the real-life obstacles of wind turbine design that are not necessarily quantifiable by a well-known mathematical model or law presented in class. We successfully designed a safely-operating blade, gathered meaningful data, and reflected on our results while identifying shortcomings of our design and experimental process.


