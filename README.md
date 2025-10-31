# Economic Development and Under-5 Mortality Analysis
**Author**: Shreya Sriram

## Problem Statement

Child mortality is a key measure of development and health system effectiveness, as targeted by SDG
3.2 [United Nations, 2015]. While wealthier countries generally have lower child mortality rates [Swift,
2018], we want to understand whether the strength of this relationship varies by development level.
In low-income countries, additional income can fund basic high-impact interventions such as vaccines,
clean water, and nutrition programs. In contrast, high-income countries have already addressed these
preventable causes of death, so further economic growth yields smaller health gains. By testing this
hypothesis in 80 countries, we seek to provide evidence on the factors that could contribute the best to
achieving the SDG 3.2 targets in different development contexts.

## Hypothesis

H₀ (Null): The relationship between GDP per capita and under-5 mortality is uniform across all development levels.Economic development yields consistent child health returns regardless of a country's income classification. 

H₁ (Alternate): Low-income countries experience significantly larger reductions in under-5 mortality per unit increase in GDP per capita compared to high-income countries (β ≠ 0), reflecting differential returns to economic development across income levels.

## SDGs Addressed

SDG 3 (Good Health and Well-being): Target 3.2 - End preventable deaths of children under 5 

SDG 8 (Decent Work and Economic Growth): Examining economic development's health impacts 

SDG 10 (Reduced Inequalities): Analyzing differential returns across income levels 


### Datasets

* Under-5 mortality (response variable): https://ourworldindata.org/grapher/child-mortality
* GDP per capita (input variable): https://data.worldbank.org/indicator/NY.GDP.PCAP.PP.KD
* Income Classification (input variable): https://ourworldindata.org/grapher/world-bank-income-groups
* Health expenditure (input variable): https://data.worldbank.org/indicator/SH.XPD.CHEX.GD.ZS
* DPT3 immunization (input variable): https://data.worldbank.org/indicator/SH.IMM.IDPT
* Population density (input variable): https://data.worldbank.org/indicator/EN.POP.DNST
* Access to safely managed drinking water services (input variable) : https://data.worldbank.org/indicator/SH.H2O.SMDW.ZS


## Technical Implementation

### Data Pipeline
- Data collection and restructuring from 7 different sources
- Merging strategy for panel data (80 countries, 2000-2021)
- Missing data imputation using time series and central tendency methods

### Statistical Analysis
- Custom transformation pipeline:
  - Log transformations for right-skewed variables (GDP, population density, mortality)
  - Box-Cox transformation for target normalization
  - Reflect-and-transform for left-skewed variables
  - Logit transformation for percentage variables
- Implementation of three regression approaches:
  - Pooled OLS with clustered standard errors
  - Simple Random Effects model
  - Random Effects model using Mundlak's approach (the best model)

### Visualization & Diagnostics
- Distribution analysis and transformation validation
- Income group comparisons
- Regression diagnostics (Q-Q plots, residual analysis)
- Model comparison visualizations

### Documentation
- Comprehensive Jupyter notebooks with step-by-step explanations
- Reproducible research workflow
- Detailed comments and markdown explanations

## Getting Started

### What You'll Need

- Python 3.10 or higher

### Setup Instructions

1. Clone the repository :
   ```bash
   git clone https://github.com/s-hreya-riram/sustainable-development-goals-modeling.git
   ```

2. Set up your Python environment:
   ```bash
   python -m venv venv
   source ./venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

4. Run individual Jupyter notebooks as needed. 
Start with raw_data_restructuring.ipynb, then merging_all_datasets.ipynb, then exploratory_data_analysis.ipynb and finally modeling.ipynb

## How This Project is Organized
```
data/
├── raw/                            # Original data files from sources
├── processed/                      # Cleaned data ready to be merged
├── modeling/                       # Data ready for modeling
jupyter_notebooks/                  # Complete analysis pipeline
├── raw_data_restructuring.ipynb    # Standardize format across 7 datasets
├── merging_all_datasets.ipynb      # Merge into unified panel dataset
├── exploratory_data_analysis.ipynb # Data cleaning, transformations, encoding
├── modeling.ipynb                  # Pooled OLS → Random Effects → Mundlak models
```

**Notebook Execution Order**: 
1. `raw_data_restructuring.ipynb` - Prepare individual datasets in a standardized format
2. `merging_all_datasets.ipynb` - Create unified panel data
3. `exploratory_data_analysis.ipynb` - Clean and transform variables
4. `modeling.ipynb` - Run models and diagnostics

## Citation

If you use this analysis or code, please cite:
```
Shreya Sriram (2025). Economic Development and Under-5 Mortality Analysis. 
GitHub repository: https://github.com/s-hreya-riram/sustainable-development-goals-modeling
```

Note: The figure 'Countries by Income Classification.jpg' under data/report_figures referenced in the pdf of the report was created by Chen Ke Yuan Kowin using the dataset in Excel and refined in QGIS and is not part of the Git repository