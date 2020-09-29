---
layout: page2
title: 	Using Neural Networks for Simultaneous and Proportional Estimation of Upper Arm Kinematics
permalink: /emg/
description: Machine Learning
tags: [Jekyll, theme, responsive, blog, template]
image:
  feature:
---
Supervisor: Dr. Tracey Camilleri (University of Malta)\
Co-supervisor: Dr. Marvin Bugeja (University of Malta)

<br>**Project description**
<p align="justify"> This work compares the use of three different artificial neural networks (ANNs) to estimate shoulder and elbow kinematics using surface electromyographic (EMG) signals for proportional and simultaneous control of multiple degrees of freedom (DOFs). The three different networks considered include a multilayer perceptron (MLP) neural network, a time delay neural network (TDNN), and a recurrent neural network (RNN). <br><br>

<p align="justify"> In each case, surface EMG signals from agonist and antagonist arm muscles detected during seven different movements, three of which involve the simultaneous activation of the shoulder and elbow, were used as inputs to the neural networks. The three configurations were trained to estimate angular displacements of the shoulder and/or elbow. The average correlation coefficient (CC) between the true and the estimated angular position for simultaneous movements for the elbow and shoulder combined was 0.866 +- 0.050 when using the MLP structure, 0.830 $\pm$ 0.130 for the TDNN structure and 0.840 +- 0.058 when using the RNN architecture. These results show that all three neural networks are plausible alternatives to model the EMG to joint angle relationship of the upper arm with the MLP being the most computationally efficient option. <br><br>

<p align="justify"> In order to keep computational time as low as possible, the lowest possible number of EMG input sources were considered for each movement. This is important because an increase in the number of electrodes would result in an increase in power consumption and cost of the assistive device. When tested in real-time, the robotic arm followed the user's wrist position with a constant delay of 500ms, which was due to the delay in the transfer protocol from the wireless EMG transmitters to the robotic arm. The MLP was able to handle real-time data with no bottleneck at 10Hz, which is more than enough to produce a responsive device. <br><br>

<p align="center">
  <img src="https://github.com/cgre23/cgre23.github.io/blob/master/images/Muscles2.JPG?raw=true" width="280" title="Electrode placement">
  <img src="https://github.com/cgre23/cgre23.github.io/blob/master/images/Application.JPG?raw=true" width="335" alt="Robotic Arm Application">
</p>
Figure 1: Electrode and position marker placement  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   Figure 2: Application of the framework on a Robotic Arm
