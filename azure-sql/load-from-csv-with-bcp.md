---
title: Load data from CSV file into a database (bcp)
description: For a small data size, uses bcp to import data into Azure SQL Database.
services: sql-database
ms.service: sql-database
ms.subservice: data-movement
ms.custom: sqldbrb=1
ms.devlang:
ms.topic: how-to
author: dzsquared
ms.author: drskwier
ms.reviewer: mathoma, kendralittle
ms.date: 01/25/2019
monikerRange: "=azuresql||=azuresql-db||=azuresql-mi"
---
# Load data from CSV into Azure SQL Database or SQL Managed Instance (flat files)
[!INCLUDE[appliesto-sqldb-sqlmi](includes/appliesto-sqldb-sqlmi.md)]

You can use the bcp command-line utility to import data from a CSV file into Azure SQL Database or Azure SQL Managed Instance.

## Before you begin

### Prerequisites

To complete the steps in this article, you need:

* A database in Azure SQL Database
* The bcp command-line utility installed
* The sqlcmd command-line utility installed

You can download the bcp and sqlcmd utilities from the [Microsoft sqlcmd Documentation](/sql/tools/sqlcmd-utility?view=sql-server-ver15&preserve-view=true).

### Data in ASCII or UTF-16 format

If you are trying this tutorial with your own data, your data needs to use the ASCII or UTF-16 encoding since bcp does not support UTF-8.

## 1. Create a destination table

Define a table in SQL Database as the destination table. The columns in the table must correspond to the data in each row of your data file.

To create a table, open a command prompt and use sqlcmd.exe to run the following command:

```cmd
sqlcmd.exe -S <server name> -d <database name> -U <username> -P <password> -I -Q "
    CREATE TABLE DimDate2
    (
        DateId INT NOT NULL,
        CalendarQuarter TINYINT NOT NULL,
        FiscalQuarter TINYINT NOT NULL
    )
    ;
"
```

## 2. Create a source data file

Open Notepad and copy the following lines of data into a new text file and then save this file to your local temp directory, C:\Temp\DimDate2.txt. This data is in ASCII format.

```txt
20150301,1,3
20150501,2,4
20151001,4,2
20150201,1,3
20151201,4,2
20150801,3,1
20150601,2,4
20151101,4,2
20150401,2,4
20150701,3,1
20150901,3,1
20150101,1,3
```

(Optional) To export your own data from a SQL Server database, open a command prompt and run the following command. Replace TableName, ServerName, DatabaseName, Username, and Password with your own information.

```cmd
bcp <TableName> out C:\Temp\DimDate2_export.txt -S <ServerName> -d <DatabaseName> -U <Username> -P <Password> -q -c -t ","
```

## 3. Load the data

To load the data, open a command prompt and run the following command, replacing the values for Server Name, Database name, Username, and Password with your own information.

```cmd
bcp DimDate2 in C:\Temp\DimDate2.txt -S <ServerName> -d <DatabaseName> -U <Username> -P <password> -q -c -t ","
```

Use this command to verify the data was loaded properly

```cmd
sqlcmd.exe -S <server name> -d <database name> -U <username> -P <password> -I -Q "SELECT * FROM DimDate2 ORDER BY 1;"
```

The results should look like this:

| DateId | CalendarQuarter | FiscalQuarter |
| --- | --- | --- |
| 20150101 |1 |3 |
| 20150201 |1 |3 |
| 20150301 |1 |3 |
| 20150401 |2 |4 |
| 20150501 |2 |4 |
| 20150601 |2 |4 |
| 20150701 |3 |1 |
| 20150801 |3 |1 |
| 20150801 |3 |1 |
| 20151001 |4 |2 |
| 20151101 |4 |2 |
| 20151201 |4 |2 |

## Next steps

To migrate a SQL Server database, see [SQL Server database migration](database/migrate-to-database-from-sql-server.md).

<!--MSDN references-->
[bcp]: /sql/tools/bcp-utility
[CREATE TABLE syntax]: /sql/t-sql/statements/create-table-azure-sql-data-warehouse

<!--Other Web references-->
[Microsoft Download Center]: https://www.microsoft.com/download/details.aspx?id=36433
