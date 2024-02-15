# Kern_mosquito_shiny

This repository contains all the script and data necessary for running and hosting the Shiny app. Please see [this repository](https://github.com/n-mcmanus/mosq_shiny_data "mosq_shiny_data")  for more information on data used and code for how it was generated. 


## File structure:
* `www/`: folder with images and videos included in the Shiny.
* `data/`:  contains the raw and generated data used in the Shiny
    * `central_valley/`: contains the associated SHP files for the entire CA central valley (Alluvial_Bnd.shp) as well as the portion of the valley only within Kern County (valley.shp)
    * `counties_ca/`: contains the associated SHP files for all counties in CA (cnty19_1.shp) as well as Kern county (kern.shp)
    * `zipcodes/`: contains the associated SHP files for all zip codes in CA (CA_Zips.shp) as well as the portion of zip codes only located within both Kern County and the CA central valley (kern_zips.shp)
    * `temp/`: contains mean daily air temperature data sourced from PRISM.
        * `kern_tmean_GEE_output.csv` is the output generated from the GEE code.
        * `kerm_tmean_2010_20230930.csv` is a wrangled copy of the temperature data, including categorical information on whether a day falls within the suitable or optimal range for *Culex* spp mosquitoes. This is the file used for temperature plots in the shiny.
    * `traps/`: mosquito abundance and MIR data sourced from the Kern Mosquito & Vector Control District.
        * `andy/`: contains the KMVCD abundance and MIR data that has been processed and provided by Andrew MacDonald
        * `plotting/`: the wrangled version of the abundance and MIR data used for generating plots in the shiny app.
    * `water/`: contains all the surface water data for 2022-2023
        * `summed_water_90m_2022_2023.tif`: all the acceptable images (no cloud interference) for 2022-2023 in path 42 were added to create this "heatmap", in which the value of a pixel indicates how many dates surface water was present (max 35). This data was then upscaled to 90m resolution and then reprojected into a Leaflet-friendly CRS to align with the basemap. This raster is displayed on the surface water map in the shiny.
        * `water_acre_zipcode.csv`: zonal information on the acreage and cell count of surface water by zip code in Kern county. This data is used for generating water plots in the shiny app.
