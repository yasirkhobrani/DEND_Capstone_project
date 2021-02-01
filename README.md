# DEND_Capstone_project
This capstone project goal is to create an ETL pipeline that combines I94 immagrating data, city temperature data and demographics data into FACT table(star schema is applied because it is a simple model), that is optimized for queries to analyze immigration events. These optimized data will then be used to answer questions regarding immigration behavior based on location temperatures and population capacity.
##### Star Schema chosen because it makes queries simpler and easier to perform through the fact table.
**Fact Table - This will contain information from the I94 immigration data joined with the city temperature data and demographic data on i94port**

Columns:

* i94yr = 4 digit year
* i94mon = numeric month
* i94cit = 3 digit code of origin city
* i94port = 3 character code of destination city
* arrdate = arrival date
* i94mode = 1 digit travel code
* depdate = departure date
* i94visa = reason for immigration
* AverageTemperature = average temperature of destination city

**1st Dimension Table - This will contain events from the I94 immigration data.**

Columns:

* i94yr = 4 digit year
* i94mon = numeric month
* i94cit = 3 digit code of origin city
* i94port = 3 character code of destination city
* arrdate = arrival date
* i94mode = 1 digit travel code
* depdate = departure date
* i94visa = reason for immigration

**2nd Dimension Table - This will contain city temperature data.**

Columns:

* i94port = 3 character code of destination city (mapped from cleaned up immigration data)
* AverageTemperature = average temperature
* City = city name
* Country = country name
* Latitude= latitude
* Longitude = longitude

**3rd Dimension Table - This will contain demographics data.**

Columns:

* i94port = 3 character code of destination city (mapped from cleaned up immigration data)
* Total Population = number of total city populaiton.
* City = city name
