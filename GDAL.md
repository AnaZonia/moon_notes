---
up:
  - "[[110 Remote Sensing]]"
stardate: Oct 15th 2023
update: Oct 15th 2023
---

#### Show information on an image
```bash
gdalinfo N28E086.hgt
```

#### Compute image statistics
```
gdalinfo -stats N28E086.hgt
```

#### Merge rasters
``` bash
# put them into a text file
ls *.hgt > filelist.txt

# merge them into a single raster
gdalbuildvrt -input_file_list filelist.txt merged.vrt

# or in one line
gdalbuildvrt merged.vrt *.hgt
```
![[Computers and Bash.png]]

#### Convert virtual raster format (vrt) to GeoTIFF
``` bash
gdal_translate -of GTiff merged.vrt merged.tif
# -of GTiff optional, as the extension says the file type
```

#### Compress
Possible algorithms are DEFLATE, LZW and PACKBITS.
- The *PREDICTOR* option helps compress data better when the neighboring values are correlated. For elevation data, this is definitely the case.
- The *TILED* option will compress the data in blocks rather than line-by-line.

```bash
gdal_translate -of GTiff merged.vrt merged.tif -co COMPRESS=DEFLATE

gdal_translate -of GTiff merged.vrt merged.tif \
  -co COMPRESS=DEFLATE -co TILED=YES -co PREDICTOR=2

# specifying a new threshold for the nodata value, since the default is -32768
gdal_translate -of GTiff merged.vrt merged.tif \
  -co COMPRESS=DEFLATE -co TILED=YES -co PREDICTOR=2 -a_nodata -9999
```

#### Writing Cloud-Optimized GeoTIFF (COG)
 A _Cloud-optimized_ GeoTIFF is behaving just like a regular GeoTIFF imagery, but instead of downloading the entire image locally, you can access _portions_ of imagery hosted on a cloud server streamed to clients like QGIS.
 
``` bash
gdal_translate -of COG merged.vrt merged_cog.tif \
  -co COMPRESS=DEFLATE -co PREDICTOR=2 -co NUM_THREADS=ALL_CPUS \
  -a_nodata -9999
```