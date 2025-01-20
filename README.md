# Digitalization-growth-urbanization

BEEM136 - FINAL PROJECT
Project title: An exploratory research into the relationship of digitalization (subscription-based economy), economic growth, and urban development
This study aims to untangle two research questions: (i) how digitalization correlates with eco- nomic growth; (ii) how urban development correlates with digitalization

**This file includes fundamental information to replicate the work crafted in the assignment**
**The package associated with this project includes: A pdf report, a do-file with full script, a folder of raw datasets, a folder of derived datasets, a folder of results graphs, and a README file**
**This project is done with Stata 18.5**

1. Data sources
Dataset title: International Panel Data Analysis of the Effect of Digitalization on Economic Growth
Published: 7 February 2024
doi: 10.17632/ctm7vvpp7n.1
Contributors: Abderrazek ELKHALDI, Nadia Sghaier, Monia Chikhaoui

Worldbank open data (Indicators: access_to_electricity, urban_population, GINI)

Geographic data of countries and regions are retrieved from World Administrative Boundaries - Countries and Territories
Source: https://public.opendatasoft.com/explore/dataset/world-administrative-boundaries/export/?location=2,42.18783,0&basemap=jawg.light


2. Libraries used:
estout: to generate descriptive statistics
shp2dta, spmap: to draw geographic graphs
coefplot: to export regression tables after running the models

3. Process to replicate research results:
Narrative 1 consists of 1 model
- Dependent var: log_gdp (economic growth)
- Independent var: 
DDI
DDI_sq (square of DDI)
Other control var for economic constraints: trade_openness, RD, capital (GFCF), population growth

Narrative 2 consists of 2 models
- Dependent var: DDI
- Independent var: urban population growth, square term of urban population growth, access to electricity, gini, log_gdp

Method used: fixed-effects regression
Data properties: strongly balanced, panel, continuous variables

4. Data cleaning and variable generation process:
- Master file is combined with digitalization_based.dta, access_to_electricity.dta, urban_pop.dta, and gini_index.dta
- access_to_electricity.dta, urban_pop.dta, and gini_index.dta are reshaped from wide to long format, and standardized with mean approx 0 and standard dev 1.
- Keys to merge: country_code and year
- DDI is created by principal component analysis method with 4 variables (MPS, IU, FPS, BBS). This is contributed by ELKHALDI et.al (2024) and is defaultly contained in the master file.
- DDI_sq (quadratic term of DDI) = square of DDI
- Urban population growth is generated by taking natural log of urban population

5. Other explanations in term of data:
- The process of generating geographical graphs including merging and dealing with missing values is explained in Appendix 6.2, pdf file.
- The process of reproducing digitalization index (DDI) is elaborated in Appendix 6.4, pdf file.
