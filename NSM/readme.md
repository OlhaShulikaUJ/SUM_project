# NSM (on-demand pooled transit feeder service)
## Input:

* graphml file with [city graph](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/Krakow.graphml)
* the [default](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM/default_SUM.json) file with configurations
* [csv file](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/PT/data/demografia_KRK_example.csv) with demography and address points distribution 
* [shp file](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM/Obszary_SUM.shp) with a set of candidate areas
* csv file with the [list] of preselected hubs coordinates
* dbf file with OSM network (available e.g. [here](https://www.interline.io/osm/extracts/))
* OSM file shall be stored in data folder

## Output:
* [results](https://github.com/OlhaShulikaUJ/SUM_project/blob/main/NSM/area%203-Skotniki.ipynb) the feeder service performance assessment for Area 3 with two hubs
