---
layout: post
title: Machine Learning Techniques for Bragg Crystal Calibration
permalink: /euxfel/
description: Machine Learning
tags: [Jekyll, theme, responsive, blog, template]
image:
  feature:
---
<br>**Project description**


<p align="justify"> Single-crystal monochromators are used in free electron lasers for hard x-ray self-seeding, selecting a very narrow spectral range and further amplifying the original SASE signal.
When a crystal is rotated, one can exploit several symmetric and asymmetric reflections as established by Bragg's law.  
Currently, a Machine Learning (ML) classifier is used during experimental setup to identify the crystal indices corresponding to a given reflection, compare to a model, and eventually calculate
the difference between the photon energy as measured by the single-shot spectrometer and the actual one. Extracting information from images has proven to be challenging measurement
artifacts such as noise and dead pixels. </p>


<p align="justify"> This project proposes an alternative method for identifying the actual photon energy by implementing a technique known as Template Matching.
Template matching is a common computer vision technique where an algorithm is trying to find similarities between two images.
This technique slides a window across the image that will provide a percent match with the template. If the percent match is above a certain threshold then it is assumed to be a match.
This will in some situations result in poor performance because it requires the template to overlap the image identically. </p>


<p align="justify"> Template matching is a sufficient technique if one knows exactly what they are looking for and are confident that it will appear almost identically in every example.
ML techniques such as Convolutional Neural Networks (CNN) can be used in cases where the template and the image are not identical. ML techniques are not rigid and are able to generalize a dataset very well.
What is required in this case is a fairly large dataset so that the model is robust to many different scenarios. </p>

<p align="justify"> This project involves the matching of a processed spectrometer image (template), with an image created from an available model. </p>

<p align="center">
  <img src="https://github.com/cgre23/cgre23.github.io/blob/master/images/poc.png?raw=true" width="500" title="Template Matching proof-of-concept">
</p>
