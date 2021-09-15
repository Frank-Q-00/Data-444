# Exercise 2 -- Spacial Population of Description of Georgia

## Plot Georgia's subdivisions
```R
library(tidyverse)
library(sf)

rm(list=ls())

int <- read_sf('gadm36_GEO_shp/gadm36_GEO_0.shp')
adm1 <- read_sf('gadm36_GEO_shp/gadm36_GEO_1.shp')
adm2 <- read_sf('gadm36_GEO_shp/gadm36_GEO_2.shp')

ggplot() +
  geom_sf(data = adm1,
          size = 0.65,
          color = "gray50",
          fill = "gold3",
          alpha = 0.65) +
  geom_sf(data = int,
          size = 2.0,
          color = "black",
          #fill = "color",
          alpha = 0) +
  geom_sf_text(data = int,
               aes(label = NAME_0),
               size = 6,
               color = "black") +
  geom_sf_text(data = adm1,
                aes(label = NAME_1),
                size = 1.5,
                color = "black")

ggplot() +
  geom_sf(data = adm2,
          size = 0.2,
          color = "gray70",
          fill = "wheat2",
          alpha = 0.65) +
  geom_sf(data = adm1,
          size = 0.6,
          color = "gray50",
          alpha = 0) +
  geom_sf(data = int,
          size = 1.5,
          color = "black",
          alpha = 0) +
  geom_sf_text(data = adm1,
               aes(label = NAME_1),
               size = 1.5,
               color = "black") +
  geom_sf_text(data = adm2,
               aes(label = NAME_2),
               size = 0.7,
               color = "black")
```


