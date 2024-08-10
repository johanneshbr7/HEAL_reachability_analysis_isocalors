# HEAL Reachability Analysis with Isocalors

## Introduction

This repository contains the jupyter notebooks for conducting a reachability analysis under heat stress conditions using isocalors. The reachability analysis was performed within my master's thesis with the title "Heat stress in urban areas: heat-stress-avoiding reachability analysis using the example of Heidelberg" at the Institute of Geography at Heidelberg University. This work is integrated in the [HEAL research project](https://www.geog.uni-heidelberg.de/gis/heal.html), a collaboration between the [Heidelberg Institute for Geoinformation Technology (HeiGIT)](https://heigit.org/), the [GIScience Research Group Heidelberg](https://www.geog.uni-heidelberg.de/gis/index_en.html) and the [TdLab of the University of Heidelberg](https://www.geog.uni-heidelberg.de/institut/tdlab_en.html), which develops adaptation strategies to support vulnerable populations during heat waves.

This project investigates the effects of heat stress on the accessibility of essential services in Heidelberg. As urban heat waves become more frequent due to climate change, it is increasingly important to understand how heat impacts access to critical services, particularly for vulnerable populations.To address this challenge, the traditional concept of isochrones—commonly used to map accessibility based on travel time—is extended by incorporating heat stress factors. This innovative approach, known as isocalor analysis, is implemented using a heat-sensitive routing tool developed by the [HEAL-project](https://heal.openrouteservice.org/#/place/@8.684134483337404,49.40897673906448,12). By applying this method to the city of Heidelberg, the project provides valuable insights into how varying levels of heat stress influence access to essential health and livelihood services, offering guidance for strategies aimed at enhancing urban resilience in a warming climate.



The notebook [Get_POIs.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/Get_POIs.ipynb) calls POIs for kindergardens, social facilities for elderlys and trees with the [Overpass-API](https://overpass-api.de/) from OpenStreetMap and saves them to respective shapefiles.

[HEAL-Isocalors_POI.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/HEAL_Isocalors_POI.ipynb) calculates via the [HEAL-API](https://heal.openrouteservice.org/#/place/@8.684134483337404,49.40897673906448,12) the isocalors for input shapefiles downloaded from [geofabrik](https://www.geofabrik.de/data/) or with [Get_POIs.ipynb](https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors/blob/316272769e5c91b0649a0a43cacb88c97dc01348/src/Get_POIs.ipynb). Make sure to insert the HEAL-API-URL into the corresponding code block. In order to get the HEAL-URL contact the [HeiGIT team](https://heigit.org/de/kontakt/) or the author of this repository to get access to the HEAL-API.


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


## Contributing
Contributions are welcome! Please follow these steps to contribute:
1. Fork the repository.
2. Create a new branch (git checkout -b feature/YourFeature).
3. Commit your changes (git commit -m 'Add your feature').
4. Push to the branch (git push origin feature/YourFeature).
5. Open a pull request.

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Contact
For any questions or feedback, please contact Johannes H. at johanneshuber1@web.de.
