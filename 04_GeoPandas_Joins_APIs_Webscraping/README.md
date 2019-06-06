# GeoPandas, Joins, APIs & Webscraping

## Pending from last class
* Look at a Buzzfeed notebook, how it's documented

## References from last class
* [Python cheatsheet](https://github.com/computationaljournalism/columbia2019/blob/master/cheatsheets/Python_Cheatsheet.ipynb)
* [Datacamp Jupyter Notebook shortcuts](https://towardsdatascience.com/jypyter-notebook-shortcuts-bf0101a98330)

## Geopandas and joins
* **Installation**:
  * `conda install geopandas`
  * `conda install -c conda-forge rtree`
* Median household income downloaded from the [American Fact Finder](https://factfinder.census.gov/faces/nav/jsf/pages/index.xhtml): American Community Survey, 5-year estimates, 2017, table B19013, for New York City at the census tract level.
* New York State census tract shapefile downloaded from the [US Census Bureau](https://www.census.gov/cgi-bin/geo/shapefiles/index.php) for 2017.
* `merge` vs `join` vs `concat`
* Pandas merge [documentation](http://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.merge.html)
* Geodataframe [documentation](http://geopandas.org/data_structures.html)

## Import fwf & merge

## APIs
* Final exercise: write a function that queries Twitter's api for something and then writes the result to a csv file, and this gets updated every x minutes.

## The web
* Design your own basic site with HTML and CSS in preparation for webscraping