# HEAL Reachability Analysis Isocalors

## Introduction
This repository contains the code and resources for conducting reachability analysis using isocalors. Reachability analysis is a method used to compute the set of states that a dynamical system can reach, starting from a set of initial states under given constraints. This project aims to provide tools and methods to perform such analysis efficiently.

## Features
- **Reachability Analysis**: Compute reachable sets for various types of systems.
- **Isocalors Visualization**: Visualize the reachable sets using isocalors.
- **Support for Continuous and Hybrid Systems**: Applicable to both continuous and hybrid dynamical systems.

## Installation
To set up the project locally, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/johanneshbr7/HEAL_reachability_analysis_isocalors.git

Navigate to the project directory:
bash
cd HEAL_reachability_analysis_isocalors

Install the required dependencies:
bash
pip install -r requirements.txt

Usage
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