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
  



# Key Insights

# Dashboard

# How To Run This Project

# Results & Conclusion

# Future Work
