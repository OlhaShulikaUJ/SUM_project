# Demand distribution
## Input:
* graphml file with [city graph](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/Krakow.graphml)
* [geojson file](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/krk.geojson) with geometries of Krakow's areas
* [geojson file](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/krk_centroid.geojson) with centroid locations of Krakow's areas
* [shp file](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/Obszary_SUM.shp) with geometries of preselected areas
* [csv file](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/demografia_KRK.csv) with demography and address points distribution 
* [xlsx](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/Krakow_model_OD_matrices.xlsx) file with destinations probabilities according to ODM

## Output:
* csv with requests (origin, destination, time request, etc.) [georequests_OD.csv](https://github.com/OlhaShulikaUJ/SUM_project/tree/main/PT/georequests)

## Usage:
* demand distribution in this [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/demand_distribution.ipynb)

# Public Transport queries
## Input:
* csv  with requests [georequests_OD.csv](https://github.com/OlhaShulikaUJ/SUM_project/tree/main/PT/georequests)
* dbf file with OSM network (available e.g. [here](https://www.interline.io/osm/extracts/))
* zip with GTFS file for the area and date that we query (available e.g. from [gtfs](https://gtfs.ztp.krakow.pl/))
* both OSM and GTFS file shall be stored in data folder

## Output:
* csv with trip details (time, transfers, modes, wait and walk times, etc.) [georequests_OD_PT.csv](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/georequests/georequests_O(area10)_D_PT.csv)

## Usage:
* single trips and visualization in this tutorial [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/tutorial-KRK.ipynb)
* running the OTP server [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/run%20OTP%20server-KRK.ipynb)
