This document explains the data source and how to use the replication materials for Espadafor & Martínez (2021).
All the code and data will be also published and available in Harvard Dataverse once the paper is accepted for publication.

Please email us: maria.canizares@eui.eu & sergi.martinez@eui.eu

# Data description

This section details the source of the data employed in this study.

## Main analysis:

This study uses several sources for data:

- Information on schools' characteristics and educational performance come from public administrative data yearly released by Madrid's education authorities, which is available here: https://gestiona3.madrid.org/wpad_pub/run/j/MostrarConsultaGeneral.icm

- Information on openings of betting houses is available as part of the census data provided by the Government of Madrid, which is also accessible here: https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=23160329ff639410VgnVCM2000000c205a0aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default


We restrict the sample to educational centers that offered the academic track in post-compulsory education (Bachillerato, in Spanish).  We obtained information on whether centers were privately or publicly funded, their location, their average grade obtained by each high school at the State-level exams, which grants access to university, and the number of students attending each year. 
Additionally, we extracted and linked the average household income level of the neighbourhood where high schools are located, which is also publicly available https://datos.madrid.es/sites/v/index.jsp?vgnextoid=71359583a773a510VgnVCM2000001f4a900aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD 

Information about the betting houses was extracted by the authors using the licenses issued by the Government of Madrid to betting houses companies. These licenses come from the following census record: "Censo de locales, sus actividades y terrazas de hostelería y restauración". We restricted our sample to private gambling facilities, excluding stores regulated by _Loterías y Apuestas del Estado_, the State-owned enterprise in charge of the most popular both football and lottery games. 

We coded each license's location and the year in which it was issued to match betting houses to high schools. After this, we calculated walking distances in meters from each high school to the closest betting house to assess each high school's access to gambling facilities. We employ a radius to divide Madrid high schools using a dummy variable switching on those education centers exposed to a betting house at less than 500m. The rationale behind this choice is that, according to the "Encuesta Domiciliaria de Mobilidad 2018" (Consorcio de Mobilidad de Madrid, Comunidad de Madrid), the average Madrid students' commuting to educational centers is 500 meters, as suggested by descriptive statistics shown in Table. S.1 and Figure. S.1. in the Supplementary Materials document.

## Placebo analysis

As part of the placebo tests, we extracted licenses issued to Starbucks. We then geolocated them and calculated walking distances from each high school to the closest Starbucks.

- Information on licences to Starbucks can be found in the census data provided by the Government of Madrid (see link above).

Finally, as part of the robustness checks, we used monthly rent prices by districts. We linked each high
school to the rent prices in their area. 

- The data on rent prices can be downloaded here: https://www.madrid.es/portales/munimadrid/es/Inicio/El-Ayuntamiento/Estadistica/Areas-de-informacion-estadistica/Edificacion-y-vivienda/Mercado-de-la-vivienda/Precios-de-la-vivienda/?vgnextfmt=default&vgnextoid=bf281b47a277b210VgnVCM1000000b205a0aRCRD&vgnextchannel=22613c7ea422a210VgnVCM1000000b205a0aRCRD


# Files description


## Main analysis:

To replicate the main analysis of Espadafor & Martínez (2021) you will need the following files:

- The file "gambling.dta" includes all the variables ready to replicate the main analysiis of this study. 
- The file "gambling.do" has the code to reproduce results in Fig.1 to Fig.3 and Fig.5
- The file "honestDID.r" has the code to reproduce results in Fig.4 and Fig S14-15 in the Supplementari Information Document.

In the Supplementary Materials we provide furthere analysis:

- The file "gambling_SI.do" has the code to reproduce all summary statistics (Tables 2-3 and S.Fig 2-4), Average effect and time-placebos (Tables 5-9 and S.Figure 5)
- The file "sorting.do" has the code to reproduce Tables S.10-S.14 and Fig.S9.


## Suplementary Analysis:

The replicate the placebo analysis of Espadafor & Martínez (2021) you will need the following files:

- The file "prices.dta" includes all the variables in the main study, and rent prices by neighborhoods from 2014-2017.
- The file "prices.do" includes the code to reproduce the results in Tables S15-S17 and Fig.S10.


- The file "starbucks.dta" includes all the variables in the main study, and schools' distance to Starbucks from 2014-2017.
- The file "starbuscks.do" has the code to reproduce results in Table S18 and Fig.S11-12





