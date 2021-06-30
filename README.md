# README
This document explains the data sources and how to use the replication materials for "The Negative Consequences of Gambling Opportunities on
Human Capital Formation: Evidence from Spain", Espadafor & Martínez (2021).

All the code and data will be also published and available in Harvard Dataverse once the paper is accepted for publication.

This replication package contains Stata/R data- and do-files/scripts to generate the results reported in "The Negative Consequences of Gambling Opportunities on
Human Capital Formation: Evidence from Spain" by Espadafor & Martínez (2021).

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

To replicate the results of Espadafor & Martínez (2021) you will need the following files:

- The file `gambling.dta` includes all the variables ready to replicate the main analysiis of this study. 
- The file `gambling.do` has the code to reproduce results in Fig.1 to Fig.3 and Fig.5
- The file `honestDID.r` has the code to reproduce results using the Callaway and Sant Anna (2020) estimator for staggered
difference-in-differences designs, which is reeported in Fig.4 and Fig S14-15 in the Supplementari Information Document.

The following files creates additional results under alternative specifications and alternative outcomes as reported in the online Supplementary Material document:

- The file `gambling_SI.do` has the code to reproduce all summary statistics (Tables 2-3 and S.Fig 2-4), Average effect and time-placebos (Tables 5-9 and S.Figure 5)
- The file `sorting.do` has the code to reproduce Tables S.10-S.14 and Fig.S9.
- The file `prices.dta` includes all the variables in the main study, and rent prices by neighborhoods from 2014-2017.
- The file `prices.do` includes the code to reproduce the results in Tables S15-S17 and Fig.S10.
- The file `starbucks.dta` includes all the variables in the main study, and schools' distance to Starbucks from 2014-2017.
- The file `starbucks.do` has the code to reproduce results in Table S18 and Fig.S11-12

### Software Requirements

- Stata (code was last run with version 16)
  - `estout` 
  - `rdrobust` 
  - the program "`0_setup.do`" will install all dependencies locally, and should be run once.


- R 3.4.3
  - `tidyr` (0.8.3)
  - `rdrobust` (0.99.4)
  - the file "`0_setup.R`" will install all dependencies (latest version), and should be run once prior to running other programs.


### Figure & tables list

| Figure/Table #    | Program                  | Line Number | Output file                      | Note                            |
|-------------------|--------------------------|-------------|----------------------------------|---------------------------------|
| Table 1           | 02_analysis/table1.do    |             | summarystats.csv                 ||
| Table 2           | 02_analysis/table2and3.do| 15          | table2.csv                       ||
| Table 3           | 02_analysis/table2and3.do| 145         | table3.csv                       ||
| Figure 1          | n.a. (no data)           |             |                                  | Source: Herodus (2011)          |
| Figure 2          | 02_analysis/fig2.do      |             | figure2.png                      ||
| Figure 3          | 02_analysis/fig3.do      |             | figure-robustness.png            | Requires confidential data      |




