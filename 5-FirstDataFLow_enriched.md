## Create your first Data Flow ( < 10 min ) (Enriched)

Toogle *Data flow debug* ON

Click *Author*

Click *'+'/Data flow/Data flow

Rename: Enrich Crime

Click Add Source/Add Source

Name: CSV Source

Source Type: Data Set

Dataset: (new) CrimeCSV
-   NEW
    - Select Azure Data Lake Storage Gen2
    - Click *Continue*
    - Select *DelimitedText*
    - Click *Continue*
    - Name: *CrimeCSV*
    - (new) LinkedService
    - Name: *ADLS_Crime*
    - From Azure Subscription
    - Select appropritate subscription (housing the storage account)
    - Select Storage Account Name
    - Click *Create*
-   FilePath: data/raw/crime
-   Click *OK*
-   Click *Open*
-   Check: "First row as header"

Navigate back to data flow tab

On Source settings, set Sampling = Enable

Click *Projection*

Click *Import projection* (can take a few minutes depending on files)

Click *Data Preview*

Click *Refresh*

Observe the expected sample rows

Click *'+' after SourceCSV container

Add *Derive Column*

Rename: DeriveDate

Open Expression builder

Rename Column Name: *Date*

Set Expression = toDate(left(Date, 10), "MM/dd/yyyy")

Click *Save and finish*

Click *Data Preview*

Click *Refresh*

CLick *'+' after DeriveDate container

Add *Derive Column*

Rename: DeriveYearMonth

Open *Expression Builder*

Rename Column: Year

Set Expression = year(Date)

Add new Column

Rename Column: Month

Set Expression = month(Date)

Click *Save and Finish*

Click *Data Preview*

Click *Refresh*

Scroll far right, observe Months as numbers

Click *'+'* after DeriveYearMonth

Add Sink

Rename: TargetDelta

Sink Type: Inline

Inline Dataset Type: Delta

Linked Service: ADLS_Crime

Click *Settings*

Browse for data/enriched/crime (if the path does not exist, create it in Azure Storage Explorer)

Click *Mapping*

Uncheck *Auto Mapping*

Remove Column: *_c0* 

Rename all columns that include blank spaces: Case Number, Primary Type, Location Description, Community Area, FBI Code, X Coordinate, Y Coordinate, Updated On

Click *Optimize*

Set *Partition Option* to *Set partitioning*

Select Key Columns: *Year*

Click *'+'* after *Year* column

Select Key Columns: *Month*

Click *Data Preview*

Click *Refresh*

Observe that data is as expected

Click *Publish All*