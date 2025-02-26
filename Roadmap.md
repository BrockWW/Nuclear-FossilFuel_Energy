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
We have collected data on energy production, fuel consumption, and waste creation in the U.S. from the U.S. Energy Information Administration [website](www.eia.gov). The detailed breakdown is as follows:
  -	Energy production by type: [webpage](https://www.eia.gov/international/data/country/USA/electricity/more-electricity-data?pd=2&p=00000020000000000000070000000e000000000000000000000000000000000u&u=1&f=A&v=mapbubble&a=-&i=none&vo=value&t=C&g=none&l=249--238&s=315532800000&e=1672531200000&ev=false)
    -	1980-2023
    -	Generation
      -	Generation (Total)
      -	Nuclear
      -	Coal
      -	Natural gas
      -	Oil
      -	Other gases
    -	Energy consumption (Total)
    -	Energy capacity
      -	Capacity (Total)
      -	Nuclear
      -	Fossil fuels
  -	Fossil fuel emissions: [webpage](https://www.eia.gov/international/data/world/other-statistics/emissions-by-fuel?pd=40&p=0000000000000000000000000000000000000000000000000000000b0001&u=0&f=A&v=mapbubble&a=-&i=none&vo=value&t=C&g=none&l=249--238&s=-662688000000&e=1640995200000&)
    -	1949-2022
    -	CO2 emissions
      -	CO2 emissions (Total)
      -	Coal and coke
      -	Consumed natural gas
      -	Petroleum and other liquids
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
  -	Uranium waste: [webpage](https://www.eia.gov/nuclear/spent_fuel/ussnftab3.php)
    -	1968-2017
    -	Online table copied
  -	State electricity profiles full data table: [webpage](https://www.eia.gov/electricity/state/unitedstates/state_tables.php)
    -	1990-2023
    -	Provides a lot of information that was downloaded separately together with a difference in values to those downloaded above
      -	Some differences may be a difference in reporting source or the fact that some of the sheets in this table are estimated values for the year
Included are links to the webpage with the correct filters applied to each dataset. We also provide the selected filters below each energy type to clarify the content of the data collected. Next, we will dicsuss our choices for how each dataset how filtered and collected, explain how we intend to use each dataset, and discuss some discrepancies that may lead to a difference in results based on the constraints of how data can be selected on the EIA website.

### Collected Data Discussion
The first data collected is for the U.S. annual energy generation per source, the total amount of energy produced and consumed annually, and the energy capacity for nuclear and fossil fuel sources from 1980-2023. We ignore any renewable energy sources such as wind, solar, etc. to focus our analysis on just nuclear and fossil fuels. We will use the annual energy generation per source to track the change in energy production over time and see the percentage breakdown of total produced energy. We will also pair the amount of energy generated with the amount of fuel consumed or waste produced to get a rough efficiency rating for each type of energy source.

The second dataset contains fossil fuel CO2 emissions annually from 1949-2022 which we will use as a "waste" parameter to compare with the nuclear waste data. We acknowledge that there may be additional waste associated with the usage of fossil fuels in producing energy but will focus on CO2 emissions as this is the most widely known and significant waste from burning fossil fuels.

The third dataset is coal production, consumption, imports, and exports for bituminous, subbituminous, and lignite coal types from 1980-2023. We focus on these three types of coal as they are often used for electricity generation rather than primarily for industrial use. We include the amount of coal imported and exported for the possibility of comparing fuel source trading in the U.S.

The fourth data collected is for the amount of dry natural gas produced, consumed, imported, and exported from 1980-2023. The dry natural gas values reported are used for domestic household and business use as well as electricity generation, so we will reference the final dataset we collected to better estimate the amount of natural gas used purely for energy production.

The fifth dataset we collected includes general information on active U.S. nuclear power plants from 1957-2023, the most important of which is the net nuclear energy generation and percentage of total energy produced by nuclear power. We will pair this data with the first dataset to get a more complete view of electricity produced from nuclear power.

The sixth dataset is for uranium production, imports, exports, and amount loaded into nuclear reactors from 1949-2023 which will be used to compare with the fossil fuel consumption data.

The seventh dataset is the amount of nuclear waste removed from nuclear power plants annually from 1968-2017. We will use these values to compare with the amount of CO2 produced by burning fossil fuels to get a value like electricity generated per amount of waste produced. The available dataset is lacking more recent years that all other datasets include, so we have reached out to the EIA to request access to more recent data if publicly available.

The final dataset is a full spreadsheet of the electricity industry in the U.S., including values like those we have collected. Comparing the data available through their website search function to this spreadsheet, there is a difference in values between the same data, but these differences are largely under an order of magnitude in difference, and at first glance may be within a factor of 2~3. Because of this, we will try to exclusively use the individual data downloaded via the data search function and only use this additional spreadsheet as a reference when the other data we collected is incomplete or encompasses a wider scope of energy production than only electricity production.

## Process
WIP

## Analyze
WIP

## Share
WIP

## Act
WIP
