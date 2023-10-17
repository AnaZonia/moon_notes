---
up:
  - "[[110 Remote Sensing]]"
type:
  - platform
aliases:
  - gee
  - GEE
---
- Needed to use earthengine auhenticate --auth_mode=notebook to install. Thanks [SpatialThoughts!](https://courses.spatialthoughts.com/install-gee-python-api.html)
- [community datasets](https://github.com/samapriya/awesome-gee-community-datasets)

Image <- one Scene
- ImageCollection
Feature <- polygons, points, lines
- FeatureCollection

### Resources
[GIS Stack Exchange](https://gis.stackexchange.com/questions/tagged/google-earth-engine)
[Google Earth Engine Developers Forum](https://groups.google.com/g/google-earth-engine-developers)
## Javascript
*Why use APIs instead?*
- It is not recommended to run for loops in the GEE interface
- cannot run deep learning
- an API allows to overlay GEE data with my own other datasets
But since a lot of resources come in javascript, it's good  (and very possible) to have some basic understanding of the code. Also, there's the window to visualize things immediately!
[Cloud-Based Remote Sensing with Google Earth Engine: Fundamentals and Applications](https://www.eefabook.org/go-to-the-book.html) Chapters 1-5
	- [​Chapter Summary Videos (eefabook.org)](https://www.eefabook.org/videos.html)

[Land use and Land cover classification using Random forest machine learning in Google Earth Engine - YouTube](https://www.youtube.com/watch?v=Z-DPRCWWaqg)




## rgee
- [Using Google Earth Engine with R](https://www.css.cornell.edu/faculty/dgr2/_static/files/R_html/ex_rgee.html)
- [Introduction to Google Earth Engine with R language - YouTube](https://www.youtube.com/watch?v=SHXuIpjU3YE)
[rgee examples](https://csaybar.github.io/rgee-examples/)
- [rgee documentation](https://r-spatial.github.io/rgee/)
[Best Practices](https://r-spatial.github.io/rgee/articles/rgee03.html)
[Earth Engine with R book](https://r-earthengine.com/rgeebook/)
[Installing RGEE to use Google Earth Engine inside R - YouTube](https://www.youtube.com/watch?v=1-k6wNL2hlo)

## geemap
- [A collection of 300+ examples for using Earth Engine and the geemap Python package](https://github.com/giswqs/earthengine-py-examples)
- [Earth Engine Python API](https://developers.google.com/earth-engine/tutorials/community/intro-to-python-api)