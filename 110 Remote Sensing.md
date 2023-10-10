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

## Passive Sensors
### Multispectral
[[Multispectral]] is a passive remote sensing system that allows [[Land Use]] Classification and [[Fire]] detection.
- [[Landsat]]
- [[MODIS]]
- [[Planet]]
- [[Sentinel 2]]
- [[Maxar]]
- [[Airbus]]
### Hyperspectral
- [[Hyperion]]
- [[HyspIRI]]
### Spectrometers
![[110 Remote Sensing-1.png]]
![[110 Remote Sensing-2.png]]
Analyzes the spectral content of radiation. Can help find out the composition of things - in this case, three rock types that were noticeable as they absorb different parts of the spectrum, but that was impossible to tell with Landsat.

- [[MERIS]]

### Radiometers
Measures the intensity of radiation in some bands within the spectrum. Can cover different portions of the spectrum (visible, IR, microwave)
- [[ECOSTRESS]] (thermal infrared)
- [[VIIRS]]
- GOES
- Visible : Can show whether clouds are thicker or thinner, and where they turn to become hurricanes.
- Infrared : Can be used to distinguish low and high clouds, as low clouds are warmer. IR is available both day and night. 
- Water vapor : between 6.500 nm and 6.900 nm (lower infrared, but not usually noticeable by IR imagery, which is higher)

## Other facts
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
#### With cloud computing
- [Planetary Computer](https://planetarycomputer.microsoft.com/catalog)
- [[Google Earth Engine]]


NASA's products (GEDI, Landsat) have processing levels:
1. raw data
2. derived geophysical
3. mapped to uniform space-time grid scales
## Learning resources
[Applied Remote Sensing Training Program | NASA Applied Sciences](https://appliedsciences.nasa.gov/what-we-do/capacity-building/arset)

### Ongoing
- [NASA ARSET: Overview of Machine Learning, Part 1/3 - YouTube](https://www.youtube.com/watch?v=U-uJGnhD-zg&list=PLiuUQ9asub3QSgIPLo_RdmRd38EEkUzC6)
- [ARSET - Agricultural Crop Classification with Synthetic Aperture Radar and Optical Remote Sensing | NASA Applied Sciences](https://appliedsciences.nasa.gov/get-involved/training/english/arset-agricultural-crop-classification-synthetic-aperture-radar-and)
- [ARSET - Introduction to Synthetic Aperture Radar | NASA Applied Sciences](https://appliedsciences.nasa.gov/get-involved/training/english/arset-introduction-synthetic-aperture-radar)

### Next
- [ARSET - Mapping Crops and their Biophysical Characteristics with Polarimetric SAR and Optical Remote Sensing | NASA Applied Sciences](https://appliedsciences.nasa.gov/get-involved/training/english/arset-mapping-crops-and-their-biophysical-characteristics)
- [NASA ARSET: Crop Classification with Time Series of Polarimetric SAR Data, Part 1/3 - YouTube](https://www.youtube.com/watch?v=QP4VPaBovBk&list=PLiuUQ9asub3Si5Ke17_uwzs1uwZqTQbWR)
