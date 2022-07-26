# Data Warehouse and Olap
This is project for Data Warehouse and Olap object in my university.
## Introduction
Air transport is an important enabler to achieving economic growth and development so My partner and I learned about American air carriers in 2019.


The dataset is reported by US airlines, including information such as: airline name, point of origin, destination, aircraft type and class of service, freight and mails, number of seats, scheduled departure flights, flights taken, number of flight hours, distance,... between two airports.

The dataset lists direct flights between two airports. This means including the case with a scheduled flight from airport A to airport C, if this flight has to make an emergency landing at an airport B, the dataset only record the information of that flight from airport A to airport B, but not information from airport A to airport C.
## Dataset
- Dataset Name: T-100 International Segment (US Carriers Only)
- Latest Update: 12/2020
- Original: The Bureau of Transportation Statistics - United States Department of Transportation.
- The dataset include 42 columns and range from 2017 to 2019:
  - 2017: 51733 rows.
  - 2018: 51222 rows.
  - 2019: 50394 rows.
- Link: https://www.transtats.bts.gov/DL_SelectFields.asp?gnoyr_VQ=GDK
- Detailed description of dataset properties:

    |Property|Description|
    | --- | --- |
    |DepScheduled|Departures Scheduled.|
    |DepPerformed| Departures Performed.|
    |Payload|Available Payload.|
    |Seats| Available Seats.|
    |Passengers| Non-Stop Segment Passengers Transported.|
    |Freight| Non-Stop Segment Freight Transported.|
    |Mail| Non-Stop Segment Mail Transported.|
    |Distance| Distance between airports|
    |AirTime| Airborne Time|
    |DistanceGroup|Distance group is every 500 Miles for a distance group.|
    |Class| Service Class:<br />&emsp;F: Scheduled Passenger/ Cargo Service F<br />&emsp;G: Scheduled All Cargo Service G<br />&emsp;L: Non-Scheduled Civilian Passenger/ Cargo Service L<br />&emsp;P: Non-Scheduled Civilian All Cargo Service P|
    |UniqueCarrier| Unique Carrier Code.|
    |AirlineID| An identification number assigned by US DOT to identify a unique airline (carrier).|
    |UniqueCarrierName|Unique Carrier Name.|
    |CarrierRegion| Carrier's Operation Region. Carriers Report Data by Operation Region<br />&emsp;A: Atlantic<br />&emsp;D: Domestic<br />&emsp;I: International<br />&emsp;L: Latin America<br />&emsp;P: Pacific|
    |CarrierGroup|Carrier Group Code. Used in Legacy Analysis|
    |OriginAirportSeqID|Origin Airport, Airport Sequence ID. An identification number assigned by US DOT to identify a unique airport at a given point of time. Airport attributes, such as airport name or coordinates, may change over time.|
    |OriginCityMarketID| Origin Airport, City Market ID. City Market ID is an identification number assigned by US DOT to identify a city market. Use this field to consolidate airports serving the same city market.|
    |Origin|Origin Airport|
    |OriginCityName| Origin City|
    |OriginCountry| 	Origin Airport, Country|
    |OriginCountryName|	Origin Airport, Country Name|
    |OriginWac| Origin Airport, World Area Code|
    |DestAirportSeqID| Destination Airport, Airport Sequence ID. An identification number assigned by US DOT to identify a unique airport at a given point of time.| 
    |DestCityMarketID| Destination Airport, City Market ID. City Market ID is an identification number assigned by US DOT to identify a city market. Use this field to consolidate airports serving the same city market.|
    |Dest| Destination Airport.|
    |DestCityName| Destination City.|
    |DestCountry| Destination Airport, Country.|
    |DestCountryName| Destination Airport, Country Name.| 
    |DestWac| Destination Airport, World Area Code.|
    |AircraftGroup| Aircraft Group.|
    |AircraftType| Aircraft Type.|
    |AircraftConfig| Aircraft Configuration.|
    |Year| Year.|
    |Quarter|	Quarter	Analysis.|
    |Month| Month.|
## Processing
### 1. Modeling data
Create a Snowflake schema.
![image](https://user-images.githubusercontent.com/72924182/180922025-12b8e198-a4d8-4974-9c95-e9cabda9bbae.png)
### 2. Create data warehouse
Using SQL Server Integration Services (SSIS) with 5 steps:
- Step 1: Preprocessing
- Step 2: Create ORIGIN_CITY_MARKET table.
- Step 3: Create and load data to dimensions.
- Step 4: Create and load data to facts.
- Step 5: Create foreign keys.
![image](https://user-images.githubusercontent.com/72924182/180925285-ea85b9e0-82f3-4fa0-9702-42cbdc446108.png)
### 3. Analyze data using MDX Query
- Create new project SASS
- Defined Data Source and Data Source View.
- Create and deploy Cube.
- Create Calculation Named and Hierchies.
- Execute Query statements
### 4. Report
Create report with Microsoft Reporting Services Projects and Power BI.
### 5. Data Mining 
Use the Health Insurance Cross Sell Prediction to predict.
    

