---
up:
  - "[[Remote Sensing]]"
---
It's called synthetic aperture as it uses a very large antenna that moves in a way that it artificially acts as if it's a much larger aperture ([great explanation!](https://www.youtube.com/watch?v=u2bUKEi9It4))
- The same antenna is used repeatedly as it moves, acting as if it's a much larger antenna.
- The doppler shift in the return signal allows it to determine which direction the echoes are coming from.
It can image through clouds, as well as day or night.

![[SAR.png]]
SAR is dependent on the *structure* and *moisture*.

**Dielectric constant** measures how easily a dipolar molecule (such as water!) will rotate in response to an electromagnetic field.
- water molecules rotate easily in response to the micro/radiowaves
- so water reflects a ton of energy back!
- more soil moisture = more backscatter = brighter returns

**Polarization** is the orientation in the plane in which the wave oscillates:
- Signals emitted in vertical and received in vertical are often a result of rough terrain
- Signals emitted in horizontal and received in horizontal are often a result of buildings (double bounce)
- A mix of both is a result of dense vegetation or highly porous soil (sand, dry soil)
- the ratio of HH to VV is an indicator of moisture content (moisture is depolarizing)
- V-polarized waves couple with vertically structured vegetation so more of the energy is attenuated
- H-polarized waves penetrate better through the canopy to the underlying soil
- HV/VH cross-polarizations show volume of target (density of forest?)
![[SAR-1.png]]

**Penetration depth** increases with wavelength and decreases with moisture
- Physics - large wavelength means lower frequency, which means more penetration depth.
![[SAR1.png]]

SAR backscatter are recorded in both return **strength and phase**, with weaker signals coming from rough terrain (more backscatter)

**Interferometry** is an analysis method that shows changes in the land topography in between two observations of the same target. Can be used to identify volcanic eruptions and earthquakes down to the centimeter!

![[SAR-3.png]]
Can be useful for *land use classification* as structure varies significantly across different crop types!

![[SAR-2.png]]


## Limitations
- **Rainfall** can scatter the light
- Can be less useful at extremely **large or low densities**
- The C-band performed better in more open forests with lower AGB and the L-band performed better in closer forests with moderate AGB levels [Zeng et al 2022](https://www.mdpi.com/1999-4907/13/3/442)
- Distortions happen in sloped areas due to the sensor that looks sideways.