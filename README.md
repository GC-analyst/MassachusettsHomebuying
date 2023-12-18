# MassachusettsHomebuying
A project that seeks to identify the best location for new homebuyers, based on municipalities having a median home value &lt; $400,000, median family income &lt; $100,000 and 75% home-ownership.
## Analyses include
 - geo-spatial analysis
 - correlation matrix
 - scatterplots
 - regression
 - clustering
 - time series analysis and decomposition
Data Source
https://www.kaggle.com/datasets/ikalats/massachusetts-house-pricing/

# Summary

The data is sourced from several places:
 - Average Fair Market Rent Prices information was scraped from https://www.rentdata.org/states/massachusetts/ from 2006 to 2022.
 - Annual Estimates of the Resident Population: April 1, 2010 to July 1, 2019. U.S. Census Bureau Population Division. May 21, 2020. The data is available for 351 towns in MA. 
 - Home prices in MA were scraped from Boston Magazine web portal: https://www.bostonmagazine.com/property/single-family-home-price-chart-2021/.
 - Boston neighborhood and town median home prices, sales volumes, and days on market provided by the Massachusetts Association of Realtors (marealtor.com) and MLS Property Information Network (mlspin.com).
 - The income per household per town was retrieved from https://en.wikipedia.org/wiki/List_of_Massachusetts_locations_by_per_capita_income.

Data is owned by several distinct entities:
 - Rentdata.org, US. Census Bureau, marealtor.com/mlspin.com
 - Rentdata and realtor/spin data appears to be external, and the US Census Bureau is internal.

Rentdata.org is not very transparent about its collection method, but pricing appears to be consistent with other price sites.
US Census and realtor data is internal, and high trustworthiness.

Rent/realtor data appears to have been scraped from price sites directly. Scraping could be considered survey data, as is the US Census data, but pricing could also be administrative.

Columns include: Time, Year, Value, Type, County, Population.
Derivable columns include: % Homeownership, Per Capita Income, # Households, Median Household Income, Median Family Income.

This data is ideal for my business question: What is the most affordable area for new home buyers?
Limitations of the data lie in its timeliness. Income data was from 2019. However, the data still qualifies as recent.

# Business Questions:

This data was chosen to answer the question: Where is the best place to purchase a first time home in Massachusetts?
The area needs to be
1) affordable, defined as median home price <$400,000, AND median family income <=$100,000.
2) in a residential area, defined as being 75% home-owned
   
Data was improperly stored, so cleaned (in Excel) by:
 - Separating sheets into key information
 - VLOOKUP to merge key columns into the MASTER sheet
 - Replacing N/A values with blanks so that counts and averages were more accurate
 - Identifying blank/improper names and rectifying
 - Data typing each column
 - Deriving new columns for key metrics, easier pivot tables
 - Renaming municipalities that had been improperly split into two words after 2015 (ex. Province Town - Provincetown)

Data Cleaning in Jupyter:
 - I ran basic info, shape, head, describe checks for the dataset.
 - I looked for missing values in a key column ‘2019 Median Family Income’, then identified the towns for which that data was missing.
 - I deleted all rows with the town names with missing values in that column.

Data limitations and ethics
 - Data is limited by its collection date, as important values such as Median Family Income are from 2019. Some data is missing, but can be reasonably excluded. Also, an important value is distance from the major metropolitan city of Boston, which is difficult to impute, though this can be done after the other analyses, to simplify the process.
