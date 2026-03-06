# REANNZ training environment RStudio app
Open OnDemand RStudio app for the REANNZ training environment.

## Docker Configuration

### R Version
The Dockerfile does not explicitly specify an R version. It uses FROM rocker/geospatial:latest, which means it pulls the latest version of the Rocker geospatial image. The specific R version will be whatever is current in that latest geospatial image at build time.

### R Packages Installed
The following R packages are explicitly installed via Rscript:

`vegan` - Ecological diversity analysis  
`palmerpenguins` - Palmer Archipelago penguin data  
`Manu` - New Zealand data visualization (from G-Thomson/Manu on GitHub)  
`viridis` - Colorblind-friendly color palettes  
`ggbeeswarm` - ggplot2 extension for bee swarm plots  
`ggtext` - ggplot2 extension for improved text rendering  
`ggridges` - ggplot2 extension for ridge plots  

### System Packages Installed
In addition to R packages, the following system packages are installed:

curl, git, nano, vim (text editors)
unzip, wget, zip (utilities)

### Workshops
[Introduction to R](https://genomicsaotearoa.github.io/Introduction-to-R/)
[Vizualization](https://genomicsaotearoa.github.io/visualization_day/)
