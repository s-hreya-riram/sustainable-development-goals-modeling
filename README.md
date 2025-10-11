## Problem Statement

Does economic development yield differential returns for child health outcomes across income levels? Specifically, do low-income, middle-income, and high-income countries experience different magnitudes of under-5 mortality reduction for each unit increase in GDP per capita? 

## Hypothesis

H₀ (Null): The relationship between GDP per capita and under-5 mortality is uniform across all development levels. Economic development yields consistent child health returns regardless of a country's income classification. 
H₁ (Alternate): The relationship between GDP per capita and under-5 mortality differs significantly across income levels. Low-income countries experience stronger mortality reductions per unit GDP increase compared to middle-income and high-income countries, reflecting different stages of epidemiological transition and healthcare system development. 

## SDGs Addressed

SDG 3 (Good Health and Well-being): Target 3.2 - End preventable deaths of children under 5 
SDG 8 (Decent Work and Economic Growth): Examining economic development's health impacts 
SDG 10 (Reduced Inequalities): Analyzing differential returns across income levels 


### Datasets

* Under-5 mortality (response variable): https://ourworldindata.org/grapher/child-mortality
* GDP per capita (input variable): https://data.worldbank.org/indicator/NY.GDP.PCAP.PP.KD
* Income Classification (input variable): https://databank.worldbank.org/data/download/site-content/OGHIST.xls
* Health expenditure (input variable): https://data.worldbank.org/indicator/SH.XPD.CHEX.GD.ZS
* DPT3 immunization (input variable): https://data.worldbank.org/indicator/SH.IMM.IDPT
* Population density (input variable): https://data.worldbank.org/indicator/EN.POP.DNST
* Access to safely managed drinking water services (input variable) : https://data.worldbank.org/indicator/SH.H2O.SMDW.ZS

## Why did we choose this problem statement?

Child mortality is a key measure of development and health system effectiveness, targeted by SDG 3.2. While wealthier countries generally have lower child mortality rates (the Preston Curve), we want to understand whether the strength of this relationship varies by development level. In low-income countries, additional income can fund basic, high-impact interventions like vaccines, clean water, and nutrition programs. In contrast, high-income countries have already addressed these preventable causes of death, so further economic growth yields smaller health gains. By testing this hypothesis across ~65 countries, we can provide evidence on the factors that could contribute the best for achieving SDG 3.2 targets in different development contexts.

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
   source ./venv/bin/activate  # Windows folks: venv\Scripts\activate
   ```

3. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

4. Run individual Jupyter notebooks as needed. 
Start with raw_data_restructuring.ipynb, 
then merging_all_datasets.ipynb and then
exploratory_data_analysis.ipynb

## How This Project is Organized

```
data/
├── raw/                # The original data files (straight from the source)
├── processed/          # Clean, processed data ready for modeling
jupyter_notebook        # Notebooks for cleaning and preparing the data
```