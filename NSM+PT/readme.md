# NSM+PT
## Input:
* csv with requests [georequests_OD.csv](https://github.com/OlhaShulikaUJ/SUM_project/tree/main/PT/georequests)
  
* graphml file with [city graph](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/Krakow.graphml)
* the [default](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM%2BPT/default_SUM.json) file with configurations
* csv with the [list](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM%2BPT/list_of_hubs.csv) of preselected hubs coordinates
  
* dbf file with OSM network (available e.g. [here](https://www.interline.io/osm/extracts/))
* zip with GTFS file for the area and date that we query (available e.g. from [gtfs](https://gtfs.ztp.krakow.pl/))
* both OSM and GTFS file shall be stored in data folder

## Output:
* csv with KPIs for SUM users [KPI.csv]

## Usage:
* Utilities, Mode choice, Demand_NSM definitions in this [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM%2BPT/SUM_KRK_OD.ipynb)
* running the OTP server [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/run%20OTP%20server-KRK.ipynb)
