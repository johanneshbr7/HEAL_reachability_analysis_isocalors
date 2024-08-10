# HEAL Reachability Analysis with Isocalors

## Introduction

This repository contains the jupyter notebooks for conducting a reachability analysis under heat stress conditions using isocalors. The reachability analysis was performed within my master's thesis with the title "Heat stress in urban areas: heat-stress-avoiding reachability analysis using the example of Heidelberg" at the Institute of Geography at Heidelberg University. This work is integrated in the [HEAL research project](https://www.geog.uni-heidelberg.de/gis/heal.html), a collaboration between the [Heidelberg Institute for Geoinformation Technology (HeiGIT)](https://heigit.org/), the [GIScience Research Group Heidelberg](https://www.geog.uni-heidelberg.de/gis/index_en.html) and the [TdLab of the University of Heidelberg](https://www.geog.uni-heidelberg.de/institut/tdlab_en.html), which develops adaptation strategies to support vulnerable populations during heat waves.

This project investigates the effects of heat stress on the accessibility of essential services in Heidelberg. As urban heat waves become more frequent due to climate change, it is increasingly important to understand how heat impacts access to critical services, particularly for vulnerable populations.To address this challenge, the traditional concept of isochrones—commonly used to map accessibility based on travel time—is extended by incorporating heat stress factors. This innovative approach, known as isocalor analysis, is implemented using a heat-sensitive routing tool developed by the [HEAL-project](https://heal.openrouteservice.org/#/place/@8.684134483337404,49.40897673906448,12). By applying this method to the city of Heidelberg, the project provides valuable insights into how varying levels of heat stress influence access to essential health and livelihood services, offering guidance for strategies aimed at enhancing urban resilience in a warming climate.

## Usage
To use this project, follow these instructions:
- Download the Juypter Notebooks
- Download the POI Data from [geofabrik](https://www.geofabrik.de/data/)
- Download population data from [Zensus 2022](https://www.zensus2022.de/DE/Ergebnisse-des-Zensus/_inhalt.html#Gitterdaten2022)
- Download LCZ-Map for Heidelberg [here](https://lcz-genera-tor.rub.de/factsheets/42fa3c8077fb21373f4b83cb338957922f8ec58a/42fa3c8077fb21373f4b83cb338957922f8ec58a_factsheet.html)
- Perform [Get_POIs.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/Get_POIs.ipynb) notebook
- Enter HEAL-API-URL in [HEAL_Isocalors_POI.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/HEAL_Isocalors_POI.ipynb)
- Perform the second Notebook
- Perform [lcz_analysis.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/lcz_analysis.ipynb)

## Requirements
To run the notebooks, you will need the following Python packages:
- Jupyter Notebook
- OpenRouteService
- GeoPandas
- Pandas
- NumPy
- Matplotlib
- SeabornPandas
- Pyogrio
- Rasterio
- Rasterstats
- OverPy
- Shapely


## Content
1. **Get_POIs**
  The notebook [Get_POIs.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/Get_POIs.ipynb) calls POIs for kindergardens, social facilities for elderlys and trees with the [Overpass-API](https://overpass-api.de/) from OpenStreetMap and saves them to respective shapefiles.

2. **HEAL_Isocalors_POI**
  [HEAL_Isocalors_POI.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/HEAL_Isocalors_POI.ipynb) calculates via the [HEAL-API](https://heal.openrouteservice.org/#/place/@8.684134483337404,49.40897673906448,12) the isocalors for input shapefiles downloaded from [geofabrik](https://www.geofabrik.de/data/) or with [Get_POIs.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/Get_POIs.ipynb). Make sure to insert the HEAL-API-URL into the corresponding code block. In order to get the HEAL-URL contact the [HeiGIT team](https://heigit.org/de/kontakt/) or the author of this repository to get access to the HEAL-API. The HEAL-API is based on [OpenRouteService](https://openrouteservice.org/). The notebook will call the Isocalors from the HEAL-API and will perform consecoutive calculations.
The output will be stored as GeoJSON files. Afterwards two histograms and a graph from affected population by city quarter will be created.

4. **lcz_analysis**
  The [lcz_analysis.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/lcz_analysis.ipynb) performs calculations using the Local Climate Zones to analyse the isocalors created in HEAL_Isocalors_POI. It calculated the Population, Area, Population Density, Transport stop number, Transport Stop density and affected Population by Heat Factor, Heat-Minute-Equivalent and Timeofday and outputs two GeoJSON files contoining the results.
There will be created a Plot showing the Percentage of the affected population within each LCZ compared to the total population of the respective LCZ, divided by Heat Factor, Heat-Minute-Equivalent and Timeofday. A second plot shows the absolute number of affected population for heat factors 3 and 5 averaged by LCZ.


## Contributing
Contributions are welcome! Please follow these steps to contribute:
1. Fork the repository.
2. Create a new branch (git checkout -b feature/YourFeature).
3. Commit your changes (git commit -m 'Add your feature').
4. Push to the branch (git push origin feature/YourFeature).
5. Open a pull request.

## License
This project is licensed under the  GNU GENERAL PUBLIC LICENSE - see the [LICENSE](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/d32bc3c0791a80cc4a5a3fbbc9ff8477a8c7980c/LICENSE.txt) file for details.

## Contact
For any questions or feedback, please contact Johannes H. at johanneshuber1@web.de.
