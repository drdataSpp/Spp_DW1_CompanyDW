# Data Warehouse - SSIS - Company Expenses and Profits
*This repository has the code that was used to Extract the data from a CSV file into MS SQL Server Database using SSIS.*

## Project Description
A company has stored all its expenses and profits in a .csv file. The company wants to store all the .csv file data in a Microsoft SQL Server database. This project uses Microsoft SQL Server Integration Services to extract the data from the .csv file and stores it into the SQL Server database.

## How this project was done?
1. In the excel file, all the column's data was checked and corrected.
2. Created a new database and a table in Microsoft SSMS using the following code:
``` 
  DROP DATABASE IF EXISTS [CompanyExpProfits];
  CREATE DATABASE [CompanyExpProfits];

  USE [CompanyExpProfits];

  CREATE TABLE Expenses_Profits(
  [R&D] MONEY NOT NULL,
  [ADMINISTRATION] MONEY NOT NULL, 
  [ADVERTISING] MONEY NOT NULL, 
  [CITY] VARCHAR(100) NOT NULL, 
  [PROFIT] MONEY NOT NULL 
  ); 
```
3. A new SSIS project was created in Visual Studio 2019.
4. A Data Flow Module was used to create the following pipeline:

<img src="https://github.com/drdataSpp/Spp_DW1_CompanyDW/blob/master/Screenshots/Data%20Flow.PNG" width="700" height="400" />

5. In the above image, the Flat File source has the .csv file and the OLE DB destination has the table that was created in step 2.

## Data Pipeline Execution Results

<img src="https://github.com/drdataSpp/Spp_DW1_CompanyDW/blob/master/Screenshots/DataPipeline-Execution.PNG" width="700" height="300" />

[**LINK TO SSIS Project**](https://github.com/drdataSpp/Spp_DW1_CompanyDW/tree/master/CompanyExpensesProfit)

## Output

#### Excel Data
<img src="https://github.com/drdataSpp/Spp_DW1_CompanyDW/blob/master/Screenshots/CSV%20Data.PNG" width="700" height="300" />

#### Empty Database
<img src="https://github.com/drdataSpp/Spp_DW1_CompanyDW/blob/master/Screenshots/Empty%20Data.PNG" width="700" height="400" />

#### Database after running the pipepline
<img src="https://github.com/drdataSpp/Spp_DW1_CompanyDW/blob/master/Screenshots/Filled%20Data.PNG" width="700" height="400" />


## Tools Used

[Microsoft SQL Server Management Studio](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15)

[Microsoft SQL Server Integration Services](https://docs.microsoft.com/en-us/sql/integration-services/sql-server-integration-services?view=sql-server-ver15)

[Visual Studio 2019](https://visualstudio.microsoft.com/vs/)

[Microsoft Excel](https://www.microsoft.com/en-us/microsoft-365/excel)

