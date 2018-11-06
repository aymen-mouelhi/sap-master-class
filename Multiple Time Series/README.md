This hands-on guide shows how to forecast multiple time series at once with SAP Predictive Analytics, Automated Mode. Use the scripting functionality to produce forecasts en masse.

The data used in this guide is publicly available so that the reader can follow hands-on and carry out the same analysis.

Please note that this guide is giving a high-level introductory overview and only shows a small fraction of the available functionality.

Download the tutorial and all required files (source data, sample script) from GitHub.

In case you are new to time-series forecasting with SAP Predictive Analytics, I suggest to follow this tutorial first, working with just a single time-series: Hands-On Tutorial SAP Predictive Analytics, Automated Mode: Time Series Analysis

Happy Forecasting!

Update July 2016: With the release of SAP Predictive Analytics 3.0, it is possible to easily automate the forecasting of many time-series without having to script as described on this page. Please see this article for details:

Create One Forecasting Model, Automate Many with SAP Predictive Factory 3.0!



From <https://blogs.sap.com/2015/10/14/hands-on-tutorial-sap-predictive-analytics-automated-mode-multiple-time-series/>  


Dynamically forecasting multiple time series

Creating the forecast with the graphical user interface was easy. In case you have only a few time series to forecast, you will be done quickly. If however you have a much larger number of time series to forecast a different approach is needed. A retailer for instance that wants to forecast sales quantities on individual product items by stores has to repeatedly forecast thousands of time series.

In such a situation scripting is needed to produce the forecasts en masse. Everything that is done in the graphical user interface can be specified with a script. Through such scripts it is possible to forecast as many time series as needed. You do not have to write a new script yourself from scratch. Instead you carry out one forecast in the graphical interface and SAP Predictive Analytics provides you with the script that recreates what the user did in the graphical interface. Now you just need to modify the script to handle multiple time series and you can forecast as many time series as needed with fairly little effort.

Typically the script it split between two files. One script is training and saving the models. Another script loads these models and does the actual forecasts.

The following chapters apply this model to forecast three different time series through scripting. We forecast the number of accidents in the City, in the Countryside and on the Motorway (based on the data in AccidentsMultipleLocations.csv). The same principle applies to forecasting much larger number of time series.

This tutorial uses a flat file as data source. The same concept would apply connecting to a database. Either way, it is important that the dataset is sorted in descending order by date when it is filtered on one individual time series (so one single accident location in this example).
