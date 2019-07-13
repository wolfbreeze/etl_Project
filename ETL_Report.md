## **ETL Project Report**

**Team:** Pramit Ghosh, Ileri Onabanjo, Bill Ulrich



## Extract

After scouring the internet for different sets of data, we pulled crime data for 4 major cities (Denver, Philadelphia, Boston &amp; Los Angeles) from Kaggle.com

1.  Denver [https://www.kaggle.com/paultimothymooney/denver-crime-data](https://www.kaggle.com/paultimothymooney/denver-crime-data)

2.  Phiadelphia [https://www.kaggle.com/mchirico/philadelphiacrimedata](https://www.kaggle.com/mchirico/philadelphiacrimedata)

3.  Los Angeles [https://www.kaggle.com/cityofLA/crime-in-los-angeles](https://www.kaggle.com/cityofLA/crime-in-los-angeles)

4.  Boston https://www.kaggle.com/ankkur13/boston-crime-data

## Transform

Our cleaning protocol started in Excel by reformatting every record&#39;s time from a MMDDYY to YYYY. Next, we filtered out all the petty and non-violent crimes. We saved this data into CSV and uploaded to GitHub.

In Jupyter Notebooks we used python and pandas to pull the CSV data into panda DataFrames.

Then using &quot;.replace&quot; we generalized the listed crimes to our four general violent crimes. (Homicide, Rape, Robbery, Aggravated Assault)

Individually, each city dataframe was run through &quot;.value\_counts(dropna=True, sort=True)&quot; leaving us with a dataframe with three columns and four data rows. Primary Key, Crime type, Counts. This line of code also renamed our columns, leaving four dataframes like this:

We showed out removal of non-violent crimes in the city of Los Angeles to show that it could be done in pandas as well as Excel.



## Load

Finally, to join all our dataframes we used pandas .merge and one by one we created our large table of four cities and their counts of major violent crimes.
