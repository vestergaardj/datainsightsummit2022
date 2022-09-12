## Create a data flow to curate the data

Ensure *Data flow debug* ON

Click *Author*

Click *'+'/Data flow/Data flow

Rename: Curate Crime

Click Add Source/Add Source

Name: Delta Source

Source Type: Inline

Source dataset type: Delta

Linked Services: ADLS_Crime

Set *Sampling* Enabled

Click *Settings*

Browse for folder path *data/enriched/crime*

Select Compression Type: snappy

Click *Projection*

Click *Import schema*

Click *Optimize*

Set *Partition Option* = *Set partitioning*

Set first key column = Year

Click *'+'* after Year column

Select next key column = Month

Click *Data Preview* 

Click *Refresh*

Observe the data... praise the data!

Click *'+'* after the *Delta Source*

Add *Filter*

Set *Output Stream Name* = *FilterOutliers*

Open *Expression Builder*

Set *Expression* = Latitude >= 41 && Longitude >= -88

Click *Save and Finish*

Click *Data Preview*

Observe the data :)

Click *'+'* after the *FilterOutliers* container

Add sink

Rename *Output Stream* = *DeltaTarget*

Set *Sink type* = *Delta*

Set *Linked service* = ADLS_Crime

Click *Settings*

Browse to data/curated/crime

Set *TableAction* = truncate

Click *Optimize*

Set *Partition option* = *Set partition*

Select *Year* as partition column

Click *Data Preview*

Observe data is as good as can be :)

Click *Publish All*