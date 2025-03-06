# Roadmap

## 6 Steps of Data Analysis
We will base this project around the 6 general steps of data analysis, using these to guide and develop the project.
1. Ask
2. Prepare
3. Process
4. Analyze
5. Share
6. Act

## Ask
We want to answer the following questions by analyzing nuclear and fossil fuel energy production, fuel consumption, and waste creation data from the United States of America:
1. What are the historical trends between each type of energy source and how does their energy production, fuel consumption, and waste production compare?
2. Is nuclear energy a cleaner, more effective source of energy when comparing the amount of fuel consumed and waste produced to the energy output?
3. Would increasing the amount of nuclear energy produced help reduce greenhouse gas emissions from fossil fuels and how would the amount of nuclear waste compare?

## Prepare
We have collected data on energy production, fuel consumption, and waste creation in the U.S. from the U.S. Energy Information Administration [website](www.eia.gov) and the Pacific Northwest National Labs [website](https://www.pnnl.gov). The detailed breakdown is as follows:
- Monthly Energy Review: [source](https://www.eia.gov/totalenergy/data/monthly/)
    - Variable start year through 2023
    - Table 7.2b: Electricity Net Generation – Electric Power Sector
    - Table 7.4b: Consumption of Combustible Fuels for Electricity Generation and Useful Thermal Output – Electric Power Sector
    - Table 8.2: Uranium Overview
    - Table 11.6: Carbon Dioxide Emissions from Energy Consumption – Electric Power Sector
- Uranium waste: [source](https://gc859.pnnl.gov/summary/table2)
    - 1968-2022
    - Number of discharged assemblies
    - Metric tons of initial heavy metal of discharged assemblies
    - Average burnup of discharged assemblies
    - Average initial enrichment of discharged assemblies
    - Cumulative total number of discharged assemblies
    - Cumulative total metric tons of initial heavy metal of discharged assemblies

### Collected Data Discussion

The monthly energy review data includes several tables provided by the EIA that focuses on the electricity sector in the United States of America. Table 7.2b contains data on electricity production by different source such as coal, natural gas, nuclear, etc. collected from 1949-2023. Table 7.4b covers the amount of combustible fuels used to generate the electricity given in Table 7.2b from 1949-2023. Table 8.2 includes data on reactor grade uranium consumption from 1949-2023. Table 11.6 covers the amount of Carbon Dioxide emitted from the burning of fuels to generate electricity from 1973-2023. The range of years each field contains data in varies, so a smaller subset of years will be investigated to ensure all fields contain data. 

The uranium waste dataset includes the amount of nuclear waste removed from nuclear power plants annually from 1968-2023. We will use these values to compare with the amount of CO2 produced by burning fuels to get a value like electricity generated per amount of waste produced. We will focus on the metric tons of initial heavy metal of discharged assemblies average burnup of discharged assemblies data fields since these relate to the amount of waste produced per year.

## Process
The changelog for our data cleaning and processing can be found under [Data_Processing_Changelog.pdf](Data_Processing_Changelog.pdf). We largely standardized the units between each sheet to be in SI, typically being kilowatthours of electricity generated or metric tons of a substance consumed/produced, and standardized the formats of each sheet to easily compare data from different sheets using the year the data is from along with their column names. Cells that reported data as "not available' or "withheld" were all replaced with empty cells rather than zero to clarify where data was missing and where data was zero.

We are somewhat limited with the uranium consumption data, as the earliest available data is from 1991, while the other data dates back to the 1960s or earlier. We will utalize as much of the data as we can and point out where data does and does not exist in our analysis. 

## Analyze
WIP

## Share
WIP

## Act
WIP
