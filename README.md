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

We can see that there was a large collective increase in the Winter of 2020/2021 and has since been on the decrease with increased accessibility to vaccines. Some states have spikes of cases that cause different trajectories between states, but ultimately, the number of new cases is trending towards 0. The variation in state cases and large spikes due to outbreaks may phurt predictive accuracy.

## Experimental Results

For choosing the nodes, number of layers etc. we used:

- Batch Size of 64, as is common
- input layer with nuerons equal to the input size 55 (number of states)
- output layer equal to the number of states
- the nuerons for the hidden layer where estimated from the following equation

$$N_h= \frac{N_s}{(\alpha * (N_i + N_o))}$$

- N_i = Number of input nuerons
- N_o = Number of output nuerons
- N_s = Number of samples in training data set
- $\alpha$  = An arbitrary scaling fator set at 5

So, $N_h \approx 47$.

The following picture show the trend of loss Function, Mean Squared Error, of actual data compared to predicted data:

> ![Covid Cases](https://github.com/ClaytonOlsen/Covid_timeseries_lstm/blob/main/images/epoc_vs_accuracy.png)

Since there is limited availble data, and some states experienced random spikes in covid cases apart from the general direction fo new cases across states, the predictive accuracy is fairly limited. 

## Prediction

The predicitions for the first 10 states is deisplayed below. The other 45 states can be found under images.

> ![Covid Cases](https://github.com/ClaytonOlsen/Covid_timeseries_lstm/blob/main/images/states_1-10.png)


