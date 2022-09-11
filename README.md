# Data Insight Summit 2022 - Chicago
This repo is for the attendees at the Data Insight Summit 2022 in Chicago

# Sources
We are going to use the follwoing sources:

https://www.kaggle.com/code/fahd09/eda-of-crime-in-chicago-2005-2016/data
and for your conveinience (of you not already have an account at Kaggle) I have placed a copy of the files here in this repo.

https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Chicago-Zip-Code-and-Neighborhood-Map/mapn-ahfc


# Demo
## Create Resource Group (< 1 min)
Name: chicago_demo
Region: optional
Tags: Owner, State, Purpose

## Create Azure Synapse Analytics (<15 min)

  ### Basic
Managed resource group: optional (for aux resources)
Name: dis-chicago-synapse
region: <same as above?>

Select Data Lake Storage Gen2: From Subscription
Account: (new) chicagodemosa

File System Name: (new) data

Check "Assign myself the Storage Blob Data Contributor role on the Data Lake Storage Gen2 account to interactively query it in the workspace."

  ### Security

Select: "Use both local and Azure Active Directory (Azure AD) authentication"

SQL Server Admin login: sqladminuser
SQL Password: <select fitting password>

All other options: leave as is

  ### Networking

Check: "Allow connections from all IP addresses"

All other options: leave as is

### Tags
Tags: Owner, State, Purpose

