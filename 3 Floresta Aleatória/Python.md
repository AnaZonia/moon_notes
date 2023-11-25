---
up:
  - "[[100 A Floresta Aleatória]]"
stardate: Sep 30th 2023
update: Oct 8th 2023
---
### Ongoing
1. [Suggested Learning Paths – Spatial Thoughts](https://spatialthoughts.com/learning-paths/)
	- [Python Foundation for Spatial Analysis (Full Course Material) (spatialthoughts.com)](https://courses.spatialthoughts.com/python-foundation.html#introduction)
	- [Rebecca Barter - An introduction to Python for R Users](https://www.rebeccabarter.com/blog/2023-09-11-from_r_to_python)
- [Get Started With GIS in Open Source Python - Geopandas, Rasterio & Matplotlib | Earth Data Science - Earth Lab](https://www.earthdatascience.org/workshops/gis-open-source-python/)
- [Machine Learning Mastery](https://machinelearningmastery.com/start-here/)
- [QGIS Google Earth Engine plugin](https://gee-community.github.io/qgis-earthengine-plugin/)
- [Creating Maps with Google Earth Engine and PyQGIS – Spatial Thoughts](https://spatialthoughts.com/2020/04/04/ndvi-time-series-gee-qgis/)
### Next
- [FULL COURSE - Google Earth Engine Python API and Colab for Absolute Beginners in 3 Hours](https://www.youtube.com/watch?v=Lqirs04EccA)
- [McMedHacks](https://app.gumroad.com/d/5f76a9bc66bfd87f4d75d4d157304e99)
- [Python for Statistical Analysis | Udemy](https://www.udemy.com/course/python-for-statistical-analysis/)
- [Machine Learning in Python (Data Science and Deep Learning) | Udemy](https://www.udemy.com/course/data-science-and-machine-learning-with-python-hands-on/)
### Help if needed
- [Pandas_Cheat_Sheet](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)
- [Corey Schafer - YouTube](https://www.youtube.com/@coreyms)
- [Workshop Materials MICM](https://www.mcgill.ca/micm/training/workshops-series/workshop-materials)

## First steps
- Always have a virtual environment. Conda is a sort of a manager for packages and virtual environments, but it's unnecessary - everything can be managed easily with pip and venv.


## Venv

```bash
# the virtual environment is just a directory with the information of the python version used at time of creation.

# install venv
sudo apt install python3.10-venv

# create a new virtual environment
python3 -m venv forest_regrowth_env
# to create a venv with all the packages from the global installation:
python3 -m venv venv --system-site-packages 

#activate it 
source project_env/bin/activate


#to show only packages installed in this specific environment
pip list --local
pip freeze --local
#exit venv
deactivate

```
## Machine Learning
[[017 Aprendizado de Máquina]]

### TPOT
[TPOT](https://machinelearningmastery.com/tpot-for-automated-machine-learning-in-python/) allows for Automated Machine Learning in Python. I used it to run my model, but so far have not found much improvement in comparison with Optim.