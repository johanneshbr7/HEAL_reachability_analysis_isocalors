# HEAL Reachability Analysis with Isocalors

## Introduction
This repository contains the jupyter notebooks for conducting a reachability analysis under heat stress conditions using isocalors. The reachability analysis was performed within my master's thesis with the title "Heat stress in urban areas: heat-stress-avoiding reachability analysis using the example of Heidelberg" at the Institute of Geography at Heidelberg University. This work is integrated in the [HEAL research project](https://www.geog.uni-heidelberg.de/gis/heal.html), a collaboration between the [Heidelberg Institute for Geoinformation Technology (HeiGIT)](https://heigit.org/), the [GIScience Research Group Heidelberg](https://www.geog.uni-heidelberg.de/gis/index_en.html) and the [TdLab of the University of Heidelberg](https://www.geog.uni-heidelberg.de/institut/tdlab_en.html), which develops adaptation strategies to support vulnerable populations during heat waves.

## Installation
To set up the project locally, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors.git'''

2. **Navigate to the project directory:**
'''bash
cd HEAL_reachability_analysis_isocalors'''

3. **Install the required dependencies:**
After cloning the repository you should creat an environment containing the needed packages.

## Usage
To use this project, follow these instructions:
Run the main script:
bash
python main.py

This will perform the reachability analysis and generate the isocalors visualization.
Configuration:
Modify the config.json file to set different parameters for the analysis.
Examples
Here are some examples of how to use the project:
Basic Reachability Analysis:
bash
python main.py --config configs/basic_config.json

This example runs the reachability analysis with the basic configuration.
Advanced Analysis:
bash
python main.py --config configs/advanced_config.json

This example runs the analysis with advanced settings, providing more detailed results.
Contributing
Contributions are welcome! Please follow these steps to contribute:
Fork the repository.
Create a new branch (git checkout -b feature/YourFeature).
Commit your changes (git commit -m 'Add your feature').
Push to the branch (git push origin feature/YourFeature).
Open a pull request.
License
This project is licensed under the MIT License - see the LICENSE file for details.
Contact
For any questions or feedback, please contact Johannes H. at johanneshbr7@example.com.
