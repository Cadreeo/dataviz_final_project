---
title: "Visualizing Text and Distributions"
output: 
  html_document:
    keep_md: true
    toc: true
    toc_float: true
---

# Data Visualization Project 03


In this exercise you will explore methods to visualize text data and practice how to recreate charts that show the distributions of a continuous variable. 


## Part 1: Density Plots

Using the dataset obtained from FSU's [Florida Climate Center](https://climatecenter.fsu.edu/climate-data-access-tools/downloadable-data), for a station at Tampa International Airport (TPA) from 2016 to 2017, attempt to recreate the charts shown below

```r
library(tidyverse)
library(ggplot2)
library(lubridate)
library(ggridges)
weather_tpa <- read_csv("https://github.com/reisanar/datasets/raw/master/tpa_weather_16_17.csv")
# random sample 
sample_n(weather_tpa, 4)
```

```
## # A tibble: 4 x 6
##    year month   day precipitation max_temp min_temp
##   <dbl> <dbl> <dbl>         <dbl>    <dbl>    <dbl>
## 1  2016     7     6             0       94       82
## 2  2016    12     8             0       69       58
## 3  2016    12     1             0       80       66
## 4  2016     9    17             0       91       78
```
See https://www.reisanar.com/slides/relationships-models#10 for a reminder on how to use this dataset with the `lubridate` package for dates and times.
(a) Recreate the plot below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_facet.png" width="80%" style="display: block; margin: auto;" /><img src="Hudson_project_03_files/figure-html/unnamed-chunk-2-2.png" width="80%" style="display: block; margin: auto;" />
Hint: the option `binwidth = 3` was used with the `geom_histogram()` function.
(b) Recreate the plot below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_density.png" width="80%" style="display: block; margin: auto;" /><img src="Hudson_project_03_files/figure-html/unnamed-chunk-3-2.png" width="80%" style="display: block; margin: auto;" />
Hint: check the `kernel` parameter of the `geom_density()` function, and use `bw = 0.5`.
(c) Recreate the chart below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_density_facet.png" width="80%" style="display: block; margin: auto;" /><img src="Hudson_project_03_files/figure-html/unnamed-chunk-4-2.png" width="80%" style="display: block; margin: auto;" />
Hint: default options for `geom_density()` were used. 
(d) Recreate the chart below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_ridges.png" width="80%" style="display: block; margin: auto;" />

```
## Picking joint bandwidth of 1.49
```

<img src="Hudson_project_03_files/figure-html/unnamed-chunk-5-2.png" width="80%" style="display: block; margin: auto;" />
Hint: default options for `geom_density()` were used. 
(e) Recreate the plot below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_ridges.png" width="80%" style="display: block; margin: auto;" />

```
## Picking joint bandwidth of 1.49
```

<img src="Hudson_project_03_files/figure-html/unnamed-chunk-6-2.png" width="80%" style="display: block; margin: auto;" />
Hint: use the`ggridges` package, and the `geom_density_ridges()` function paying close attention to the `quantile_lines` and `quantiles` parameters.
(f) Recreate the chart below:
<img src="https://github.com/reisanar/figs/raw/master/tpa_max_temps_ridges_plasma.png" width="80%" style="display: block; margin: auto;" />

```
## Picking joint bandwidth of 1.49
```

<img src="Hudson_project_03_files/figure-html/unnamed-chunk-7-2.png" width="80%" style="display: block; margin: auto;" />
Hint: this uses the `plasma` option (color scale) for the _viridis_ palette.
