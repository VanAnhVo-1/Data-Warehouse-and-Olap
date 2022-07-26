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
    |Class| Service Class: F: Scheduled Passenger/ Cargo Service F;G: Scheduled All Cargo Service G
