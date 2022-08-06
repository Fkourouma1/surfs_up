# surfs_up
# Overview of the analysis
In this project, we are looking for an investor to invest into our Surfs Shop and Ice Cream that we are looking for opening in Oalu. W.Avy, a potential investor, requested a data analysis based on the weather on Uola island. We did a few analysis in the module on the weather. Now he is asking more information about the temperature trends of the months of June and December in Oahu, in order to determine if the surf and ice cream shop business is sustainable year-round.

## Results
This challenge consists of two technical analysis deliverables and a written report.
### Deliverable 1: Determine the Summary Statistics for June
In this first step, We first made sure all the right dependencies are imported correctly, then we created the engine to run our queries in SQLite. We reflect and save the tables. Finally create our session.
Next, we determine the summary Statistics for June. We started by filtering the measurement table to retrieve the temperatures for the Month of June by using this code : June_temperatures = session.query(Measurement).filter(extract('month', Measurement.date) == 6).
Then we calculate the summary statistics by using this script: June_temp_df.describe()
We notice that the average temperature is between 64(as min) and 85(as max). The standard deviation shows 3.257417 and the mean shows 74.944118.
### Deliverable 2: Determine the Summary Statistics for December
we determine the summary Statistics for June. We started by filtering the measurement table to retrieve the temperatures for the Month of June by using this code: Dec_temperatures = session.query(Measurement).filter(extract('month', Measurement.date) == 12).
Then we calculate the summary statistics by using this script: Dec_temp_df.describe()
We notice that the average temperature is between 56(as min) and 83(as max). The standard deviation shows 3.745920 and the mean shows 71.041529.

## Summary
We noticed that, there is no much differences between the maximum temperature of the months of June and December as 85 and 83. But the minimum is a little different. June minimum temperature is 64 while December is 56.
Regarding two other queries to gather more information on the weather, we could create queries to get the temperature for the month February and September.

1- Query to retrieve February temperature summary

Feb_temperatures = session.query(Measurement).filter(extract('month', Measurement.date) == 2)
Feb_temp_list = [temp.tobs for temp in Feb_temperatures]
Feb_temp_df = pd.DataFrame(Feb_temp_list, columns=["Feb Temps"])
Feb_temp_df.describe()

2- Query to retrieve September temperature summary

Sep_temperatures = session.query(Measurement).filter(extract('month', Measurement.date) == 9)
Sep_temp_list = [temp.tobs for temp in Sep_temperatures]
Sep_temp_df = pd.DataFrame(Sep_temp_list, columns=["Sep Temps"])
Sep_temp_df.describe()



