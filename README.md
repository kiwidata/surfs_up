# surfs_up

## Overview of the analysis

In this analysis, the temperature data for the months of June and December in Oahu are been compared to determine for W.Avy if the surf and ice cream shop business is sustainable year-round.

## Results

The June temparatures statistics are as followed based on our data: 
- A mean temperature of 75 degrees, with a minimum temperature of 64 degrees and a maximum temperature of 85 degrees. 
- The temperature is above 73 degrees 75% of the time.
- The standard deviation is only 3.25 degrees from the mean

![June Temperatures](https://user-images.githubusercontent.com/111706055/200136809-735a7fba-15b3-4316-8e34-2c2afac1ef64.png)

The December temparatures statistics are as followed based on our data: 
- A mean temperature of 71 degrees, with a minimum temperature of 56 degrees and a maximum temperature of 83 degrees. 
- The temperature is above 69 degrees 75% of the time.
- The standard deviation is only 3.75 degrees from the mean

![December Temperatures](https://user-images.githubusercontent.com/111706055/200136813-d0046bce-c5e4-4f5c-b053-3a4a2a1a3a64.png)

## Summary

Based on this data, the temperatures in June and December are usually above 70 degrees and are very similar with a slight hotter month in June. Thus, based on this data, the ice cream shop business is sustainable year round. 

2 queries related to precipitation would gather more weather data for June and December. Please find below the query for the June dataset for precipitation. 

from sqlalchemy import extract
June_Month_Prec = session.query(Measurement.date,Measurement.prcp).filter(extract('month', Measurement.date)==6).all()
June_Month_Prec
prec_df = pd.DataFrame(June_Month_Prec, columns=['date','June Prec'])
prec_df.set_index(prec_df['date'], inplace=True)
prec_df = prec_df.sort_index()
prec_df.head(5)
prec_df.describe()

This is similar for the December query.
Please find find below the statistic for precipitation for both of these months

![June Precipitation](https://user-images.githubusercontent.com/111706055/200137964-5fc2e3ee-b470-411a-a727-423a6735a709.png)

![December Precipitation](https://user-images.githubusercontent.com/111706055/200137966-11fc30a9-a586-444b-b931-9cd227048e74.png)

Based on this data there is more rainfall in December than June.
