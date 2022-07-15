---
layout: post
title: Machine Learning Techniques for Bragg Crystal Energy Calibration
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
the difference between the photon energy as measured by the single-shot spectrometer and the actual one.  </p> <br><br>


<p align="justify"> Crystal reflections are first scanned at different pitch angles using the spectrometer, and the image obtained is binarized.
With a 68% extraction rate and a very low false positive rate, lines with a high intensity and good contrast from the background can be detected using the Hough Transform method.
A ML classifier then compares a preset measurement model and the extracted lines and identifies the reflections based on different line properties.  Most errors were noted in cases where multiple parallel lines occur close to each other (for example classifying [1, -1, -1] as [1, -1, 1]).
Improvements in the future can be made in extracting more information from the raw images by trying different image processing techniques. </p> <br><br>

<p align="center">
  <img src="https://github.com/cgre23/cgre23.github.io/blob/master/images/feature_abc.png?raw=true" width="1000" title="Example of a) a captured image, b) a processed version (binarization, dilation, erosion) and c) the detected lines (Hough Transform).">
</p>


<p align="justify"> We are now proposing an alternative method for identifying the actual photon energy by implementing a technique known as Template Matching.
Template matching is a common computer vision technique where an algorithm is trying to find similarities between two images.
This technique slides a window across the image that will provide a percent match with the template. If the percent match is above a certain threshold then it is assumed to be a match.
This will in some situations result in poor performance because it requires the template to overlap the image identically. </p><br><br>


<p align="justify"> Template matching is a sufficient technique if one knows exactly what they are looking for and are confident that it will appear almost identically in every example.
ML techniques such as Convolutional Neural Networks (CNN) can be used in cases where the template and the image are not identical. ML techniques are not rigid and are able to generalize a dataset very well.
What is required in this case is a fairly large dataset so that the model is robust to many different scenarios. </p><br><br>

<p align="justify"> This project involves the matching of a processed spectrometer image (template), with an image created from an available model. The following proof-of-concept gets the original spectrometer scan (first image) and clips out the unnecessary blank areas (second image).
The second image is the template. The third image is the image created from the Bragg model, with the red box being the matched area using sklearn’s match_template package.
By comparing the bottom left corner energy value of the spectrometer image and the matched image, one can calculate the energy difference.  The final image plots the calibrated template on top of the model.  </p><br>

<p align="center">
  <img src="https://github.com/cgre23/cgre23.github.io/blob/master/images/poc.png?raw=true" width="1000" title="Template Matching proof-of-concept">
</p>

<br>
<br>**Project resources**

* [Code](https://github.com/cgre23/pyhirex)
* [Bragg Crystal Map](graphs.md)
* [Crystal Bragg Model](Braggmodel.md)
* [Crystal reflection map](reflectionscamera.md)
* [Crystal Reflections Camera Acquisitions](reflectionsintensity.md)
