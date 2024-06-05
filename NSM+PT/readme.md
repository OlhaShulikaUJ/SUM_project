# NSM+PT
## Input:
* [csv file](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/demografia_KRK.csv) with demography and address points distribution 
  
* graphml file with [city graph](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/Krakow.graphml)
* the [default](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM%2BPT/default_SUM.json) file with configurations
* csv with the [list](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM%2BPT/list_of_hubs.csv) of preselected hubs coordinates
  
* dbf file with OSM network (available e.g. [here](https://www.interline.io/osm/extracts/))
* zip with GTFS file for the area and date that we query (available e.g. from [gtfs](https://gtfs.ztp.krakow.pl/))
* both OSM and GTFS file shall be stored in data folder

## Output:
* general [results](https://github.com/anniutina/SUM/tree/main/results)
* the choise of [hubs](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM%2BPT/Hub_choice_Bronowice.ipynb) for Bronowice

## Usage:
* Utilities, Mode choice definitions in this [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM%2BPT/SUM_KRK_OD.ipynb](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM%2BPT/sum_main.ipynb)). Full version is [here](https://github.com/anniutina/SUM/tree/main)
* Comparison of the areas: Bronowice and Skotniki in this [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM%2BPT/sum_results.ipynb). Full version is [here](https://github.com/anniutina/SUM/tree/main)
* running the OTP server [notebook](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/run%20OTP%20server-KRK.ipynb)
