Case Study 09
================
Hang Tian
2022-11-01

# 1. Import packages and get data

``` r
library(sf)
```

    ## Linking to GEOS 3.10.2, GDAL 3.4.2, PROJ 8.2.1; sf_use_s2() is TRUE

``` r
library(tidyverse)
```

    ## ── Attaching packages
    ## ───────────────────────────────────────
    ## tidyverse 1.3.2 ──

    ## ✔ ggplot2 3.3.6      ✔ purrr   0.3.4 
    ## ✔ tibble  3.1.8      ✔ dplyr   1.0.10
    ## ✔ tidyr   1.2.1      ✔ stringr 1.4.1 
    ## ✔ readr   2.1.2      ✔ forcats 0.5.2 
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(ggmap)
```

    ## Google's Terms of Service: https://cloud.google.com/maps-platform/terms/.
    ## Please cite ggmap if you use it! See citation("ggmap") for details.

``` r
library(rnoaa)
```

    ## Registered S3 method overwritten by 'hoardr':
    ##   method           from
    ##   print.cache_info httr

``` r
library(spData)
```

    ## To access larger datasets in this package, install the spDataLarge
    ## package with: `install.packages('spDataLarge',
    ## repos='https://nowosad.github.io/drat/', type='source')`

``` r
data(world)
data(us_states)
# Download zipped data from noaa with storm track information
dataurl="https://www.ncei.noaa.gov/data/international-best-track-archive-for-climate-stewardship-ibtracs/v04r00/access/shapefile/IBTrACS.NA.list.v04r00.points.zip"

tdir=tempdir()
download.file(dataurl,destfile=file.path(tdir,"temp.zip"))
unzip(file.path(tdir,"temp.zip"),exdir = tdir) #unzip the compressed folder
storm_data <- read_sf(list.files(tdir,pattern=".shp",full.names = T))
```

# 2. Data processing

``` r
storm_cleaned=storm_data%>%filter(ISO_TIME>=1950)%>%
  mutate_if(is.numeric, function(x) ifelse(x==-999.0,NA,x))%>%
  mutate(decade=(floor(year/10)*10))
region=st_bbox(storm_cleaned)
```

# 3. Plot

``` r
ggplot(world)+
  stat_bin2d(data=storm_cleaned,aes(y=st_coordinates(storm_cleaned)[,2], x=st_coordinates(storm_cleaned)[,1]),bins=100)+
  facet_wrap(~decade)+
  scale_fill_distiller(palette="YlOrRd", trans="log", direction=-1, breaks = c(1,10,100,1000))+
  coord_sf(ylim=region[c(2,4)], xlim=region[c(1,3)])
```

![](case_study_09_files/figure-gfm/unnamed-chunk-3-1.png)<!-- -->

# 4. Table calculating

``` r
us_states=st_transform(us_states,st_crs(storm_cleaned))
temp=us_states%>%select(state=NAME)
storm_states <- st_join(storm_cleaned, temp, join = st_intersects,left = F)
result=storm_states%>%group_by(state)%>%
  summarize(storms=length(unique(NAME)))%>%
  arrange(desc(storms))%>%
  slice(1:5)%>%
  st_drop_geometry()
result
```

    ## # A tibble: 5 × 2
    ##   state          storms
    ## * <chr>           <int>
    ## 1 Florida            86
    ## 2 North Carolina     66
    ## 3 Georgia            58
    ## 4 Texas              54
    ## 5 Louisiana          52
