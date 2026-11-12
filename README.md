Degrees and kinds of social differentiation in survey ceramics from the Río Frío basin, Sierra Nevada de Santa Marta, Colombia (under review)
--------------------------------------------------------------
This repository contains the code and data for a framework designed to measure both the degree and the kind of social differentiation among residential units from survey ceramics. The protocol integrates (1) regional proportions of sherd attributes estimated with residential units as clusters, and comparisons between periods within the same sites with Holm-adjusted p values, (2) the degree of differentiation as the mean Euclidean distance between unit assemblages per standardized variable, compared with two chance expectations that reassign either sherds or whole collection locations of similar size, (3) controls for far outliers, single-location assemblages, alternative sample-size minima and spatial structure, (4) nonmetric multidimensional scaling in three dimensions and average-linkage clustering, and (5) quasibinomial logistic regressions of attribute shares on site size with HC3 standard errors, Spearman rank correlations and negative binomial count models for comparison. The protocol is applied to Neguanje (c. AD 100-700), Buritaca (c. AD 700-1000) and Tairona (c. AD 1000-1600) residential units in the Río Frío basin, Sierra Nevada de Santa Marta, Colombia.

Data Archive:
----------------------------------
- The nine spatial inputs are stored in this repository as R data files (.RData). Each file holds one sf object in WGS 84 / UTM zone 18N (EPSG:32618).
- The R notebook loads them from a local folder, checks their coordinate reference systems, feature counts and the attribution of every sherd to its unit, and stops if any check fails.

Data Files:
----------------------------------
1. CERAMICS_RIO_FRIO_2026.RData (object CERAMICS_RIO_FRIO_2026), 12,058 sherd records as points, with ceramic type, period, surface treatment, decoration, vessel form, function, rim type, rim diameter, firing core and production steps.
2. TAIRONA_POLYGONS_SITES.RData (object poly_tai), 551 Tairona residential sites as polygons, with area in hectares.
3. TAIRONA_STRUCTURES.RData (object str_tai), 2,526 terraces as points, with terrace diameter.
4. NEGUANJE_WIDE_FORMAT_DATABASE_2026.RData (object wf_neg), 190 Neguanje residential units as polygons, with unit totals of sherds, vessel functions and terraces.
5. BURITACA_WIDE_FORMAT_DATABASE_2026.RData (object wf_bur), 178 Buritaca residential units as polygons, with the same fields.
6. TAIRONA_WIDE_FORMAT_DATABASE_2026.RData (object wf_tai), 176 Tairona residential sites with sherds as polygons, used to validate the attribution of Tairona sherds.
7. NEGUANJE_STRUCTURES.RData (object str_neg), 365 terraces with Neguanje sherds as points.
8. BURITACA_STRUCTURES.RData (object str_bur), 319 terraces with Buritaca sherds as points.
9. POLYGON_SURVEY_RIO_FRIO.RData (object survey), the 52.2 km² survey area as one polygon.

Repository Structure:
----------------------------------
1. R Code Files:
   - The main R notebook (ARC_RIO_FRIO_GITHUB.Rmd) contains the code to:
     a) Load required packages and set up the CPU parallel backend.
     b) Load the nine RData inputs, assign each sherd to its Tairona site and to the residential unit of its own period, and validate these assignments against the unit databases.
     c) Estimate regional proportions, within-site differences between periods, rim diameters and production steps by vessel form.
     d) Measure the degree of differentiation against the two chance expectations, with controls for far outliers, single-location assemblages, sample-size minima and spatial structure.
     e) Perform the multidimensional scaling, the clustering and the site-size models.
     f) Generate Figures 2 through 6 and Tables 1 and 2 as presented in the manuscript, with the numerical summary of each figure, and export the figures as 600 dpi TIFF and PDF files.
     g) Record the analysis parameters, the random number settings, an audit of every reported p value and the session information.
   - Figure 1, the location map, was prepared separately and is not produced by the notebook.

Software and Key Package Versions:
----------------------------------
- R version: 4.6.1
- GEOS 3.14.1, GDAL 3.12.1 and PROJ 9.7.1, through sf

Key R packages used in this project include:
    • dplyr: version 1.2.1
    • future: version 1.75.0
    • future.apply: version 1.20.2
    • ggplot2: version 4.0.3
    • knitr: version 1.52
    • MASS: version 7.3.65
    • parallelly: version 1.48.0
    • patchwork: version 1.3.2
    • sandwich: version 3.1.3
    • sf: version 1.1.3
    • tidyr: version 1.3.2

Getting Started:
----------------------------------
1. Clone or download this repository.
2. Open ARC_RIO_FRIO.Rmd in RStudio and set `data_dir` in the Parameters section to the folder that holds the nine RData files.
3. Knit the notebook. Missing packages are installed automatically. The output is PDF, which needs a LaTeX distribution with xelatex such as TinyTeX.
4. Figures are written to the ARC_RIO_FRIO_outputs folder inside `data_dir`.

Manuscript Summary:
----------------------------------
Survey ceramics and terrace areas can show how much and in which ways residential units differed. This study analyzes 12,058 sherds and 2,526 terraces from a full-coverage survey of the Río Frío basin, Sierra Nevada de Santa Marta, Colombia, with two chance expectations, multidimensional scaling, quasibinomial models and Gini coefficients. Finishing labor on undecorated vessels increased from the Neguanje to the Tairona period. Units differed beyond sampling in every period, mostly between collection locations, and Tairona sites also differed as wholes, along finishing and firing axes, regardless of site size. Terrace area was moderately unequal but unrelated to ceramic differences.

For questions or further information, please contact: lms313@pitt.edu
