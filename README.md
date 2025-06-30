# Replication Package for "The Impact of Minimum Wage Increases on Employment and Income Distribution in Spain: Evidence from Administrative Census Data"

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![DOI](https://img.shields.io/badge/DOI-Pending-blue.svg)]()

This repository contains the full replication code and public data for the paper, "The Impact of Minimum Wage Increases on Employment and Income Distribution in Spain: Evidence from Administrative Census Data" by Marcos Lacasa-Cazcarra.

## Abstract

This paper evaluates the employment and distributional effects of Spain's 22% minimum wage increase in 2019, using administrative data on all formal-sector workers. Our difference-in-differences analysis reveals that while aggregate employment remained resilient, the reform caused a persistent 14% decline in youth employment relative to its counterfactual trajectory. This large negative effect, masked by aggregate statistics, proves descriptive claims of a "recovery" are misleading.

Furthermore, the reform had perverse distributional consequences. Counterfactual simulations show it paradoxically worsened inequality, raising the Gini coefficient by 0.20% as employment losses among the poorest youth dominated the wage gains of incumbent workers. Our results show how a confluence of a large hike, extreme labor market dualism, and high pre-existing vulnerability created a severe employment barrier. This case demonstrates that in segmented markets, aggressive, uniform wage hikes can deepen the inequality they intend to fix.

## Main Findings

1.  **Youth Employment Collapse:** Spain's 2019 minimum wage increase caused a **14% decline** in youth employment (ages 16-24), an effect completely hidden in aggregate employment figures.
2.  **Increased Inequality:** The reform paradoxically **increased the Gini coefficient by 0.20%**. Job losses for the poorest workers at the bottom of the distribution outweighed the wage gains for those who remained employed.
3.  **Methodological Importance:** Descriptive analyses are shown to be fundamentally misleading. Rigorous causal inference methods are essential to uncover the true effects of the policy.

## Repository Structure

```
.
├── code/
│   ├── 01_data_cleaning.py         # Scripts for cleaning public and confidential data
│   ├── 02_did_analysis.py          # Main Difference-in-Differences estimations
│   ├── 03_heterogeneity.py         # Heterogeneity analysis (sector, region, etc.)
│   ├── 04_inequality_simulation.py # Counterfactual inequality analysis
│   └── 05_generate_figures_tables.py # Scripts to generate all outputs
├── data/
│   └── (This folder is for placing the confidential data once obtained)
├── output/
│   ├── figures/                  # All figures from the paper and appendix
│   └── tables/                   # All tables in LaTeX format
├── paper/
│   ├── main_submission.tex       # Anonymous manuscript for submission
│   └── supplementary_appendix.tex  # Online Appendix
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt              # List of Python dependencies
```

## Data Availability

This study uses two types of data:

1.  **Public Data:** Macroeconomic time series from the Spanish National Institute of Statistics (INE), Eurostat, and the World Bank. The scripts in the `/code` directory can download and process this data automatically.
2.  **Confidential Data:** The core of this analysis relies on confidential administrative tax records from the **Spanish Tax Agency (Agencia Tributaria)**. Due to strict legal and privacy regulations, these data cannot be shared publicly.
    * **Access for Researchers:** Qualified researchers can request access to these data for replication purposes by following the formal application process directly with the Spanish Tax Agency. More information can be found on their official website (search for "cesión de información tributaria con fines de investigación científica").
    * The confidential data files, once obtained, should be placed in the `/data/` directory for the replication scripts to work correctly.

## Replication Instructions

To replicate the results of this study, follow these steps:

**1. Clone the Repository:**
```bash
git clone [https://github.com/mlacasa/spain-minimum-wage-2019-analysis.git](https://github.com/mlacasa/spain-minimum-wage-2019-analysis.git)
cd spain-minimum-wage-2019-analysis
```

**2. Set Up a Python Environment:**
It is highly recommended to use a virtual environment.
```bash
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

**3. Install Dependencies:**
Install all required Python libraries using the `requirements.txt` file.
```bash
pip install -r requirements.txt
```

**4. Data Acquisition:**
* Run the provided script to download all public data.
* Obtain the confidential administrative data via the official application process with the Spanish Tax Agency and place it in the `/data/` folder.

**5. Run Analysis Scripts:**
Execute the Python scripts in the `/code` directory in sequential order. A master script can be run, or they can be run individually.
```bash
python code/01_data_cleaning.py
python code/02_did_analysis.py
# ... and so on for the rest of the scripts.
```

The final outputs (figures and tables) will be saved in the `/output/` directory.

## Software Requirements

* Python 3.9+
* Key libraries are listed in `requirements.txt`. They include:
    * `pandas` (>= 1.5.3)
    * `statsmodels` (>= 0.13.5)
    * `scikit-learn` (>= 1.2.1)
    * `matplotlib` (>= 3.6.2)
    * `seaborn` (>= 0.12.2)

## Citation

If you use the findings or code from this study, please cite the original paper:

**Chicago Style:**
> Lacasa-Cazcarra, Marcos. [Year]. "The Impact of Minimum Wage Increases on Employment and Income Distribution in Spain: Evidence from Administrative Census Data." *[Journal Name, once published]* [Volume]([Issue]): [Pages].

**BibTeX:**
```bibtex
@article{LacasaCazcarra[Year],
  title   = {The Impact of Minimum Wage Increases on Employment and Income Distribution in Spain: Evidence from Administrative Census Data},
  author  = {Lacasa-Cazcarra, Marcos},
  year    = {[Year]},
  journal = {[Journal Name, once published]},
  volume  = {[Volume]},
  number  = {[Issue]},
  pages   = {[Pages]}
}
```

## Contact

For any questions regarding the code or the analysis, please contact Marcos Lacasa-Cazcarra at `marcos.lacasa@unir.net`.
