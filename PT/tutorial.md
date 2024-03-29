# Public Transport queries
## Input:
* csv file with requests [georequests.csv](https://github.com/OlhaShulikaUJ/SUM_project/tree/main/PT/demand_area)
* dbf file with OSM network (available e.g. [here](https://www.interline.io/osm/extracts/)
* zip with GTFS file for the area and date that we query (available e.g. from [gtfs](https://gtfs.ztp.krakow.pl/))
* both OSM and GTFS file shall be stored in data folder

## Output:
* csv with trip details (time, transfers, modes, wait and walk times, etc.) georequests_PT.csv

## Usage:
* single trips and visualization in this tutorial [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/tutorial-KRK.ipynb)
* running the OTP server [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/run%20OTP%20server-KRK.ipynb)

# Demand distribution
## Input:
* [city graph.graphml](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/Krakow.graphml))
* [geojson file](https://www.interline.io/osm/extracts/) with geometries of Krakow's areas (https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/krk.geojson)
* [geojson file](https://www.interline.io/osm/extracts/) with centroid locations of Krakow's areas (https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/krk_centroid.geojson)
* [shp file](https://www.interline.io/osm/extracts/) with geometries of preselected areas (https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/Obszary_SUM.shp))
* [csv file](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/demografia_KRK.csv) with demography and address points distribution 
* [xlsx](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/Krakow_model_OD_matrices.xlsx) file with destinations probabilities according to ODM

## Output:
* csv with requests details (origin, destination, time request, etc.) [demand_OD_area.csv](https://github.com/OlhaShulikaUJ/SUM_project/tree/main/PT/demand_area)

## Usage:
* demand distribution in this [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/demand_distribution.ipynb)
