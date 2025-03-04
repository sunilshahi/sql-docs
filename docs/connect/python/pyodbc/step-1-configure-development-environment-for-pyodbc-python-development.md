---
title: "Step 1: Configure pyodbc Python environment"
description: "Step 1 of this getting started guide involves installing Python, the Microsoft ODBC Driver for SQL Server, and pyODBC into your development environment."
ms.custom: ""
ms.date: 03/24/2022
ms.prod: sql
ms.technology: connectivity
ms.topic: conceptual
author: David-Engel
ms.author: v-davidengel
---
# Step 1: Configure development environment for pyodbc Python development

This article explains how to configure your development environment for pyodbc Python development.

## Windows

Connect to SQL Database by using Python - pyodbc on Windows:
  
1. **Download Python installer**. If your machine doesn't have Python, install it. Go to the [**Python download page**](https://www.python.org/downloads/windows/) and download the appropriate installer. For example, if you are on a 64-bit machine, download the Python 2.7 or 3.10 (x64) installer.  
  
2. **Install Python**. Once the installer is downloaded, do the following steps:

   1. Double-click the file to start the installer.
   1. Select your language, and agree to the terms.
   1. Follow the instructions on the screen to install Python on your computer.
   1. You can verify that Python is installed by going to a command prompt and running `python -V` or `py -V` (for 3.x). You can also search for Python in the start menu.

3. [**Install the Microsoft ODBC Driver for SQL Server on Windows**.](../../odbc/windows/system-requirements-installation-and-driver-files.md#installing-microsoft-odbc-driver-for-sql-server)
  
4. **Open cmd.exe as an administrator**.

5. **Install pyodbc using pip - Python package manager**. (Replace `C:\Python27\Scripts` with your installed Python path)

   ```cmd
   cd C:\Python27\Scripts  
   pip install pyodbc  
   ```

## Linux

Connect to SQL Database by using Python - pyodbc:
  
1. **Open terminal**.

2. [**Install Microsoft ODBC Driver for SQL Server on Linux**.](../../odbc/linux-mac/installing-the-microsoft-odbc-driver-for-sql-server.md)

3. **Install pyodbc**.  

   ```bash  
   sudo -H pip install pyodbc
   ```

## Next steps

[Create an SQL database for pyodbc](step-2-create-a-sql-database-for-pyodbc-python-development.md).