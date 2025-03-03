Data sets for the e-sensing project.
================

<img src="inst/extdata/sticker/sits_sticker.png" alt="SITS icon" align="right" height="150" width="150"/>

This project contains in situ data sets used in the e-sensing project. These data sets consists of time series of selected locations which are used to train machine learning models, csv files containing training locations, and data cubes to run examples of sits usage.

To load these data sets:

`devtools::install_github("e-sensing/sitsdata")`

## Time series samples for classification using machine learning

### Data availability 

R package `sitsdata` contains  time series to be used for classification with machine learning methods which are available when the package is loaded using `library(sitsdata)`. All satellite image time series have the following columns: 

- longitude (East-west coordinate of the time series sample in WGS 84).
- latitude (North-south coordinate of the time series sample in WGS 84).
- start_date (initial date of the time series).
- end_date (final date of the time series).
- label (the class label associated to the sample).
- cube (the name of the image data cube associated with the data).
- time_series (list  with the values of the time series).

### LULC for Cerrado Biome using MODIS

A dataset containing 50,160 time series samples from Brazilian Cerrado biome, with 12 classes ("Dense_Woodland", "Dunes", "Fallow_Cotton", "Millet_Cotton", "Pasture", "Rocky_Savanna", "Savanna", "Savanna_Parkland", "Silviculture",  "Soy_Corn", "Soy_Cotton", "Soy_Fallow"). Each time series covers 12 months (23 data points) from MOD13Q1 product, and has 4 bands (`EVI`, `NDVI`, `MIR`, and `NIR`). 

Reference: Lorena Santos, Karine Ferreira, Gilberto Camara, Michelle Picoli, Rolf Simoes, “Quality control and class noise reduction of satellite image time series”. ISPRS Journal of Photogrammetry and Remote Sensing, vol. 177, pp 75-88, 2021. https://doi.org/10.1016/j.isprsjprs.2021.04.014.

Example: See chapter ["Improving the Quality of Training Samples"](https://e-sensing.github.io/sitsbook/improving-the-quality-of-training-samples.html) in the `sits` [reference book](https://e-sensing.github.io/sitsbook/index.html)

Usage: `data("samples_cerrado_mod13q1")`

License: Creative Commons Attribution 4.0 International (CC BY 4.0).


### Land Use and Land Cover for Mato Grosso (Brazil) using MODIS

A dataset containing 1,892 time series samples from Brazilian Mato Grosso State (Amazon and Cerrado biomes). It has 9 classes ("Cerrado", "Fallow_Cotton", "Forest", "Millet_Cotton", "Pasture", "Soy_Corn", "Soy_Cotton", "Soy_Fallow", "Soy_Millet"). Each time series comprehends 12 months (23 data points) from the MOD13Q1 product, and has 6 bands.

References: 

- Michelle Picoli, Gilberto Camara, et al., “Big Earth Observation Time Series Analysis for Monitoring Brazilian Agriculture”. ISPRS Journal of Photogrammetry and Remote Sensing, 145: 328-339, 2018. DOI: 10.1016/j.isprsjprs.2018.08.007.

- Câmara, Gilberto; Picoli, Michelle, et al., Land cover change maps for Mato Grosso State in Brazil: 2001-2017 (version 3). PANGAEA, 2021. https://doi.org/10.1594/PANGAEA.899706. 

Example: See chapter ["Machine Learning for Data Cubes"](https://e-sensing.github.io/sitsbook/machine-learning-for-data-cubes.html) in the `sits` [reference book](https://e-sensing.github.io/sitsbook/index.html)

Usage: `data("samples_matogrosso_mod13q1")`

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

### Land Use and Land Cover for part of Brazilian Cerrado using CBERS-4 AWFI

A dataset with 922 time series sampled on the Brazilian Cerrado, obtained from a set of CBERS-4 AWFI images over a subset of tile "022024" of cube "CB4_64_16D_STK" of the Brazilian Data Cube. CBERS-4 AWFI is a sensor with 64 meter resolution. Each time series has one year of 16-day composites from AWFI images, comprising 23 data points and 6 bands ("BAND13", "BAND14", "BAND15", "BAND16", "NDVI", "EVI"). 

Reference: Karine Ferreira, Gilberto Queiroz, et al., “Earth Observation Data Cubes for Brazil: Requirements, Methodology and Products”. Remote Sensing, 12, 4033, 2020. https://doi.org/10.3390/rs12244033.

Example: See chapter ["Image Classification in Data Cubes"](https://e-sensing.github.io/sitsbook/image-classification-in-data-cubes.html) in the `sits` [reference book](https://e-sensing.github.io/sitsbook/index.html).

Usage: `data("samples_cerrado_cbers")`.

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

### Deforestation in Rondonia (Brazil) using SENTINEL-2/2A data

A dataset containing a tibble with 480 times series collected over the state of Rondonia (Brasil) for detecting deforestation from the period 2020-06-04 to 2021-08-26. Each time series contains 8 bands ("B02", "B03", "B04", "B08", "B8A", "B11", "B12") and three indices ("NDVI", "EVI", "NBR") and 4 classes ("Burned_Area", "Forest", "Highly_Degraded" and "Cleared_Area").

Example: See chapter ["Uncertainty and active learning"](https://e-sensing.github.io/sitsbook/uncertainty-and-active-learning.html) in the `sits` [reference book](https://e-sensing.github.io/sitsbook/index.html).

Usage: `data("samples_prodes_4classes")`.

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

### Yearly deforestation samples of 9 classes on Amazonia biome from SENTINEL-2/2A images

A dataset containing a tibble with 6007 times series collected over the state of Rondonia (Brasil) for detecting deforestation and degradation from the period 2022-01-05 to 2022-12-23. Each time series contains 3 bands ("B02", "B8A", "B11") and three indices ("NDVI", "EVI", "NBR") and 9 classes ("Clear_Cut_Bare_Soil", "Clear_Cut_Burned_Area", "Clear_Cut_Vegetation", "Forest", "Mountainside_Forest", "Riparian_Forest", "Seasonally_Flooded", "Water", "Wetland").

Usage: `data("samples_deforestation")`.

License: Creative Commons Attribution 4.0 International (CC BY 4.0).


## CSV files with samples of land use and land cover

R package `sitsdata` contains CSV files to be used for extraction of time series from data cubes. All CSV files have the following columns: 

- longitude (East-west coordinate of the time series sample in WGS 84).
- latitude (North-south coordinate of the time series sample in WGS 84).
- start_date (initial date of the time series).
- end_date (final date of the time series).
- label (the class label associated to the sample).

### Mali Crop Type Data for 2019

This dataset produced by the NASA Harvest team includes crop types labels from ground referencing matched with time-series of Sentinel-2 imagery during the growing season.  Crop types include Maize, Millet, Rice and Sorghum. Funding for this dataset is provided by Lutheran World Relief, Bill & Melinda Gates Foundation, and University of Maryland NASA Harvest program.

Data provided by the Radiant Earth MLHub (https://mlhub.earth/data/umd_mali_crop_type).

Reference: Nakalembe, C.L., Ouedraogo, H., Diarra, N., & Kuzimbu, B. (2021). 2019 Mali Crop Type Training Data for Machine Learning (Version 1.0) Radiant MLHub. Access date: 11 August 2022. https://doi.org/10.34911/rdnt.tgz68o

Usage: `read.csv(system.file("extdata/csv/mali_crops.csv", package = "sitsdata"))`.

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

### Rwanda Crop Type Classification Dataset

RTI International (RTI) generated 2,611 labeled point locations representing 19 different land cover types, clustered in 5 distinct agroecological zones within Rwanda. These land cover types were reduced to three crop types (Banana, Maize, and Legume), two additional non-crop land cover types (Forest and Structure), and a catch-all Other land cover type to provide training/evaluation data for a crop classification model.

Data provided by the Radiant Earth MLHub (https://mlhub.earth/data/umd_mali_crop_type).

References:

- Rineer J., Beach R., Lapidus D., O’Neil M., Temple D., Ujeneza N., Cajka J., & Chew R. (2021), “Drone Imagery Classification Training Dataset for Crop Types in Rwanda”, Version 1.0, Radiant MLHub https://doi.org/10.34911/rdnt.r4p1fr.

- Chew, R., Rineer, J., Beach, R., O’Neil, M., Ujeneza, N., Lapidus, D., Miano, T., Hegarty-Craver, M., Polly, J., & Temple, D. S. (2020). Deep neural networks and transfer learning for food crop identification in UAV images. Drones, 4(1), 7. https://doi.org/10.3390/drones4010007

Usage: `read.csv(system.file("extdata/csv/rwanda_crops.csv", package = "sitsdata"))`

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

### Uganda Crop Type Classification Dataset

This dataset contains crop types and field boundaries along with other metadata collected in a campaign run by Dalberg Data Insights in the end of September 2017, as close as possible to the harvest period of 2017. Post ground data collection, Radiant Earth Foundation conducted a quality control of the polygons using Sentinel-2 imagery of the growing season as well as Google basemap imagery, and removed several polygons that overlapped with infrastructure or built-up areas. 

Data provided by the Radiant Earth MLHub (https://mlhub.earth/data/ref_african_crops_uganda_01).

Reference: Bocquet, C., & Dalberg Data Insights. (2019) "Dalberg Data Insights Uganda Crop Classification", Version 1.0, Radiant MLHub. Access date: 12 August 2022. https://doi.org/10.34911/RDNT.EII04X.

Usage: `read.csv(system.file("extdata/csv/uganda_crops.csv", package = "sitsdata"))`

License: Creative Commons Attribution 4.0 International (CC BY 4.0).


## Samples from the Fields of the World (FTW) dataset

[Fields of The World (FTW)](https://source.coop/repositories/kerner-lab/fields-of-the-world/description) is a comprehensive benchmark dataset designed to enhance the development of machine learning models for instance segmentation of agricultural field boundaries. This dataset aims to meet the growing need for accurate and scalable field boundary data for global agricultural monitoring and assessments.

### Field Boundaries for Brazil

This dataset is supplementary material for a paper published in the Data in Brief journal. It provides monthly land use information for 1,854 fields from October 2019 to September 2020, covering Luís Eduardo Magalhães (LEM) and other municipalities in the western region of Bahia state, Brazil. The dataset includes 14 labeled classes ("Beans", "Brachiaria", "Cerrado", "Coffee", "Conversion area", "Corn", "Cotton", "Crotalaria", "Eucalyptus", "Hay", "Millet", "Pasture", "Sorghum", and "Soybean"). The paper describes the methods and procedures applied in data collection.

Reference: Oldoni, Lucas Volochen; Sanches, Ieda Del’Arco; Picoli, Michelle Cristina A.; Covre, Renan Moreira; Fronza, José Guilherme (2020), “LEM+ dataset: for agricultural remote sensing applications”, Mendeley Data, V1. http://dx.doi.org/10.17632/vz6d7tw87f.1

Usage: `library(arrow)`

`read_parquet(system.file("extdata/parquet/field_boundaries_for_brazil_2020.parquet", package = "sitsdata"))`.

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

### Field Boundaries for Kenya

This is a dataset released as a part of the Bird’s-Eye project, a collaboration between Pula and Tetra Tech under the Enabling Crop Analytics at Scale Project. This work, funded by the Bill & Melinda Gates Foundation, is meant to foster the collection of Ground truth georeferenced Agriculture labelled datasets that would improve predictive analytics in smallholder agriculture, through the use of Artificial intelligence and Machine Learning (AI/ML) and satellite imagery. The dataset includes 6 labeled classes ("Beans", "Greengrams", "Irish_Potatoes", "Maize", "None" and "Sorghum").

Reference: Bird’s-Eye. (2022). A collaboration between Pula and Tetra Tech under Enabling Crop Analytics at Scale project. Access date: 06 February 2025. https://ecaas.pula.io

Usage: `library(arrow)`

`read_parquet(system.file("extdata/parquet/field_boundaries_for_Kenya_2022.parquet", package = "sitsdata"))`.

License: GPL-2.0-or-later

### Field Boundaries for Rwanda

This dataset contains field boundaries for smallholder farms in eastern Rwanda. The Nasa Harvest program funded a team of annotators from TaQadam to label Planet imagery for the 2021 growing season for the purpose of conducting the Rwanda Field boundary detection Challenge.

Reference: NASA Harvest. (2021). NASA’s Global Food Supply and Agriculture Consortium. University of Maryland. Access date: 06 February 2025. https://nasaharvest.org

Usage: `library(arrow)`

`read_parquet(system.file("extdata/parquet/field_boundaries_for_Rwanda_2021.parquet", package = "sitsdata"))`.

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

## Image Data cubes used for classification examples


### Indices and spectral bands of SENTINEL-2/2A images for the 20LMR tile in Rondonia (Brazil)

This dataset contains 23 TIF files with 3 spectral bands (B02, B8A, and B11) and 3  indices (EVI, NDVI, and NBR) of SENTINEL-2/2A for the period 2022-01-05 to 2022-12-23. These images correspond to tile 20LMR of the MGRS grid. These files with associated timeline are used to test and validate the algorithms in the R package "sits". 

Usage: `system.file("extdata/Rondonia-20LMR", package = "sitsdata")`

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

### EVI and NDVI MOD13Q1 images for Sinop (Brazil)

TIF files containing 23 EVI and NDVI MOD13Q1 images for the period 2013-09-14 to 2014-08-29, covering the agricultural year in the city of Sinop (Mato Grosso). These files with associated timeline are used to test and validate the algorithms in the R package "sits". 

Example: See chapter ["Introduction to SITS"](https://e-sensing.github.io/sitsbook/introduction-to-sits.html) in the `sits` [reference book](https://e-sensing.github.io/sitsbook/index.html)

Usage: `system.file("extdata/sinop", package = "sitsdata")`

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

### EVI and NDVI CBERS-4 AWFI images for Brazilian Cerrado

TIF files containing 23 EVI and NDVI CBERS-4 AWFI images for the period 2018-08-29 to 2019-08-13, covering the agricultural year in the Brazilian Cerrado near the city of Barreiras (Bahia). These files with associated timeline are used to test and validate the algorithms in the R package "sits". 

Reference: Karine Ferreira, Gilberto Queiroz, et al., “Earth Observation Data Cubes for Brazil: Requirements, Methodology and Products”. Remote Sensing, 12, 4033, 2020. https://doi.org/10.3390/rs12244033.

Example: See chapter ["Image Classification in Data Cubes"](https://e-sensing.github.io/sitsbook/image-classification-in-data-cubes.html) in the `sits` [reference book](https://e-sensing.github.io/sitsbook/index.html).

Usage: `system.file("extdata/CBERS", package = "sitsdata")`

License: Creative Commons Attribution 4.0 International (CC BY 4.0).

### LULC classification using Landsat-8 for the Brazilian Cerrado

A data cube containing classified images of a Landsat-8 data cube for the Brazilian Cerrado biome, as described in the paper by Simoes et al. (2021).  

Reference: Simoes, Rolf, Gilberto Camara, Gilberto Queiroz, Felipe Souza, Pedro R. Andrade, Lorena Santos, Alexandre Carvalho, and Karine Ferreira. 2021. "Satellite Image Time Series Analysis for Big Earth Observation Data" Remote Sensing 13, no. 13: 2428. https://doi.org/10.3390/rs13132428.

Example: See chapter ["Validation and accuracy measurements"](https://e-sensing.github.io/sitsbook/validation-and-accuracy-measurements.html) in the `sits` [reference book](https://e-sensing.github.io/sitsbook/index.html)

Usage: `system.file("extdata/Cerrado", package = "sitsdata")`

License: Creative Commons Attribution 4.0 International (CC BY 4.0).




