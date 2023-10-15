## Active Sensors
[[LiDAR]] and [[SAR]] are active remote sensing systems that allow the detection of [[Biomass]].
### LiDAR
- [[GEDI]]
- [[ICESat1 - GLAS & ICESat2 - ATLAS]]
- [[Asner ACD]]
### SAR
- [[ESA CCI Biomass]]
- [[Sentinel 1]]
- [[NISAR]]
- [[ASAR-ESA]]
- [[PALSAR - ALOS]]
*Scatterometers* use radar to measure backscatter due to ocean wind and direction.
## Passive Sensors
### Multispectral
Is a passive remote sensing system that allows [[Land Use]] Classification and [[Fire]] detection.

![[Multispectral.png]]

![[Multispectral-1.png]]

- [[Landsat]]
- [[MODIS]]
- [[Planet]]
- [[Sentinel 2]]
- [[Maxar]]
- [[Airbus]]
### Hyperspectral
![[110 Remote Sensing-5.png]]
Finds hundreds of very narrow bands on visible, near-IR and mid-IR, so higher spectral resolution.
- [[Hyperion]]
- [[HyspIRI]]
- PROBA-1 (ESA) in 2001
- PRISMA (Italy) in 2019
- EnMap (Germany) in 2020
- HISUI (Japan) in 2020
They are not very commonly used because:
- Very expensive and difficult to manufacture
- Enormous data that is very hard to handle
- Insufficient labelled data for training
Possibly this can be solved with [machine learning](https://www.netguru.com/blog/hyperspectral-imaging-applications)
### Spectrometers
![[110 Remote Sensing-1.png]]
![[110 Remote Sensing-2.png]]
Analyzes the spectral content of radiation - sometimes they use prisms! Can help find out the composition of things - in this case, three rock types that were noticeable as they absorb different parts of the spectrum, but that was impossible to tell with Landsat.
- [[MERIS]]

### Radiometers
Measures the intensity of radiation in some bands within the spectrum. Can cover different portions of the spectrum (visible, IR, microwave)
- [[ECOSTRESS]] (thermal infrared)
- [[VIIRS]]
- GOES
- *Visible* : Can show whether clouds are thicker or thinner, and where they turn to become hurricanes.
- *Infrared* : Can be used to distinguish low and high clouds, as low clouds are warmer. IR is available both day and night. 
- *Water vapor* : between 6.500 nm and 6.900 nm (lower infrared, but not usually noticeable by IR imagery, which is higher)

## Other facts
- **Polar orbits** cover the whole world, with low-earth being faster. Non-polar low-Earth orbit satellites only cover some latitudes.
- **Thermal sensors** are passive, but can collect data at night as it's emitted from the source and independent of the sun.
- **Sounders** can be active or passive, and they measure temperature, precipitation, humidity, cloud composition.
- **Radiometric resolution** indicates the ability of the sensor to detect small differences in energy, and show more detail in the terrain.
	- More relevant for old Landsat data (ETM, TM, MSS)
![[110 Remote Sensing-4.png]]
- **Processing levels** for NASA's products (GEDI, Landsat):
1. raw data
2. derived geophysical quantity
3. mapped to uniform space-time grid scales
4. combined with models or other instrument data

- The **nadir** is the point in the Earth directly below the satellite.

- A **datum** is a point in Earth that we use as a reference point for other locations.

- **Coordinate Reference Systems (CRS)**
	- *Geographic (WGS84)*: Good for large extents, bad for specific regions
	- *Projected (UTM)*: Good for specific regions, bad for large extents. UTM is cylindrical, so it's good for equatorial regions.
- **Larger wavelengths require larger apertures for same resolution**
	![[110 Remote Sensing-3.png]]
- **Plants reflect near-infrared very strongly!**
		And that reflectance changes with the season/growth stage... possibly also species??
- **We need atmospheric correction!**
		Much energy is absorbed and reflected by the atmosphere. 
![[Pasted image 20231009200418.png]]

- **It's hard to find something with high spectral, temporal AND spatial resolution**
		Landsat has high resolution, but only returns every 16 days. MODIS, on the other hand, returns every 1-2 days, but has a 500m resolution

Solved with constellations, such as [[Airbus]], [[Planet]] and [[Maxar]].
![[110 Remote Sensing.png|ARSET image - MODIS boxes in blue and Landsat boxes in red]]

## Data Access
- [INPE :: Catálogo de Imagens](http://www.dgi.inpe.br/catalogo/explore)
- [USGS EarthExplorer](https://earthexplorer.usgs.gov/)
- [ESA Copernicus](https://dataspace.copernicus.eu/)
- [Sentinel Hub Playground](https://apps.sentinel-hub.com/sentinel-playground/?source=S2L2A&lat=40.4&lng=-3.730000000000018&zoom=12&preset=1_TRUE_COLOR&layers=B01,B02,B03&maxcc=20&gain=1.0&gamma=1.0&time=2023-04-01%7C2023-10-09&atmFilter=&showDates=false)
- [Sentinel Hub EO Browser](https://apps.sentinel-hub.com/eo-browser/)
- [NASA Earthdata](https://search.earthdata.nasa.gov/search)
- [NASA Worldview](https://worldview.earthdata.nasa.gov/)
- [Zoom Earth | Weather Maps & Live Hurricane Tracker](https://zoom.earth/maps/satellite/#view=18.1,-87.5,4z)
- [JAXA Global 3D Map](https://www.eorc.jaxa.jp/ALOS/en/dataset/aw3d_e.htm)
- [GOES Imagery Viewer - NOAA / NESDIS / STAR](https://www.star.nesdis.noaa.gov/goes/index.php)
- [Alaska Satellite Facility](https://asf.alaska.edu/)
#### With cloud computing
- [Planetary Computer](https://planetarycomputer.microsoft.com/catalog)
- [[Google Earth Engine]]
- [Open Data Cube](https://www.opendatacube.org/get-started)
- [openEO](https://openeo.org/)
## Learning resources

### Ongoing
1. [ARSET - Fundamentals of Remote Sensing | NASA Applied Sciences](https://appliedsciences.nasa.gov/get-involved/training/english/arset-fundamentals-remote-sensing)
2. [NASA ARSET: Overview of Machine Learning, Part 1/3 - YouTube](https://www.youtube.com/watch?v=U-uJGnhD-zg&list=PLiuUQ9asub3QSgIPLo_RdmRd38EEkUzC6)
3. [ARSET - Agricultural Crop Classification with Synthetic Aperture Radar and Optical Remote Sensing | NASA Applied Sciences](https://appliedsciences.nasa.gov/get-involved/training/english/arset-agricultural-crop-classification-synthetic-aperture-radar-and)
4. [ARSET - Introduction to Synthetic Aperture Radar | NASA Applied Sciences](https://appliedsciences.nasa.gov/get-involved/training/english/arset-introduction-synthetic-aperture-radar)
5. [EO College - YouTube](https://www.youtube.com/@EOCollege)
6. [Introduction to QGIS (Full Course Material) (spatialthoughts.com)](https://courses.spatialthoughts.com/introduction-to-qgis.html#get-the-data-package)
7. [Earth Lab Courses](https://www.earthdatascience.org/)
8. [Mastering GDAL Tools](https://courses.spatialthoughts.com/gdal-tools.html#introduction)[[Computers and Bash#GDAL|Notes]]
#### Dalagnol's courses
- [Mini-curso "Deep Learning para Imagens de Sensoriamento Remoto" no WorCAP 2021 - YouTube](https://www.youtube.com/watch?v=foRhRg6VaCQ)
- [github code](https://github.com/ricds/DL_RS_GEE)

### Next
- [ARSET - Mapping Crops and their Biophysical Characteristics with Polarimetric SAR and Optical Remote Sensing | NASA Applied Sciences](https://appliedsciences.nasa.gov/get-involved/training/english/arset-mapping-crops-and-their-biophysical-characteristics)
- [NASA ARSET: Crop Classification with Time Series of Polarimetric SAR Data, Part 1/3 - YouTube](https://www.youtube.com/watch?v=QP4VPaBovBk&list=PLiuUQ9asub3Si5Ke17_uwzs1uwZqTQbWR)
- [Getting Started with NASA Global Ecosystems Dynamics Investigation (GEDI) Lidar Data - YouTube](https://www.youtube.com/watch?app=desktop&v=UlrCC1Xp-wk)

#### Packages
[fasterRaster](https://rdrr.io/github/adamlilith/fasterRaster/man/fasterProjectRaster.html)
[nn2: Nearest Neighbour in df or matrix](https://rdrr.io/cran/RANN/man/nn2.html)
[sits: Satellite image time series in R](https://github.com/e-sensing/sits)
