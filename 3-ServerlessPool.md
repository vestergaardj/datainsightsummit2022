## Create you first Serverless Pool Table

Navigate to the Azure Synapse Analytics resource created above

Open Synapse Studio 

Alternately use this link: https://web.azuresynapse.net/en/workspaces
Login and select appropriate workspace

Navigate to: Data

Navigate to: Linked 

Expand storage account dis-chicago-synapse/chicagodemosa

Select the 'Data (Primary)'

Double-click the folder 'Raw'

Observe: file named 'Traffic_Crashes_-_Crashes_sample.csv'

Right-click file and select 'New SQL Script/Select Top 100 Rows'

Observe new script created

Click 'Run'

Observe result set displayed

Click Tab: 'Data'

Right-Click file and select 'New SQL Script/Create external table'

Check 'Infer column names'

Verify by clicking link 'Preview Data'

Click 'Continue'

Select Database: (new) chicago-demo-sql

External table name: dbo.Crimes_sample

Check: Using SQL Script

Click: 'Open Script'

Observe four stages: 
- Create External File Format
- Create External Data Source
- Create External Table
- SELECT TOP 100 *

Click 'Run'

Observe obscure error message 🤯
Bulk load data conversion error (type mismatch or invalid character for the specified codepage) for row 1, column 1 (ID) in data file https://chicagodemosa.dfs.core.windows.net/data/Raw/Chicago_Crimes_sample3k.csv.