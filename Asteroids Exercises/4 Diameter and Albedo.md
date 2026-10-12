# Diameter and Albedo

## Background

In a previous exercise, we used visible wavelength photometry and the $H$, $G$ brightness relationship to derive a relationship between an unknown asteroid’s radius and albedo and use it to estimate the asteroid’s size for a reasonable range of albedos. We can derive even more accurate and independent estimates of diameter $D$ and Bond albedo $A$ by combining visible photometry with radiometry in the thermal infrared.

In this exercise, we will use data from the Wide-Field Infrared Survey Explorer (WISE) mission and AKARI missions. Each dataset consists of two brightness measurements taken by WISE or AKARI (flux $F$ in Jy) it two different bandpasses (W3 and W4, observing at 12 microns and 22 microns respectively for WISE, S9W and L18W at 9 microns and 18 microns for AKARI), the associated wavelength band the measurement was taken in ($\lambda$ in microns), and the observing geometry (heliocentric distance $r$ and observer distance $\delta$ of the asteroid in astronomical units (au) and phase angle $\alpha$ in degrees) As before, the observing geometry can be calculated from the orbital elements via numerical integration or via using an ephemeris, but is provided here for simplicity. 

## Instructions

**Size estimation from one data point (W3 or S9W)**
1. The simplest thermal model of an asteroid is the isothermal model, where the asteroid emits at constant temperature across its entire surface area, at a temperature equal to the equilibrium temperature $T$ of the asteroid. Given the equation for equilibrium temperature $T(A, r)$ and the Planck function for blackbody spectral irradiance per unit frequency $P(T, \lambda)$, derive an expression for the flux observed on Earth $F$ as a function of diameter $D$ and albedo $A$ of an asteroid. (Hints: the total flux emitted by the asteroid is proportional to its projected surface area and the intensity of radiation drops in proportion to the square of the distance to the observer—this is the inverse square law. Your final equation should be $F_0$ as a function of $\lambda$, $r$, $\delta$, $A$, and $D$. For simplicity assume $\epsilon = 1$ and use $J_{Sun} = 1365 \text{W/m}^2$)
$$T_{eff} = \frac{1}{\sqrt{r}} \left( \frac{(1 - A) J_{Sun}}{4 \epsilon \sigma}\right)^{1/4} $$
$$P(T, \lambda) = \frac{2hc}{\lambda^3} \frac{1}{\exp(\frac{hc}{\lambda k_B T}) - 1}$$

3. Compute the average flux for the WISE W3 or AKARI S9W measurements taken at the same epoch. Since these observations were not taken at a phase angle of $0^{\circ}$, we need to introduce a correction to what the flux of the asteroid would have been if observed at a phase angle of $0^{\circ}$. Empirically, asteroids in the thermal infrared are estimated to darken by 0.01 magnitudes per degree as a function of increasing phase angle. Use the flux/magnitude relationship to calculate $F_0$ (the estimated flux at $\alpha = 0^{\circ}$).
$$m - m_0 = -2.5 \log10 \left(\frac{F}{F_0}\right)$$
4. Given the expression derived in part 1, plug in the observed values of $r$, $\delta$,  $\lambda$, and $F_0$ for the WISE W3 or AKARI S9W measurements into the equation and write an equation for diameter $D$ as a function of albedo $A$. Note that $P(T,v)$ gives the spectral irradiance in $\text{J/m}^2$, but in astronomy it is often more convenient to measure fluxes in Jy (Janskies): $\text{1 Jy} = 10^{-26} \text{J/m}^2$.
5. Create a plot of your expression for diameter as a function of albedo. Next, examine the function you derived in part 2 and the function for diameter as a function of (geometric) albedo derived in the exercise on phase angle and absolute magnitude together. Recall that the Bond albedo $A$ and geometric albedo $p_v$ are not the same, but the two functions can be related via:    
$$A = qp_v$$     
The phase integral q can be empirically estimated using the phase coefficient $G$ using:
$$q = 0.29 + 0.684 G$$
This will allow you to convert geometric albedo to Bond albedo such that the two functions can be plotted on the same axes. Plot them. Where do the two functions intersect, and what is the significance of this intersection point?
6. Given the derived albedo estimate for your asteroid, what is its equilibrium temperature?

**Size estimation from two data points (W3 & W4 or S9W and L18W)**
1. Show that we can derive a temperature estimation from two data points in the thermal infrared. Using the formula for the Planck function, derive an expression for $\frac{P(T, \lambda_{W3})}{ P(T, \lambda_{W4})}$ or $\frac{P(T, \lambda_{S9W})}{ P(T, \lambda_{L18W})}$ and create a plot that shows that the ratio of measured flux density is a unique function of the effective blackbody temperature. Use your results and the observed flux density ratio to estimate the effective temperature of the asteroid. How does this result compare to the equilibrium temperature calculated earlier? What might account for the difference in results?
2. Using the effective temperature of the asteroid calculated in part 4, estimate the asteroid’s Bond albedo using the equation for equilibrium temperature, then use the Bond albedo to estimate the diameter of the asteroid via diameter-albedo relationship from the Phase Function and Absolute Magnitude exercise.

## Discussion Questions

1. What assumptions did you need to make in order to compute the diameter of your asteroid? Are these safe assumptions to make, based on what you currently know about your asteroid? How do uncertainties or errors in your assumptions affect your confidence in your results? What data would you need to be more confident? Quantitatively, uncertainties in which quanities affect the final result the most?
2. Research and critically evaluate the differences between different thermal models, including the Standard Thermal Model (STM), the Fast Rotating Model (FRM), the isothermal model, the near-Earth Asteroid Thermal Model (NEATM), and more detailed thermophysical models. What are the advantages of and disadvantages of each approach? Which populations of asteroids are they best suited for? How would you pick which method to use given a particular dataset? A good place to start is the chapter Radiometry and Thermal Modeling of Asteroids by Lebofsky & Spencer in [Asteroids II](https://open.uapress.arizona.edu/projects/asteroids-ii).
