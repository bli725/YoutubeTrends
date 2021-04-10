# YoutubeTrends

Project is posted on Kaggle at:
https://www.kaggle.com/thebli/youtube-trending-video-eda-using-tableau/output

This code is a preprocessing script for an Exploratory Data Analysis project on Youtube Trends.
The script combines the 10 datasets into 2 primary tables and uploads the information to a local MySQL server for use in Tableau. Along with the primary tables, separate tables are created for Category information and for analyzing the Video Tags.

2 primary tables(fulldf_lastTrendingDateOnly1 and fulldf_countrytags)
* Both tables contain all the fields of the original datasets. Since each observation of a trending video includes cummulative information on its interactions(Views, Likes, etc.), we require a a table that includes information on totals from all views while the video was trending. One table is to be used for the 'All Countries' filter in Tableau, while the other tag will be filterable by individual countries.
* fulldf_lastTrendingDateOnly1 uses each Video ID as a unique identifier and takes statistics from the most recent observation to best estimate this. fulldf_countrytags does this as well but further groups each Video ID by which countries the video trended in. There are 23,062 duplicated Video IDs in fulldf_percountry since videos trended in multiple countries.

1 table as a list of tags - Explodes the string of tags that is given for each video and displays them as separate lines for analysis in Tableau.

1 table for category information - aggregates the information given on categories for reference.

.csv files are also saved locally as a backup.
