## Ongoing
- [Data Visualization (socviz.co)](https://socviz.co/
- [R Crash Course](https://github.com/ColauttiLab/RCrashCourse_Book#Downloads)
- [QCBS R Workshops](https://r.qcbs.ca/workshops/)
- [Pipes in R Tutorial For Beginners | Discover %>% with magrittr](https://www.datacamp.com/tutorial/pipe-r-tutorial)
- [Get Started with Clean Coding in R | Earth Data Science - Earth Lab](https://www.earthdatascience.org/workshops/clean-coding-tidyverse-intro/importance-of-clean-code/)
## Next
- [SDS 375: Data Visualization in R](https://wilkelab.org/SDS375/syllabus.html)
- [Advanced R  - functional programming and OOP](https://adv-r.hadley.nz/index.html)
- [Beginner's Guide to Data Exploration and Visualisation with R (Zuur)](https://www.highstat.com/index.php/books2?view=article&id=24&catid=18)
- [R for Data Science](https://r4ds.hadley.nz/)
- [Geocomputation with R](https://r.geocompx.org/)

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
- [rstats.ai videos](https://rstats.ai/videos)

## r-spatial

rgeos, maptools and rgdal (from the sp package) are [retiring](https://r-spatial.org/r/2022/04/12/evolution.html) - sf/stars/terra is the new thing.
Note that some packages will work differently with data from stars, terra or raster.

**What is the difference between the [stars](https://cran.r-project.org/web/packages/stars/index.html) package and terra?**
- can handle more complex data than terra, such as rotated grids.
- stars can handle sf classes, which terra doesn't (will require conversions)
- isn't as well documented as terra
- about 3x faster than terra
- has its own 'stars' object instead of SpatRaster or Raster


## Reproducible code
```bash
# install many packages at once with their dependencies
R -q -e "install.packages(c('terra', 'randomForest', 'tidyverse'), dependencies = TRUE)"
```

### [Unit Testing](https://www.geeksforgeeks.org/unit-testing-in-r-programming/) 
With the testthat package, we can check if the results given are expected, such as dimensions and value ranges.

### Pipe Operator


### VSCode Extensions
[R in Visual Studio Code](https://code.visualstudio.com/docs/languages/r)
#### IntelliSense Code Completion
#### Linter
[documentation](https://lintr.r-lib.org/articles/lintr.html#configuring-linters)
- Checks the code for potential errors
- Styler corrects these errors.
#### Github Copilot


#### Debugging

### renv and Batch Mode
Python-like working with R code
[Introduction to renv • renv (rstudio.github.io)](https://rstudio.github.io/renv/articles/renv.html)
[R Programs in Batch mode for HPC - HPC Documentation - UIowa Wiki](https://wiki.uiowa.edu/display/hpcdocs/R+Programs+in+Batch+mode+for+HPC)


