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
-	State electricity profiles data: [webpage](https://www.eia.gov/electricity/state/unitedstates/state_tables.php)
    -	1990-2023
    -	Sheet 5: Generation
    -	Sheet 7: Emissions
    -	Additional unused sheets
  -	Coal data: [webpage](https://www.eia.gov/international/data/world/natural-gas/more-natural-gas-data?pd=1&p=1g0000000000000000000000000000000000009j3e&u=1&f=A&v=mapbubble&a=-&i=none&vo=value&t=C&g=none&l=249--238&s=315532800000&e=1672531200000&ev=false&)
    -	1980-2023
    -	Production
        -	Bituminous
        -	Subbituminous
        -	Lignite
    -	Consumption
        -	Bituminous
        -	Subbituminous
        -	Lignite
    -	Imports
        -	Bituminous
        -	Subbituminous
        -	Lignite
    -	Exports
        -	Bituminous
        -	Subbituminous
        -	Lignite
  -	Natural gas data: [webpage](https://www.eia.gov/international/data/world/natural-gas/more-natural-gas-data?pd=3002&p=00g0000g0000100001&u=1&f=A&v=mapbubble&a=-&i=none&vo=value&t=C&g=none&l=249--238&s=315532800000&e=1672531200000&ev=false&)
    -	1980-2023
    -	Production
        -	Dry natural gas
    -	Consumption
        -	Dry natural gas
    -	Imports
        -	Dry natural gas
    -	Exports
        -	Dry natural gas
  -	Petroleum: [webpage](https://www.eia.gov/international/data/world/natural-gas/more-natural-gas-data?pd=5&p=00000000006000000000000000000000002&u=1&f=A&v=mapbubble&a=-&i=none&vo=value&t=C&g=none&l=249--238&s=94694400000&e=1672531200000&ev=false&)
    -	1973-2023
    -	Production
        -	Crude oil including lease condensate
    - Consumption
        - Distillate fuel oil
        - Residual fuel oil
  -	Nuclear plant data: [webpage](https://www.eia.gov/totalenergy/data/browser/index.php?tbl=T08.01#/?f=A)
    -	1957-2023
    -	Total operable unites
    -	Net summer capacity of operable units
    -	Nuclear electricity net generation
    -	Nuclear share of electricity net generation
    -	Capacity factor
  -	Uranium consumption: [webpage](https://www.eia.gov/totalenergy/data/browser/index.php?tbl=T08.02#/?f=M&start=200001)
    -	1949-2023
    -	Domestic concentrate production
    -	Purchased imports
    -	Export sales
    -	Electric plant purchases from domestic suppliers
    -	Loaded into US nuclear reactors
    -	Inventories
        -	Domestic suppliers inventories
        -	Electric plans inventories
        -	Total inventories
    -	Average price
        -	Average price of purchased imports
  -	Uranium waste: [source](https://gc859.pnnl.gov/summary/table2)
    -	1968-2022
    -	Number of discharged assemblies
    -	Metric tons of initial heavy metal of discharged assemblies
    -	Average burnup of discharged assemblies
    -	Average initial enrichment of discharged assemblies
    -	Cumulative total number of discharged assemblies
    -	Cumulative total metric tons of initial heavy metal of discharged assemblies

Included are links to the webpage with the correct filters applied to each dataset. We also provide the selected filters below each energy type to clarify the content of the data collected. Next, we will dicsuss our choices for how each dataset how filtered and collected, explain how we intend to use each dataset.

### Collected Data Discussion

The state electricity profiles dataset includes electricity generation and fossil fuel emissions data from 1990-2023. The generation data includes values for nuclear, coal, natural gas, petroleum, other, along with a total value that inclued renewable sources that we will not focus on. We will also be using CO2 emissions per energy source as a measure of waste from generating electricty from fossil fuels. This dataset does not include amounts of fuel consumed, so most of the other datasets we collected will be for measuring this. The full spreadsheet contains many additional sheets that contains additional information we will not use in our analysis.

The coal dataset includes production, consumption, imports, and exports for bituminous, subbituminous, and lignite coal types from 1980-2023. We focus on these three types of coal as they are often used for electricity generation rather than primarily for industrial use. We include the amount of coal imported and exported for the possibility of comparing fuel source trading in the U.S.

The natrual gas dataset includes the amount of dry natural gas produced, consumed, imported, and exported from 1980-2023. Dry natural gas was the only natural gas type available from the EIA website, so we will use these values as the true amount used to produce electricity, but note that some is also used for household and industrial use.

The petroleum dataset includes the amount of processed oil used to generate electricity, and the amount of crude oil produced annually from 1980-2021. This data focuses only on fuel oil that is largely used to generate electricity at power plants and corrsponds to the fuel used to produce power listed under the "petroleum" field of the state electricity profiles dataset.

The nuclear plant dataset includes general information on active U.S. nuclear power plants from 1957-2023, the most important of which is the net nuclear energy generation and percentage of total energy produced by nuclear power. We will pair this data with the first dataset to get a more complete view of electricity produced from nuclear power.

The uranium consumption dataset includes amounts of uranium production, imports, exports, and uranium loaded into nuclear reactors from 1949-2023 which will be used to compare with the fossil fuel consumption data.

The uranium waste dataset includes the amount of nuclear waste removed from nuclear power plants annually from 1968-2023. We will use these values to compare with the amount of CO2 produced by burning fossil fuels to get a value like electricity generated per amount of waste produced. We will focus on the metric tons of initial heavy metal of discharged assemblies average burnup of discharged assemblies data fields since these relate to the amount of waste produced per year.

## Process
To begin, we will combine each dataset into one table using Excel and group the data by year.

## Analyze
WIP

## Share
WIP

## Act
WIP
