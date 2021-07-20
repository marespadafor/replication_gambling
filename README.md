# README
This document explains the data sources and how to use the replication materials for "The Negative Consequences of Betting on
Human Capital Formation: Evidence from Spain", Espadafor & Martínez (2021).

All the code and data will be also published and available in Harvard Dataverse once the paper is accepted for publication.

This replication package contains Stata/R data- and do-files/scripts to generate the results reported in "The Negative Consequences of Sport Gambling Opportunities on Human Capital Formation: Evidence from Spain" by Espadafor & Martínez (2021).

Please carefully read this document to replicate the resutls of this study. If you face any problem, drop us a line: maria.canizares@eui.eu & sergi.martinez@eui.eu

## Data description and sources

This section details the source of the data employed in this study.

This study uses several sources for data, which are publicly available.


- Information on schools' characteristics and educational performance come from public administrative data yearly released by Madrid's education authorities, which is available here: https://gestiona3.madrid.org/wpad_pub/run/j/MostrarConsultaGeneral.icm. A version of this data, including educational centers that offered the academic track in post-compulsory education (Bachillerato, in Spanish), has been published and it is publicly available to download here: Espadafor, Mar, 2021, "Panel Data on High Schools in Madrid (2013-2018)", https://doi.org/10.7910/DVN/K4NSBK, Harvard Dataverse, V1, UNF:6:B5vf/YEfEjiSv/71pOi4Kw== [fileUNF] 
 

- Information on openings of betting houses is available as part of the census data provided by the Government of Madrid, which is also accessible here: https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=23160329ff639410VgnVCM2000000c205a0aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default Information about the betting houses was extracted by the authors using the licenses issued by the Government of Madrid to betting houses companies. These licenses come from the following census record: "Censo de locales, sus actividades y terrazas de hostelería y restauración". We restricted our sample to private gambling facilities, excluding stores regulated by _Loterías y Apuestas del Estado_, the State-owned enterprise in charge of the most popular both football and lottery games. 



We coded each license's location and the year in which it was issued to match betting houses to high schools. After this, we calculated walking distances in meters from each high school to the closest betting house to assess each high school's access to gambling facilities. We employ a radius to divide Madrid high schools using a dummy variable switching on those education centers exposed to a betting house at less than 500m. The rationale behind this choice is that, according to the "Encuesta Domiciliaria de Mobilidad 2018" (Consorcio de Mobilidad de Madrid, Comunidad de Madrid), the average Madrid students' commuting to educational centers is 500 meters, as suggested by descriptive statistics shown in Table. S.1 and Figure. S.1. in the Supplementary Materials document.

Additionally, we extracted and linked the average household income level of the neighbourhood where high schools are located.

- Information on neighborhoods income levels is extracted from the "Panel de indicadores de distritos y barrios de Madrid. Estudio sociodemográfico" 2016-2020, which is also publicly available here: https://datos.madrid.es/sites/v/index.jsp?vgnextoid=71359583a773a510VgnVCM2000001f4a900aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD 


As part of the placebo tests, we extracted licenses issued to Starbucks. We then geolocated them and calculated walking distances from each high school to the closest Starbucks.

- Information on licences to Starbucks can be found in the census data provided by the Government of Madrid (see link above).

Finally, as part of the robustness checks, we used monthly rent prices by districts. We linked each high
school to the rent prices in their area. 

- The data on rent prices is extracted from Madrid open access records, "Renta mensual de la vivienda en alquiler (€/m2 construido) por Distrito y por Trimestre". It can be downloaded here: https://www.madrid.es/portales/munimadrid/es/Inicio/El-Ayuntamiento/Estadistica/Areas-de-informacion-estadistica/Edificacion-y-vivienda/Mercado-de-la-vivienda/Precios-de-la-vivienda/?vgnextfmt=default&vgnextoid=bf281b47a277b210VgnVCM1000000b205a0aRCRD&vgnextchannel=22613c7ea422a210VgnVCM1000000b205a0aRCRD

A copy of all the data is provided as part of this archive. The data are in the public domain. 

## Files description

To replicate the results of Espadafor & Martínez (2021) you will need the following files and codes:

- The file `gambling_data.dta` includes all the main variables ready to replicate the main analysis of this study. 
- The files `01_estimates_main.do` to `02_estimates_logdist.do` has the code to reproduce results in each figure in the manuscript.
- The file `06_code_for_PanelMatchdata.do` has the code to reproduce results using the Callaway and Sant Anna (2020) estimator for staggered
difference-in-differences designs, which is reeported in Fig.4 and then in Fig S14-15 in the Supplementari Information Document.
- The file `03_estimates_placebo_number_student.do` has the code to reproduce results using a placebo outcome: number of students. 

The following files creates additional results under alternative specifications and alternative outcomes as reported in the online Supplementary Material document:

- The file `08_SI.do` has the code to reproduce all tables presented in the SI:
  - All summary statistics (Tables S2-3), Average effect and time-placebos (Tables S5-9)
  - The likelihood of school being treated by type of schoool (Table S4)
  - Replication of main results using logdistance (Table S10)
  - Results from robutsness checks for compositonal change using number of students (Tables S11-S14) and rent prices (Tables S15-17)
  - Restuls from placebo test using Starbacks (Table S18)
  - Results using a different treatment definition, <200m (Table S19)


### Figure & tables list

| Figure/Table | Script      | Data                                                  | Note:                                       |
|--------------|-------------|-------------------------------------------------------|---------------------------------------------|
| Figure 1     | figure1.r   | apuestas_tipos_.dta                                   |                                             |
| Figure 2     | figure2.r   | pau2.dta                                              | Source: 01_estimates_main.do                |
| Figure 3     | figure3.r   | distance2.dta                                         | Source: 02_estimates_logdist.do             |
| Figure 4     | figure4.r   | gambling_data.dta                                     |                                             |
| Figure 5     | figure5.r   | gambling_data.dta, num2.dta                           | Source: 03_estimates_placebo_number_student |  
| Figure S1    | figureS1.r  | movilidad_merged_1503.dta                             |                                             |
| Figure S2    | figureS2.r  | apuestas_tipos_.dta, colegiosX_.dta, all_mapa2.dta    |                                             |
| Figure S3    | figureS3.r  |                                                       |                                             | 
| Figure S4    | figureS4.r  | panelmatch.dta                                        | Source: 06_code_for_PanelMatchdata.do       |
| Figure S5    | figureS5.r  | pau2.dta                                              | Source: 01_estimates_main.do                |
| Figure S6    | figureS6.r  | gambling_data.dta                                     |                                             |
| Figure S7    | figureS7.r  | gambling_data.dta                                     |                                             |
| Figure S8    | figureS8.r  | distance2.dta                                         | Source: 02_estimates_logdist.do             |
| Figure S9    | figureS9.r  | gambling_data.dta, num2.dta                           | Source: 03_estimates_placebo_number_student |  
| Figure S10   | figureS10.r | price2.dta                                            | Source: 04_estimates_placebo_rentprices.do  |
| Figure S11   | figureS11.r | gambling_data.dta                                     |                                             |
| Figure S12   | figureS12.r | star1.dta                                             | Source: 05_estimates_placebo_starbucks.do   |
| Figure S13   | figureS11.r | gambling_data.dta                                     |                                             |
| Figure S14   | figureS11.r | gambling_data.dta                                     |                                             |
| Table S1     | appendix.do | gambling_data.dta                                     |                                             |
| Table S2     | appendix.do | gambling_data.dta                                     |                                             |
| Table S3     | appendix.do | gambling_data.dta                                     |                                             |
| Table S4     | appendix.do | gambling_data.dta                                     |                                             |
| Table S5     | appendix.do | gambling_data.dta                                     |                                             |
| Table S6     | appendix.do | gambling_data.dta                                     |                                             |
| Table S7     | appendix.do | gambling_data.dta                                     |                                             |
| Table S8     | appendix.do | gambling_data.dta                                     |                                             |
| Table S9     | appendix.do | gambling_data.dta                                     |                                             |
| Table S10    | appendix.do | gambling_data.dta                                     |                                             |
| Table S11    | appendix.do | gambling_data.dta                                     |                                             |
| Table S12    | appendix.do | gambling_data.dta                                     |                                             |
| Table S13    | appendix.do | gambling_data.dta                                     |                                             |
| Table S14    | appendix.do | gambling_data.dta                                     |                                             |
| Table S15    | appendix.do | gambling_data.dta                                     |                                             |
| Table S16    | appendix.do | gambling_data.dta                                     |                                             |
| Table S17    | appendix.do | gambling_data.dta                                     |                                             |
| Table S18    | appendix.do | gambling_data.dta                                     |                                             |

### Variable description

| Variable name:     |  Description                                                     |  
|--------------------|------------------------------------------------------------------|            
| school_id          | High School's unique id                                          | 
| year               |                                                                  |
| apuestas_id        | Betting houses' unique id                                        |
| km_to_apuestas_id  | Distance from school to closest betting house in km              |
| metres             | Distance from school to closest betting house in m               |
| metres_years       | Distance from school to closest betting house in m, by year      |
| name               | High School's name                                               |
| district           | District where high schools are located                          |
| postcode           | Postcode where high schools are located                          |
| pau                | Average high school performance in PAU                           |
| pauXXXX            | Average high school performance in PAU by academic year          |
| num                | Average number of students by high school                        |
| nXXXX              | Average number of students by high school and academic year      |          
| publico            | Whether schools are publicly financed                            |
| treat              | Takes 1 if there is a betting house closer than 500m             |
| treat_year         | Takes 1 if there is a betting house closer than 500m, by year    |
| logdist_year       | Logged distance from school to closest bettng houses by year     |
| alquiler           | Rent prices euros/m2 by district                                 |
| star_id            | Starbucks' unique id                                             |
| km_to_star_id      | Distance from school to closest Starbucks in km                  |
| metres_year_star   | Distance from school to closest Starbucks in m by year           |    
| logdist_year_star  | Logged distance from school to closest Starbucks                 | 
| renta              | Average income where schools' are located                        |
| renta2             | Takes 1 if average income is above the average of Madrid         |
| tf                 | The first period when a particular observation is treated        |

| Data file           | Description                                                       |  
|---------------------|-------------------------------------------------------------------|
| gambling_data.dta   | Main dataset containing all variables described above             |
| apuestas_tipos_.dta | Dataset containing type of betting houses                         |
| all_mapa2.dta       | Dataset containing longtitude and latitude from all units         |
| colegios2_.dta      | Dataset containing longitude and latitude for all schools         |
| colegios3_.dta      | Dataset containing longitude and latitude for all public schools  |  
| colegios4_.dta      | Dataset containing longitude and latitude for all private schools | 
| dapuestas_year.dta  | Dataset containing betting house information by year              |

### Software Requirements

- Stata (code was last run with version 16)
  - `estout` 
  - `xtreg`
  - `estab` 
  
- R (code was last run wth version 4.0.4 (2021-02-15))
  - Platform: x86_64-apple-darwin17.0 (64-bit)
  - Running under: macOS Mojave 10.14.3
  - Attached base packages:
    [1] stats     graphics  grDevices utils     datasets  methods   base     

  - other attached packages:
    [1] foreign_0.8-81 sf_0.9-6       sp_1.4-2       ggmap_3.0.0   
    [5] ggplot2_3.3.3  haven_2.3.1   

  - loaded via a namespace (and not attached):
    [1] Rcpp_1.0.6          pillar_1.5.0        compiler_4.0.4     
    [4] plyr_1.8.6          class_7.3-18        forcats_0.5.1      
    [7] bitops_1.0-6        tools_4.0.4         lifecycle_1.0.0    
    [10] tibble_3.0.6        gtable_0.3.0        lattice_0.20-41    
    [13] pkgconfig_2.0.3     png_0.1-7           rlang_0.4.10       
    [16] cli_2.3.0           DBI_1.1.1           e1071_1.7-3        
    [19] stringr_1.4.0       withr_2.4.1         dplyr_1.0.4        
    [22] httr_1.4.2          generics_0.1.0      RgoogleMaps_1.4.5.3
    [25] vctrs_0.3.6         hms_1.0.0           classInt_0.4-3     
    [28] grid_4.0.4          tidyselect_1.1.0    glue_1.4.2         
    [31] R6_2.5.0            jpeg_0.1-8.1        fansi_0.4.2        
    [34] readr_1.4.0         tidyr_1.1.2         purrr_0.3.4        
    [37] magrittr_2.0.1      units_0.6-7         scales_1.1.1       
    [40] ellipsis_0.3.1      assertthat_0.2.1    colorspace_2.0-0   
    [43] KernSmooth_2.23-18  utf8_1.1.4          stringi_1.5.3      
    [46] munsell_0.5.0       rjson_0.2.20        crayon_1.4.1 


