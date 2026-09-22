# NEET in Italy, 2010–2020

A Shiny app for looking at the share of young people not in employment, education or
training across Italian regions. Built in March 2023, during my MA at Bergamo.

Live: http://rsamei.shinyapps.io/neet

You pick a year, a region, a gender and an age class, and get a table, a bar chart, a
line chart over the whole period, and a choropleth of Italy. The map and the charts are
driven by the same filters, so you can follow one region through the decade or compare
regions in a single year.

## Data

The NEET indicator comes from ISTAT (the `ITTER107` / `TIPO_DATO_FOL` / `SEXISTAT1`
coding is theirs). Quarterly rows are dropped and only annual figures are kept. Region
names are mapped onto the GADM 3.6 Italy boundaries before the join — ISTAT writes
Puglia, Sicilia and the two bilingual names differently from GADM, so those four are
recoded by hand in `global.R`.

Neither `neet.csv` nor the `gadm36_ITA_shp/` shapefile is in this repository, so a clone
will not run as it stands. Both are free downloads from dati.istat.it and gadm.org.

## Files

- `global.R` — loads and cleans the data, harmonises region names, reads the shapefile
- `ui.R` — layout and the four input controls
- `server.R` — filtering and the four outputs

R, Shiny, tidyverse, rgdal, latticeExtra.
