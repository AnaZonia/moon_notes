 ## Ongoing
- [Data Visualization (socviz.co)](https://socviz.co/
- [R Crash Course](https://github.com/ColauttiLab/RCrashCourse_Book#Downloads)
- [QCBS R Workshops](https://r.qcbs.ca/workshops/)
- [Pipes in R Tutorial For Beginners | Discover %>% with magrittr](https://www.datacamp.com/tutorial/pipe-r-tutorial)
- [Get Started with Clean Coding in R | Earth Data Science - Earth Lab](https://www.earthdatascience.org/workshops/clean-coding-tidyverse-intro/importance-of-clean-code/)
## Next
- [SDS 375: Data Visualization in R](https://wilkelab.org/SDS375/syllabus.html)
- [Advanced R book](https://adv-r.hadley.nz/)
- [Beginner's Guide to Data Exploration and Visualisation with R (Zuur)](https://www.highstat.com/index.php/books2?view=article&id=24&catid=18)
- [R for Data Science](https://r4ds.hadley.nz/)
- [Geocomputation with R](https://r.geocompx.org/)
- [Spatial Data Science](https://r-spatial.org/book/)
- [Intro a Mapas en R - Github](https://github.com/ulisesbalza/mapas_R_intro/tree/main)
- [R for Earth-System Science (pjbartlein.github.io)](https://pjbartlein.github.io/REarthSysSci/index.html)

## Help if needed
- [jakelawlor/TidyTuesday](https://github.com/jakelawlor/TidyTuesday_JL/tree/master)
- [R Screencasts - TidyTuesday Tutorials](https://www.rscreencasts.com/)
- [BIOS² Data Visualization examples and resources](https://bios2.github.io/posts/2020-09-21-data-visualization/)
- [Mutate multiple columns — mutate_all • dplyr](https://dplyr.tidyverse.org/reference/mutate_all.html)
- [Cheatsheets](https://rstudio.github.io/cheatsheets/)
- [Targets in R - making pipelines](https://docs.ropensci.org/targets/)
- [R with Google Colab and Stats](https://bookdown.org/yshang/book/)
- [Workshop Materials MICM](https://www.mcgill.ca/micm/training/workshops-series/workshop-materials)
- [The caret Package (Classification and Regression Training)](https://topepo.github.io/caret/index.html)
- [Making Sense of Data with R](https://bookdown.org/yshang/book/)
- [rstats.ai videos](https://rstats.ai/videos)
#### Packages
[fasterRaster](https://rdrr.io/github/adamlilith/fasterRaster/man/fasterProjectRaster.html)
[nn2: Nearest Neighbour in df or matrix](https://rdrr.io/cran/RANN/man/nn2.html)
[sits: Satellite image time series in R](https://github.com/e-sensing/sits)
http://adv-r.had.co.nz/Rcpp.html
[classify function - RDocumentation](https://www.rdocumentation.org/packages/RandPro/versions/0.2.2/topics/classify)
factors are labelled numbers
Difference between RData, rds, R file types

[[Data Visualization]]
## r-spatial

rgeos, maptools and rgdal (from the sp package) are [retiring](https://r-spatial.org/r/2022/04/12/evolution.html) - sf/stars/terra is the new thing.
Note that some packages will work differently with data from stars, terra or raster.

**What is the difference between the [stars](https://cran.r-project.org/web/packages/stars/index.html) package and terra?**
- can handle more complex data than terra, such as rotated grids.
- stars can handle sf classes, which terra doesn't (will require conversions)
- isn't as well documented as terra
- about 3x faster than terra
- has its own 'stars' object instead of SpatRaster or Raster

## Functional Programming and OOP


## Reproducible code and good practices
```bash
# install many packages at once with their dependencies
R -q -e "install.packages(c("curl", "httr",

"openssl", "tidyverse", # required for tidyverse in Fedora

"terra", "rstan", "ggplot2",

"remotes", "Rcpp", "sf", "terra", # required for terra

"languageserver", "rmarkdown" # for VSCode and Bayesian

), dependencies = TRUE)

remotes::install_github(c("ManuelHentschel/vscDebugger", "stan-dev/cmdstanr"))

install.packages("httpgd", repos = c(

"https://nx10.r-universe.dev",

"https://cran.r-project.org"

))"
```

### [Unit Testing](https://www.geeksforgeeks.org/unit-testing-in-r-programming/) 
With the testthat package, we can check if the results given are expected, such as dimensions and value ranges.

### Pipe Operator

Note: the pipe operator can make loops/apply/per run much slower:

![](https://i.imgur.com/wKnlrvP.png)



#### Debugging

### renv and Batch Mode
Python-like working with R code
[Introduction to renv • renv (rstudio.github.io)](https://rstudio.github.io/renv/articles/renv.html)
[R Programs in Batch mode for HPC - HPC Documentation - UIowa Wiki](https://wiki.uiowa.edu/display/hpcdocs/R+Programs+in+Batch+mode+for+HPC)
- Not as necessary in R, as packages are not so version-dependent as is Python. If anything, virtual environments can cause trouble when versions are updated globally.
- Similarly, R code should not be written the same way as Python code (everything within a function), as R functions create a separate environment and are much slower than Python.

