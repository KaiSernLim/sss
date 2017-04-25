### CS 184: Computer Graphics and Imaging, Spring 2017
# Final Project Milestone
## by Juchan Kim & Kai-Sern Lim

## Abstract
The largest part of the project is understanding the model and how to implement it, which is what we have devoted the majority of our time, so far, into.
The irradiance value is
![enter image description here](http://i.imgur.com/lDzier9.png)
where the BSSRDF is approximated by two terms, a diffusion term and a single-scattering term:
![enter image description here](http://i.imgur.com/vNWf9DH.png)
![enter image description here](http://i.imgur.com/CDeGRt3.png)
The BSSRDF is approximated with diffusion phenomenon which is modeled by the dipole model with a real and virtual light source.
Diffuse BSSRDF term: ![enter image description here](http://i.imgur.com/I1IXnAT.png) where ![enter image description here](http://i.imgur.com/SsAUqJP.png) is the effective extinction coefficient, ![enter image description here](http://i.imgur.com/wKiFWui.png) are real and virtual light refractions, ![enter image description here](http://i.imgur.com/d9ugVBT.png) are real and virtual light source distances, and ![enter image description here](http://i.imgur.com/aYLveof.png) where sigma_s (scattering coefficient), sigma_t (extinction coefficient) and eta (index of refraction) are known properties of the material.

Sampling we assume exponential falloff, so we need to take into account the exponential pdf ![enter image description here](http://i.imgur.com/nQ7YgKH.png)

## Reflection
The planning portion of the project has taken significantly longer than anticipated. We thought there would be ready-made models for us to render, but it looks like we will have to modify the `.dae` files ourselves and modify it into the framework.

We are about half a week behind schedule and we absolutely need to make up for lost time, mainly by finishing the implementation of the model and modifying the `.dae` files to work with the current raytracer. Since it has taken so much time, it is unlikely that we will be able to attempt our stretch goal to speed up the BSSRDF calculation.

### Updated schedule:
**Week 3:** Absolutely must finalize the design and organization. Must also get the program running.
**Week 4:** Tie up any loose ends with the rendering and spend time rendering the pretty pictures.

## Video and Slides
[Video](https://youtu.be/sOldr_AmJ8g)
[Slides](https://docs.google.com/presentation/d/14yhEIX0eYCW3Cwl7MBpkXEmL3pRK8PxaBxdUE_RQAlI/edit)
