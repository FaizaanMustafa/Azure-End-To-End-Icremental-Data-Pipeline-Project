# Azure-End-To-End-Icremental-Data-Pipeline-Project

# Breif One Line Summary

# Overview

# Problem Statement

# Dataset

# Tools and Technologies 
- SQL

# Methods
- We need to create resources in Azure Portal i.e. Azure Sql Database, Data Factory, ADLS Storage Account,Databricks and Access Connector
- In ALDS Gen2 create three containers i.e. Bronze,Silver and Gold in order to follow Medallion Architecture.
- In the DataFactory:
   - create three linked service i.e SQL database,HTTPS,ADLS Gen2
   - In Https link service we need to add the base URL i.e. 'https://raw.githubusercontent.com'
   - Create datasets for Https and add the realtive URL and then create a parameter name 'file_name' in string format. Then under relative url add the parameter as shown in the screenshot.
   - Create a table in the sql databses with the folowwing schema then create a pipeline to copy data from https to sql database.
   - Create a watermark table as show in order for incremental loading data from sql db to adls. In our situation we are considering Date_ID column as the date column so less then minimum value of the Date_ID column must be entered in the watermark table for the initial load.
   - We need to create a stored procedure as shown so that it gets updated after the incremnetal load.
   - Now create a new pipeline and add two lookup activity, one for last_load and another for current_load. In the last_load lookup activity parametereize the sql dataet and give it it name as table_name. Go back the the lookup activity and enter teh table_name i.e water_table and below in the query write select * from water_table.
   - In the current_load lookup activity based on the parameters created in the sqldb dataset just enter the car_sales table name and under query enter select max(Date_ID) as max_date from car_sales.
   - In the copy activity connect both lookup activities and in the source enter the query under expression builder and sink would be adlsgen2. Add the store porcedure and click on import so that it aitomatically puuls the column whcih we create i.e lastload and add the current_lookup activity output under the value section. 
  



# Key Insights

# Dashboard

# How To Run This Project

# Results & Conclusion

# Future Work
