## mrio-microdata


### Subfolder Consumption_Module
Apply MRIO-model results for policy-induced sectoral price changes with country- and decile specific household expenditure data to 1. assess consumption incidence and 2. feed decile-specific demand reactions back into the model. The aim of the MRIO is to assess the short- and medium term impacts of different climate and development policy scenarios across various outcomes.

The subfolder contains:
- **base_data**: Concordance tables, HH-Survey+Elasticity data and Placeholder MINDSET results for Bulgaria: contains all necessary input data - **Not public**
- **tax_burden_scaled.py**: Contains functions to calculate and print consumption incidence based on MINDSET price changes, Mindset Household demand and HH survey expenditure shares
- **plots.R** :  functions for plots
- **dataprep.py** : functions to merge different microdatasets and to generate consumption - GLORIA concordance table 
- **test_consumption.py** : Contains unit tests for base_incidence_draft.py : to be run with `$ pytest` . If all tests pass, calculations go as expected
- **transfers.py** : Contains functions to calculate and print cons. incidence with targeted direct transfers and public infrastructure investment
- **Survey_MINDSET_check.py** : Returns xlsx for comparing Model vs HH Survey per capita consumption in each country

The subfolder **Price_and_Income_ELAS** contains the all functions necessary to integrate decile specific price and income elasticities into the main MRIO module.
- **sector_adj_factors.py**: Contains functions to calculate sectoral price adjustment factors of demand based on decile specific demand elasticities

#### Inputs
Following inputs are needed:

Data:
- **HH_Data_with_elas.xlsx** : Contains budget shares, elasticities for all available countries/deciles. generated by dataprep.py
- **GLORIA_CPAT_concordance.xlsx** : Concordance table cons. categories - CPAT sectors
- **GTAPtoGLORIA.xlsx** : Concordance table GTAP 10 sectors - GLORIA sectors
- **Results_ISO3.xlsx** : country-scenario specific MRIO output
- **HH_Elasticities.xlsx** : consumption decile specific price elasticities of demand
- **Public_Inv.csv** : csv containing other investment in infrastructure shares
- **Templates_Tax** : Model tax template
- Exchange rates, GDP deflator , population by year and country drom World Development Indicators

### Documentation

- Code Documentation: **mindsethouseholdmodule.pdf** (generated automatically with Sphinx)
- Technical Documentation: **MINDSET_HH_MODULE.pdf**


#### Requires

1. In order for imports to properly work (Necessary when calling functions in another script -until now only for pytest) in a terminal move to the root of the repository and type `$ conda develop .`

2. All data now contained in base_data (concordance_tables, HH_survey+HH_elasticities and MINDSET results) are necessary inputs.

