# CRU-Tools-Climate-grided-historical-time-series
Climat Researche Unit (CRU) product grided datasets for climate time series from 1901 to the year before present - monthly &amp; annual  - Precipitations - Temperatures: average, min, max - Relative humidity at surface

## CRU Climate historical MONTHLY & ANNUAL timeserie - Reading, maping, interannual average, timeserie extraction & Excel export
- data Climate-Change-Knowledge-Portal/WorldBank (netCDF) : https://climateknowledgeportal.worldbank.org/netcdf-browser (format covered in this notebook, beacause easier access and  reading than original CRU plateform)
- Data CRU: https://www.uea.ac.uk/groups-and-centres/climatic-research-unit/data  (format not covered in this notebook)
- Author: loicduffar

This notebook can manage with monthly and annual timeseries:
- Map of an area of interest for a choosen parameter, and temporal resolution. 
    -  for a month or an year
    - Climatology of a periode choosen by the user. If you want the annual climatology, choose annual timeserie as input (This notebook does not comptute the raster of the annual climatoly from monthly timeserie)
- Extraction of timeserie (annual or monthly) for a point choosen by the user. NB: Annual timeserie is also generate from monthly file)
- Timeseries are saved in a excel file

Temporal representation : 
- timeserie: from 1901 to the year before present
- Not covered in this notebook:
    - climatology by decades from 1901 
    - heatplot_mean (not covered in this notebook): monthly anomalies for various 10-year periods, relative to the monthly average over the historical recent period (1995-2014)

Temporal scale: from 1901 to the year before present
- monthly & annual  
- Not covered in this notebook : seasonal 

Parameters: 
- Precipitations
- Temperatures: average, min, max
- Relative humidity at surface

Advantage of this download plateforme (Source CRU, but downloaded from Climate Change Knowledge Portal)
- Time serie (monthly or annual) is in a unique netCDF file for all the globe
- netCDF file is well formated to be regonize as a geographical and time serie raster --> Reading with xarray is straightforward (only xr.open_datset() wittout format correction and spatial definition)

Inconvenience:
- 50 km grid only
- Data duplicated for 2 values of "bnds" 0 & 1 (????). For the moment we only keep one copy (bnds=0) because the two are strictly identical in the cases studied .... While waiting to understand the difference

unknowns to be clarified:
- 2 versions of annual time series (regular and smooth). To  be clarified
- parameter "heatspot" to be clarified
