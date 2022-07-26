# Data Mining - Predict Health Insurance Owners' who will be interested in Vehicle Insurance.
## Introduction
- An insurance company already offering Health Insurance to its customers, now wants to build a model to forecast whether customers from the previous year would be interested in the Vehicle Insurance offered by the company or not.
- It is very useful for the company to build a model to predict whether customers are interested in Vehicle Insurance, so that the company can plan a communication strategy to reach customers and optimize your business and revenue model.
## Dataset
- Name: Health Insurance Cross Sell Prediction.
- Link: https://www.kaggle.com/anmolkumar/health-insurance-cross-sell-prediction?select=train.csv 

My partner and I user the train.csv file to mining. It contains 381109 rows and 12 columns. Property details:

|Property|Description|Data type|
| --- | --- | --- |
|id|Unique ID for the customer| integer|
|Gender|Gender of the customer and contains 2 values: Male and Female.| varchar(50)|
|Age|Age of the customer| interger|
|Driving_License| Did Customer have driving license? And contains 2 values: <br />&emsp;0 : Customer does not have DL.<br />&emsp;1 : Customer already has DL.|integer|
|Region Code| Unique code for the region of the customer| integer|
|Previously_Insured| Did Customer have vehicle insurance? And contains 2 values: <br />&emsp;1 : Customer already has Vehicle Insurance.<br />&emsp;0 : Customer doesn't have Vehicle Insurance.|integer|
|Vehicle Age| Age of the Vehicle| varchar(50)|
|Vehicle Damaged| Did customer got his/her vehicle damage in the past? Contains 2 values: <br />&emsp;1 : Customer got his/her vehicle damaged in the past.<br />&emsp;0 : Customer didn't get his/her vehicle damaged in the past.| varchar(50)|
|Annual_Premium| The amount customer needs to pay as premium in the year.| interger|
|PolicySalesChannel|Anonymized Code for the channel of outreaching to the customer ie. Different Agents, Over Mail, Over Phone, In Person, etc.|integer|
|Vintage|Number of Days, Customer has been associated with the company.|interger|
|Response|Reponse of Customer. Contains 2 values:<br />&emsp;1 : Customer is interested,<br />&emsp;0 : Customer is not interested.|integer|
## Processing
### Import data from .csv file to database in SQL Server.
Using SQL Server Integration Services (SSIS) to import SQL Server database with 3 steps:
- Create connection to train.csv file and import data to database.
- Derived Column: Convert data from text to conformtable data type.
- Connection to Health Insurance Database in SQL Server by OLE DB Connection manager. Create table contain properties with conformtable data type. Mapping data.
![image](https://user-images.githubusercontent.com/72924182/180952810-9b41fa2c-995c-42b1-a4da-f4491b9940bd.png)
### Mining 
- Create Analysis Server Project --> Create Data Source and Data Source Views --> Create Mining Structures with Decision Tree Model, Clustering, Naive Bayes --> Deploy Project.
## Result 
1. Model Predict Health Insurance Owners' who will be interested in Vehicle Insurance with Decision Tree Algorithm.
  With Decision Tree Algorithm have:
    - 46590 customer are interested in vehicle insurance, 12.26%.
    - 333519 customer are interested in vehicle insurance, 87.74%.
![image](https://user-images.githubusercontent.com/72924182/180953724-956567bf-4955-4401-9a86-59f2d33e7628.png)
  - The degree of dependence of the attributes in increasing direction: Vintage --> Driving_License --> Region Code --> Gender --> Vehicle_Age --> Policy_Sales_Channel --> Vehicle_Damaged --> Age --> Previous_Insured.
  ![image](https://user-images.githubusercontent.com/72924182/180954698-1452f6a9-aa92-4659-a405-5a4142c5ce29.png)
2. Model Predict Health Insurance Owners' who will be interested in Vehicle Insurance with Naive Bayes Algorithm.
  With Naive Bayes Algorithm has:
    - With case customer is interested in vehicle insurance:
      - Has driving license with 99.9%.
      - Male is majority.
      - Hasn't vehicle insurance with 99.7%.
      - Region code 28 is majority.
      - Vehicle age is 1-2 years.
      - Damaged in the past with 97.9%
    - With case customer isn't interested in vehicle insurance:
      - Has driving license with 99.8%.
      - Male is majority.
      - Has vehicle insurance with 52.2%.
      - Region code 28 is majority.
      - Vehicle age is 1-2 years.
      - Damaged in the past with 43.9%
![image](https://user-images.githubusercontent.com/72924182/180956785-6c77a9c4-1129-4777-9be9-8804e57f2f73.png)
3. Mining Accuracy Chart
  - Decision Tree Algorithm accuracy is 86%.
  - Clustering Algorithm accuracy is 80%.
  - Naive Bayes accuracy is 82%.
![image](https://user-images.githubusercontent.com/72924182/180956923-054b04ab-da42-41a9-83b6-b2e438b66eea.png)


