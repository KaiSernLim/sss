### CS 184: Computer Graphics and Imaging, Spring 2017
# Final Project Milestone
## by Juchan Kim & Kai-Sern Lim

## Abstract
The largest part of the project is understanding the model and how to implement it, which is what we have devoted the majority of our time, so far, into.
The irradiance value is $$L(x_{0},\omega_{0}) = \int_{A}\int_{\Omega}L_{i}(x_{i},\omega_{i})S(x_{i},\omega_{i},x_{0},\omega_{0})\cos(\theta)d\omega dA$$
where the BSSRDF is approximated by two terms, a diffusion term and a single-scattering term:
$$S(x_{i},\omega_{i};x_{0},\omega_{0}) = S_{d}(x_{i},\omega_{i};x_{0},\omega_{0}) + S^{(1)}(x_{i},\omega_{i};x_{0},\omega_{0})$$
$S_{d}(x_{i},\omega_{i};x_{0},\omega_{0}) = \frac{1}{\pi}F_{t}(x_{i},\omega_{i})R_{d}(\|x_{i}-x_{0}\|)F_{t}(x_{0},\omega_{0})$
The BSSRDF is approximated with diffusion phenomenon which is modeled by the dipole model with a real and virtual light source.
Diffuse BSSRDF term: $R_{d}(r) = \frac{\alpha}{4\pi}[z_{r}(\sigma_{tr}d_{r}(r)+1)e^{-\sigma_{tr}d_{r}(r)}\frac{1}{d_{r}^{3}(r)} + z_{v}(\sigma_{tr}d_{v}(r)+1)e^{-\sigma_{tr}d_{v}(r)}\frac{1}{d_{v}^{3}(r)}]$ where $\sigma_{tr} =\sqrt{3\sigma_{a}((1-g)\sigma_{s}+\sigma_{a})}$ is the effective extinction coefficient, $d_{r}(r) = \sqrt{z_{r}^{2} + r^{2}}, d_{v}(r) = \sqrt{z_{v}^{2}+r^{2}}$ are real and virtual light refractions, $z_{v} = \frac{1}{\sigma_{t}'}, z_{r} = z_{v} + 4\frac{1+F_{dr}}{3\sigma_{t}'(1-F_{dr})}$ are real and virtual light source distances, and $F_{dr} = -\frac{1.44}{\eta^{2}} + \frac{0.71}{\eta} + 0.668 + 0.0636\eta$ where $\sigma_{s}$ (scattering coefficient), $\sigma_{t}$ (extinction coefficient) and $\eta$ (index of refraction) are known properties of the material.

Sampling we assume exponential falloff, so we need to take into account the exponential pdf $X \sim \sigma_{tr}e^{-\sigma_{tr}x}$

## Reflection
The planning portion of the project has taken significantly longer than anticipated and we have barely completed any coding. We thought there would be models available online for us to render, but it looks like we will have to modify the `.dae` files ourselves to include the necessary BSSRDF information and modify it and our raytracer in order for them to work with each other properly.

We are about half a week behind schedule and we absolutely need to make up for lost time, mainly by finishing the implementation of the model and modifying the `.dae` files to work with the current raytracer. Since it has taken so much time, it is unlikely that we will be able to attempt our stretch goal to speed up the BSSRDF calculation.

### Updated schedule:
**Week 3:** Absolutely must finalize the design and organization. Must also get the program running.

**Week 4:** Tie up any loose ends with the rendering and spend time rendering the pretty pictures.

## Video and Slides
