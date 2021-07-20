# <a title="United States Covid-19 Activity LSTM Time-Series Model"> United States Covid-19 LSTM Time-series Model</a>

The New York Times is releasing a series of data files with cumulative counts of coronavirus cases in the United States, at the state and county level, over time. 
This time series data from state and local governments and health departments have been compiled and can be found on [kaggle](https://www.kaggle.com/fireballbyedimyrnmom/us-counties-covid-19-dataset) to provide a complete record on the ongoing pandemic activity in the United States. Since late January, The Times has tracked cases of coronavirus in real time as they were identified after testing. Because of the widespread shortage of testing, however, the data is necessarily limited in the picture it presents of the outbreak.

I have used the dataset to build a LSTM model, a type of Artificial Neural Network that can process sequential data/time series, to predict the future trajectory of new Covid cases for a given state. The model was built using Keras from the tensorflow library in Python.

## Data Overview

The dataset contained the following information for every state and US territory :

- date: from Jan. 21, 2020 and is being updated constantly (2020-07-11 for this set)
- fips =a specific code for counties, this may vary for metro areas
- county
- state
- cases: cumulative cases to the date
- deaths: cumulitive deaths to the date

For the model, we changed the cumulitive cases to daily new Covid cases and set the start date to 03/28/2020 where the the last state/terriory reported their first Covid case. Below displays the general trends of Covid across the United States.  

> ![Covid Cases](https://github.com/ClaytonOlsen/Covid_timeseries_lstm/blob/main/images/covid_cases.png)

We can see that there was a large collective increase in the Winter of 2020/2021 and has since been on the decrease with increased accessibility to vaccines. Some states have spikes of cases that cause different trajectories between states, but ultimately, the number of new cases is trending towards 0. 
