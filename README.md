
# HEAL Reachability Analysis with Isocalors

## Introduction

This repository contains the Jupyter notebooks for conducting a reachability analysis under heat stress conditions using isocalors. The reachability analysis was performed as part of my master's thesis titled "Heat stress in urban areas: heat-stress-avoiding reachability analysis using the example of Heidelberg" at the Institute of Geography at Heidelberg University. This work is integrated into the [HEAL research project](https://www.geog.uni-heidelberg.de/gis/heal.html), a collaboration between the [Heidelberg Institute for Geoinformation Technology (HeiGIT)](https://heigit.org/), the [GIScience Research Group Heidelberg](https://www.geog.uni-heidelberg.de/gis/index_en.html), and the [TdLab of the University of Heidelberg](https://www.geog.uni-heidelberg.de/institut/tdlab_en.html), which develops adaptation strategies to support vulnerable populations during heat waves.

This project investigates the effects of heat stress on the accessibility of essential services in Heidelberg. As urban heat waves become more frequent due to climate change, it is increasingly important to understand how heat impacts access to critical services, particularly for vulnerable populations. To address this challenge, the traditional concept of isochrones—commonly used to map accessibility based on travel time—is extended by incorporating heat stress factors. This innovative approach, known as isocalor analysis, is implemented using a heat-sensitive routing tool developed by the [HEAL project](https://heal.openrouteservice.org/#/place/@8.684134483337404,49.40897673906448,12). By applying this method to the city of Heidelberg, the project provides valuable insights into how varying levels of heat stress influence access to essential health and livelihood services, offering guidance for strategies aimed at enhancing urban resilience in a warming climate.

![Affected population under heat stress conditions at noon (13:00 CEST+2) with heat factor 5 and a heat-minute equivalent of 15.](./img/vul_pop_hf5_noon_hmeq15_v2.png)

The project consists of three main steps:
1. **Data Collection:** The first step involves collecting data on essential services, such as kindergartens, social facilities for the elderly, and trees, as well as population data and Local Climate Zones (LCZs) for Heidelberg.

2. **Isocalor Analysis:** The second step calculates isocalors for the essential services using the HEAL-API, which provides heat-sensitive routing based on OpenRouteService. The analysis considers different heat factors, heat-minute equivalents, and times of day to assess the impact of heat stress on accessibility.

3. **LCZ Analysis:** The third step uses Local Climate Zones (LCZs) to analyze the isocalors and assess the affected population by heat factor, heat-minute equivalent, and time of day. The analysis provides insights into the distribution of heat stress across different urban zones and highlights areas with high vulnerability to heat waves.



## Usage

To use this project, follow these instructions:
- Download the Jupyter Notebooks.
- Download the POI data from [Geofabrik](https://www.geofabrik.de/data/).
- Download population data from [Zensus 2022](https://www.zensus2022.de/DE/Ergebnisse-des-Zensus/_inhalt.html#Gitterdaten2022).
- Download the LCZ map for Heidelberg [here](https://lcz-generator.rub.de/factsheets/42fa3c8077fb21373f4b83cb338957922f8ec58a/42fa3c8077fb21373f4b83cb338957922f8ec58a_factsheet.html).
- Run the [Get_POIs.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/Get_POIs.ipynb) notebook.
- Enter the HEAL-API URL in [HEAL_Isocalors_POI.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/HEAL_Isocalors_POI.ipynb).
- Run the second notebook.
- Run [lcz_analysis.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/lcz_analysis.ipynb).

## Requirements

To run the notebooks, the following Python packages are required:
- Jupyter Notebook
- OpenRouteService
- GeoPandas
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Pyogrio
- Rasterio
- Rasterstats
- OverPy
- Shapely

## Content

1. **Get_POIs:**  
   The notebook [Get_POIs.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/Get_POIs.ipynb) retrieves POIs for kindergartens, social facilities for the elderly, and trees using the [Overpass-API](https://overpass-api.de/) from OpenStreetMap and saves them to respective shapefiles.

2. **HEAL_Isocalors_POI:**  
   [HEAL_Isocalors_POI.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/HEAL_Isocalors_POI.ipynb) calculates isocalors for input shapefiles downloaded from [Geofabrik](https://www.geofabrik.de/data/) or with [Get_POIs.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/Get_POIs.ipynb) via the [HEAL-API](https://heal.openrouteservice.org/#/place/@8.684134483337404,49.40897673906448,12). Ensure the HEAL-API URL is inserted into the corresponding code block. To obtain the HEAL URL, contact the [HeiGIT team](https://heigit.org/de/kontakt/) or the author of this repository. The HEAL-API is based on [OpenRouteService](https://openrouteservice.org/). The notebook will call the Isocalors from the HEAL-API and perform subsequent calculations. The output will be stored as GeoJSON files. Two histograms and a graph showing the affected population by city quarter will be created.

3. **lcz_analysis:**  
   The [lcz_analysis.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/lcz_analysis.ipynb) performs calculations using Local Climate Zones (LCZs) to analyze the isocalors created in HEAL_Isocalors_POI. It calculates population, area, population density, transport stop number, transport stop density, and affected population by heat factor, heat-minute-equivalent, and time of day, and outputs two GeoJSON files containing the results. A plot is generated showing the percentage of the affected population within each LCZ compared to the total population of the respective LCZ, divided by heat factor, heat-minute-equivalent, and time of day. A second plot shows the absolute number of affected population for heat factors 3 and 5, averaged by LCZ.

## Contributing

Contributions are welcome! Please follow these steps to contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Commit your changes (`git commit -m 'Add your feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a pull request.

## References 

Foshag, Kathrin/Fürle, Johannes/Ludwig, Christina/Fallmann, Joachim/Lautenbach, Sven/Rupp, Saskia/Burst, Patrick/Betsch, Marco/Zipf, Alexander/Aeschbach, Nicole (2024). How to as-sess the needs of vulnerable population groups towards heat-sensitive routing? ERD-KUNDE, 1–33. [https://doi.org/10.3112/erdkunde.2024.01.01](https://doi.org/10.3112/erdkunde.2024.01.01).

Mack, Sarah (2023). WUDAPT Level 0 training data for Heidelberg (Germany, Federal Republic of). submitted to the LCZ Generator. Accessable at [https://lcz-genera-tor.rub.de/factsheets/42fa3c8077fb21373f4b83cb338957922f8ec58a/42fa3c8077fb21373f4b83cb338957922f8ec58a_factsheet.html](https://lcz-genera-tor.rub.de/factsheets/42fa3c8077fb21373f4b83cb338957922f8ec58a/42fa3c8077fb21373f4b83cb338957922f8ec58a_factsheet.html) (last access 19.07.2024).

Neis, Pascal/Zipf, Alexander (2008). Openrouteservice.org is three times “open”: Combining OpenSource, OpenLS and OpenStreetMaps Manchester, GIS Research UK (GISRUK 08), 2008. [https://openrouteservice.org/](https://openrouteservice.org/).

## License

This project is licensed under the GNU GENERAL PUBLIC LICENSE - see the [LICENSE](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/d32bc3c0791a80cc4a5a3fbbc9ff8477a8c7980c/LICENSE.txt) file for details.

## Contact
For any questions or feedback, please contact Johannes H. at johanneshuber1@web.de.