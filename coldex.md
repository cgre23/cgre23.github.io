---
layout: page2
title: 	COLDEX New Data Acquisition Framework
permalink: /coldex/
description: Magnetic measurements
tags: [Jekyll, theme, responsive, blog, template]
image:
  feature:
---
Supervisor: Dr. Roberto Salemme (CERN)\
Co-supervisor: Cristovao Barreto (CERN)

<br>**Project description**
<p align="justify"> COLDEX (COLD bore EXperiment) is an experiment of the TE-VSC group installed in the Super Proton Synchrotron (SPS) which mimics a LHC type cryogenic vacuum system. In the framework of the High Luminosity upgrade of the LHC (HL-LHC project), COLDEX has been recommissioned in 2014 in order to validate carbon coatings performances at cryogenic temperature with LHC type beams. To achieve this mission, a data acquisition system is needed to retrieve and store information from the different experiment’s systems (vacuum, cryogenics, controls, safety) and perform specific calculations. This work aimed to completely redesign, implement, test and operate a brand new data acquisition framework based on communication with the experiment’s PLCs for the devices potentially available over network. The communication protocol to the PLCs is based on data retrieval both from CERN middleware infrastructures (CMW, JAPC) and on a novel open source Simatic S7 data exchange package over TCP/IP (libnodave). </p><br>


<p align="justify"> The data acquisition architecture for this project is shown in Figure 1 below. Data is collected from three PLCs (Vacuum PLC, Cryogenic PLC and COLDEX PLC), the SPS BCT (Beam Current Transformer), two RGAs (Residual Gas Analysers), two Keithley 2410 (High-Voltage Sourcemeter) and other devices which are not available on network, such as capacitance gauges. The NI PXIe-1082 acts as the system controller, as it is the central point to all the data being acquired from all the different devices. The Vacuum PLC manages the readings from several pressure gauges such as Pirani, Penning and Bayard-Alpert gauges. These gauges cover different ranges of pressure values. The Cryogenics PLC manages the readings from the cryogenic installation devices, belonging to the process (cold box, storage dewar) and to the COLDEX cryostat (cold bore vessel, beam screen, buffer, thermal shield). The COLDEX PLC monitors data on the status of the COLDEX movable stage and acquires analog inputs, such as the thermocouples of the WAMPAC calorimeter. </p><br>

<p align="center">
  <img src="https://github.com/cgre23/cgre23.github.io/blob/master/images/sensors.png?raw=true" width="700" title="Devices">
</p>
<p align="center"> Figure 1: Schematic of the device communication layout <br> <br>

<p align="justify"> The data acquisition framework is based on the LabVIEW design pattern of a Queued Message Handler, which provides a flexible and extendable programming. This design pattern is an extension of the producer-consumer pattern in which data is produced by an independently running loop, then sent via a message queue to a consumer loop which can handle the incoming data at its own pace. This allows modularization of the tasks performed by the software. The implementation of the data acquisition console uses four loops running in parallel, each performing a dedicated role within the application. Figure 2 illustrates an overview of this design. Four loops are running in parallel, each performing a dedicated task within the software. </p><br>

<p align="center">
  <img src="https://github.com/cgre23/cgre23.github.io/blob/master/images/qmh.png?raw=true" width="500" title="Design">
</p>
<p align="center"> Figure 2: The data acquisition console loops <br> <br>
