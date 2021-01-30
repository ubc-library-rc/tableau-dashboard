---
layout: default
title: Connecting to data
nav_order: 5
parent: Workshop content
---
# Connecting to data

## Understanding your data
The [sample data](data/time_series_covid19.zip) is a .zip with two .csv files from the [Novel Coronavirus (COVID-19) Cases Data](https://data.humdata.org/dataset/novel-coronavirus-2019-ncov-cases) compiled by the Johns Hopkins University Center for Systems Science and Engineering (JHU CCSE). The second header line was removed from each file to simplify import into Tableau.

- **time_series_covid19_confirmed_global_narrow.csv** - confirmed cases by day and country
- **time_series_covid19_deaths_global_narrow.csv** - deaths by day and country

<br/>

Both files are structured the same way. Every day there is one row for each geographic area, and the _Value_ column contains the cumulative total count up to that date.

<img style="margin-left:40px; margin-bottom:50px" src="images/data-1.png"/>

For some countries data is available at the _Province/State_ level. In these cases there are multiple rows per day, one for each province/state.

<img style="margin-left:40px; margin-bottom:50px" src="images/data-2.png"/>

Where province/state information is available, the total count for a country is the sum of the _Value_ column on a particular date.

"Narrow" data is preferable to "wide" data in visualization software. This data is narrow: all counts appear in the same column.
{: .note}
 
## Connecting to multiple data files
Our sample dataset is in two files. Tableau has several options for bringing data from multiple files into the same _workbook_. The recommended method in most cases is to use _Relationships_ to link files or tables (for more information see the Tableau help article [Relate Your Data](https://help.tableau.com/current/pro/desktop/en-us/relate_tables.htm)).


### *1*{: .circle .circle-yellow} Connect the files with a relationship
The video below illustrates how to add and connect the two files. 

1. Open Tableau and select _Text file_ in the _Connect to Data_ menu
2. Select `time_series_covid19_confirmed_global_narrow.csv`
3. Once loaded, other text files in the same directory are listed on the left; drag `time_series_covid19_deaths...` to the top-middle pane to create a relationship
4. In the _Edit relationships_ pop-up add one row linking the tables by _Country/Region_ and a second row linking them by _Date_
5. Close the pop-up window and rename the files to `cases table` and `deaths table`
6. Rename the data source to `covid data`
{: .step}

<video controls="controls" width="100%" name="Connect data with a relationship" src="images/connect.mp4">
</video>

Renaming tables and data sources is not strictly necessary but makes it easier to navigate the Tableau interface and identify your measures and dimensions.
{: .note}

Once both files are added click the _Sheet 1_ tab near the bottom of the screen to start working with the data.
