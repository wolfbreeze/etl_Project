## **ETL Project Report**

**Team:** Pramit Ghosh, Ileri Onabanjo, Bill Ulrich



## Extract

After scouring the internet for different sets of data, we pulled crime data for 4 major cities from Kaggle.com

1.  [Denver](https://www.kaggle.com/paultimothymooney/denver-crime-data)

2.  [Phiadelphia](https://www.kaggle.com/mchirico/philadelphiacrimedata)

3.  [Los Angeles](https://www.kaggle.com/cityofLA/crime-in-los-angeles)

4.  [Boston](https://www.kaggle.com/ankkur13/boston-crime-data)

## Transform

Our cleaning protocol started in Excel by reformatting every record&#39;s time from a MMDDYY to YYYY. Next, we filtered out all the petty and non-violent crimes. We saved this data into CSV and uploaded to GitHub.

In [Jupyter Notebooks](ETL_Crimes.ipynb) we used python and pandas to pull the CSV data into panda DataFrames.

Then using ``.replace`` we generalized the listed crimes to our four general violent crimes. (Homicide, Rape, Robbery, Aggravated Assault)

Individually, each city dataframe was run through `` .value\_counts(dropna=True, sort=True)`` leaving us with a dataframe with three columns and four data rows. Primary Key, Crime type, Counts. This line of code also renamed our columns, leaving four dataframes like this:


![alt text][logo]

[logo]: https://raw.githubusercontent.com/wolfbreeze/etl_Project/master/Resources/Screen%20Shot%202019-07-13%20at%2011.17.59%20AM.png "Logo Title Text 2"

We showed out removal of non-violent crimes in the city of Los Angeles to show that it could be done in pandas as well as Excel.



## Load

Finally, to join all our dataframes we used pandas ``.merge`` and one by one we created our large table of four cities and their counts of major violent crimes. We chose to use ``.merge`` in pandas as we wanted to watch the table grow as we added each city. We know we could have used a for loop and in just as many lines of code the final table would have been formed but again we wanted to watch the table grows and we merged each dataform in.


![alt text][logo2]

[logo2]: https://raw.githubusercontent.com/wolfbreeze/etl_Project/master/Resources/Screen%20Shot%202019-07-13%20at%2011.45.39%20AM.png "Logo Title Text 2"
