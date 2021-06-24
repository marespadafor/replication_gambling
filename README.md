# Data description

This section details the source of the data employed in this study.

The file "gambling.dta" includes all the variables ready to replicate the main analysiis of this study. 

This study uses several sources for data:
- Information on schools' characteristics and educational performance come from public administrative data yearly released by Madrid's education authorities, which is available \href{https://gestiona3.madrid.org/wpad_pub/run/j/MostrarConsultaGeneral.icm}{\textit{here}}. 

- Information on openings of betting houses is available as part of the census data provided by the Government of Madrid, which is also accessible \href{https://datos.madrid.es/portal/site/egob/menuitem.c05c1f754a33a9fbe4b2e4b284f1a5a0/?vgnextoid=23160329ff639410VgnVCM2000000c205a0aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD&vgnextfmt=default}{\textit{here}}.


We restrict the sample to educational centers that offered the academic track in post-compulsory education (Bachillerato, in Spanish).  We obtained information on whether centers were privately or publicly funded, their location, their average grade obtained by each high school at the State-level exams, which grants access to university, and the number of students attending each year. 
Additionally, we extracted and linked the average household income level of the neighbourhood where high schools are located, which is also publicly available \href{https://datos.madrid.es/sites/v/index.jsp?vgnextoid=71359583a773a510VgnVCM2000001f4a900aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD}{\textit{here}}. \par 

Information about the betting houses was extracted by the authors using the licenses issued by the Government of Madrid to betting houses companies. These licenses come from the following census record: `Censo de locales, sus actividades y terrazas de hostelería y restauraci{ó}n'. We restricted our sample to private gambling facilities, excluding stores regulated by \textit{Loterías y Apuestas del Estado}, the State-owned enterprise in charge of the most popular both football and lottery games. 
We coded each license's location and the year in which it was issued to match betting houses to high schools. After this, we calculated walking distances in meters from each high school to the closest betting house to assess each high school's access to gambling facilities. We employ a radius to divide Madrid high schools using a dummy variable switching on those education centers exposed to a betting house at less than 500m. The rationale behind this choice is that, according to the `Encuesta Domiciliaria de Mobilidad 2018' (Consorcio de Mobilidad de Madrid, Comunidad de Madrid), the average Madrid students' commuting to educational centers is 500 meters, as suggested by descriptive statistics shown in Table. S.1 and Figure. S.1. in the Supplementary Materials document.
