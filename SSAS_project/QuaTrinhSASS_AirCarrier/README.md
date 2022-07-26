# Analyze data warehouse and query data with MDX and pivot Excel.
## Processing
1. Create Analysis Services Multidimensional and Data Mining Project.
2. Create Data Source and Data Source View.
3. Create and Deploy Cube.
4. Create Calculation Named
  - Create QuaterName with example format: Q1 CY 2017 - means: quater is 1 and year is 2017.
  - Create YearName with example format: CY 2017 - means: year is 2017.
  - Create MonthName with example format: M1 Q1 CY 2017 - means: month is 1, quater is 1 and year is 2017.
  - Create CLASS_SERVICE_GROUP with conditions:
    - If class_services_id in (F,G) then class_service_group is Scheduled.
    - IF class_services_id in (L,P) then class_service_group is Non-Scheduled.
5. Create Hierarchies
  - Create DestGeography Hierarchy with level: dest country name > dest state name > dest city name > dest airport name.
  - Create DestCityMarket Hierarchy with level: dest city market name > dest airport name.
  - Create Date Hiararchy with level: Year > Quater > Month. Update Name Column of Year, Quater, Month by YearName, QuaterName, MonthName.
  - Create OriginGeography Hierarchy with level: origin country name > state name > origin city name > origin airport name.
  - Create OriginCityMarket Hierarchy with level: origin city market name > origin airport name.
  - Create Y_Q Hierarchy with level: Year > Quater. Update Name Column of Year, Quater by YearName, QuaterName.
## Query Statement
1. Statistics of total flights that Atlas Air Inc. Has the departure point been in Vietnam by month, quarter, year?
2. Find airports covered by carriers Delta Airline Inc. come the most in 2018?
3. Top 3 carriers with the most flights canceled?
4. Compare the total number of passengers transported to New York City by quarter of each year?
5. List 5 countries where the total volume of goods and mail is decreasing (Starting at 6th place) year by year?
6. Query the carrier that has flown at least 15 groups of distances and owns the fastest aircraft for each distance group?
7. For each quarter in 2019, list 3 countries with high total number of passengers?
8. Top 3 US states with the most number of city markets?
9. Find the carriers with the fastest average transit times by distance group?
10. Statistics on the total number of flights and total number of seats in each aircraft type of American Arline Inc. by quarters in 2019? Using the function DRILLDOWNLEVEL.
11. For each aircraft configuration (AirCraft_Config_Name), find the most commonly used aircraft type (AirCraft_Type_Name)?
12. List the months by year with the highest number of passengers according to Scheduled and Non-Scheduled service groups?
13. Statistics of fastest average transit time of each type of aircraft by distance group?
14. List the transportation providers that have the lowest percentage of seats in the month compared to the quarter by year with the service type being “Scheduled Passenger / Cagro Service F” (F)?
15. List the carriers with the difference between the number of flights performed and the number of scheduled flights greater than 10 per month in 2019 with Scheduled service type (F and G)?
