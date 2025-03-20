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

The monthly energy review data includes several tables provided by the EIA that focuses on the electricity sector in the United States of America. Table 7.2b contains data on electricity production by different sources such as coal, natural gas, nuclear, etc. collected from 1949-2023. Table 7.4b covers the amount of combustible fuels used to generate the electricity given in Table 7.2b from 1949-2023. Table 8.2 includes data on uranium loaded into U.S. reactors from 1949-2023 and will be used as a tracer of the amount of fuel consumed. Table 11.6 covers the amount of carbon dioxide emitted from the burning of fuels to generate electricity from 1973-2023. The range of years each field contains data varies, so a smaller subset of years will be investigated to ensure all fields contain data.

The uranium waste dataset includes the amount of nuclear waste removed from nuclear power plants annually from 1968-2023. We will use these values to compare with the amount of CO2 produced by burning fuels to get a value like electricity generated per amount of waste produced. We will focus on the metric tons of initial heavy metal of discharged assemblies average burnup of discharged assemblies data fields since these relate to the amount of waste produced per year.

The exact fields we will use in our analysis as named in the original tables are as follows:
- Table 7.2b
    - Electricity Net Generation From Coal, Electric Power Sector
    - Electricity Net Generation From Petroleum, Electric Power Sector
    - Electricity Net Generation From Natural Gas, Electric Power Sector
    - Electricity Net Generation From Nuclear Electric Power, Electric Power Sector
    - Electricity Net Generation Total (including from sources not shown), Electric Power Sector
- Table 7.4b
    - Coal Consumption for Electricity Generation and Useful Thermal Output, Electric Power Sector
    - Distillate Fuel Oil Consumption for Electricity Generation and Useful Thermal Output, Electric Power Sector
    - Residual Fuel Oil Consumption for Electricity Generation and Useful Thermal Output, Electric Power Sector
    - Other Petroleum Liquids Consumption for Electricity Generation and Useful Thermal Output, Electric Power Sector
    - Petroleum Coke Consumption for Electricity Generation and Useful Thermal Output, Electric Power Sector
    - Natural Gas Consumption for Electricity Generation and Useful Thermal Output, Electric Power Sector
- Table 8.2
    - Loaded into U.S. Nuclear Reactors
- Table 11.6
    - Coal Electric Power Sector CO2 Emissions
    - Natural Gas Electric Power Sector CO2 Emissions
    - Petroleum Electric Power Sector CO2 Emissions
    - Total Energy Electric Power Sector CO2 Emissions
- PNNL Uranium Waste
    - Total Metric tons of initial heavy metal (MTiHM) of discharged assemblies
 
We leave out any renewable sources as well as some smaller combustible fuel sources such as wood and other waste since renewable energy is outside the scope of this project and the other combustible fuels make up a small minority of the total electricity generation and CO2 emitted. From Table 7.4b, we take each type of petroleum rather than the total petroleum consumed field so we can convert each component to metric ton first, then add them together to get a more accurate conversion between barrels and metric tons. For CO2 emissions in Table 11.6, we take the total amount of CO2 produced from all petroleum sources since no conversion was needed.

## Process
The changelog for our data cleaning and processing can be found under [Data_Processing_Changelog.pdf](Data_Processing_Changelog.pdf). We largely standardized the units between each sheet to be in SI, typically being kilowatthours of electricity generated or metric tons of a substance consumed/produced, and standardized the formats of each sheet to easily compare data from different sheets using the year the data is from along with their column names. Cells that reported data as "not available' or "withheld" were all replaced with #N/A values rather than zero to clarify where data was missing and where data was reported as zero.

We are somewhat limited with the uranium consumption data, as the earliest available data is from 1991, while the other data dates back to the 1960s or earlier. We will utilize as much of the data as we can and point out where data does and does not exist in our analysis.

The unit breakdown and any non-SI conversions completed for the data are listed below:
- **Original Units -> New Units**
- Million Kilowatthours -> Kilowatthours
    - Used for all electricity generation values
- Thousand Short Tons -> Metric Tons
    - 1 Short Ton = 0.9071847 Metric Tons
    - Used for both coal and petroleum coke fuel consumption values
- Thousand Barrels -> Metric Tons
    - 1 Barrel Distillate/Residual Fuel Oil = 0.157 Metric Tons
    - 1 Barrel Other Petroleum Liquids = 0.1052 Metric Tons
        - Approximate conversion is found by averaging the conversion from barrels to approximate metric tons of ethane (0.059), liquified petroleum gas (0.086), gasoline (0.120), kerosene (0.127), and gas oil/diesel (0.134)
- Billion Cubic Feet -> Metric Tons (Oil Equivalent)
    - 1 Billion Cubic Feet = 0.024 Million Metric Tons (Oil Equivalent)
    - Used for natural gas fuel consumption
- Million Metric Tons -> Metric Tons
    - Used for all CO2 emission values
- Million Pounds Uranium Oxide -> Metric Tons Uranium
    - 1 Pound Uranium Oxide = 0.384647 Kilograms Uranium
    - 1 Metric Ton = 1000 Kilograms
    - Used for all uranium consumption values

## Analyze
To streamline the analysis process we combined the fossil fuel fuel consumption data with the uranium consumption data and stretched the dates to go from 1949 to 2023, inserting a #N/A value when a year was missing data from any field. Similarly, we combined the fossil fuel CO2 and nuclear waste produced data and again stretched the dates to go from 1949 to 2023. Combining the data allows us to create plots and calculate new fields that all span from 1949 to 2023, where any missing data is not shown in plots and is given as a #N/A if any value in the calculations are missing.

Starting with the base data, we looked at trends in electricity generated per year by source, fuel consumed per year per source, and waste produced per year by source for coal, natural gas, petroleum, and nuclear sources.

We calculated several new fields that look at the relationships between electricity production, fuel consumption, and waste production which we list below with their units:
- Kilowatt hours of electricity generated per metric ton of fuel consumed
    - Electricity Generated to Coal Consumed (kWh/t)
    - Electricity Generated to Petroleum Consumed (kWh/t)
    - Electricity Generated to Natural Gas Consumed (kWh/t)
    - Electricity Generated to Uranium Consumed (kWh/t)
- Metric ton of CO2 produced per metric ton of fuel consumed
    - CO2 Produced to Coal Consumed (%)
    - CO2 Produced to Petroleum Consumed (%)
    - CO2 Produced to Natural Gas Consumed (%)
    - Nuclear Waste Produced to Uranium Consumed (%)
- Kilowatt hours of electricity generated per metric ton of waste produced
    - Electricity Generated from Coal to CO2 Produced (kWh/t)
    - Electricity Generated from Petroleum to CO2 Produced (kWh/t)
    - Electricity Generated from Natural Gas to CO2 Produced (kWh/t)
    - Electricity Generated from Uranium to Waste Produced (kWh/t)
- Percentage of total electricity generated
    - Percent of Total Generated Electricity from Coal (%)
    - Percent of Total Generated Electricity from Petroleum (%)
    - Percent of Total Generated Electricity from Natural Gas (%)
    - Percent of Total Generated Electricity from Nuclear (%)
    - Total Amount of Electricity Accounted For (%)

We also test what would happen to fuel consumption and waste production if we increased the amount of electricity generated from nuclear power and decreased the amount of electricity generated from coal, petroleum, and natural gas. We increased the historical amount of electricity from nuclear power generated per year by 10%, 25%, 50%, and 100%, then subtracted the additional power in equal parts to each other source. Doing this allowed us to keep the percentage of total electricity produced per year by the combined coal, petroleum, natural gas, and nuclear sources the same when adjusting the amount of nuclear power produced. We did this to not interfere with any other electricity generating sources that we do not investigate, such as renewables. From each of the changes to nuclear power produced, we create a plot of electricity generated per year by source, fuel consumed per year per source, and waste produced per year by source using the calculated relationships between electricity generated, fuel consumed, and waste produced from the original data.

## Share
We arranged our findings according to each of the three main questions we set out to answer. Our findings will be collected into a short presentation.

To answer our first question, we will look at the historical data we collected and the trends of coal, petroleum, natural gas, and nuclear and their net electricity generation per year, percentage of total electricity generation per year, total amount of fuel consumed per year, and total amount of waste produced per year.

To answer our second question, we will use the created fields that measure for each source the net electricity generated per metric ton of fuel consumed, the net electricity generated per metric ton of waste produced, and the ratio of metric ton of waste produced to metric ton of fuel used.

To answer our last question, we will compare the estimated net electricity generation, fuel consumption, and waste production calculated by historically increasing the amount of electricity from nuclear by 10% and 25%. We will not discuss the 50% and 100% increase in nuclear power because they are unreasonable goals to achieve in the immediate future and would need to be built off of an initial small increase in nuclear power.

We created a report in the form of a power point that includes our main findings and the figures that support them.

## Act
In our report we advocated for the use of nuclear energy and pointed the reader to additional readings published by the World Nuclear Association that explains nuclear energy in the U.S. in more detail.
