# Covid Cases by US States

[Coivd Data](https://www.kaggle.com/fireballbyedimyrnmom/us-counties-covid-19-dataset?select=us-counties.csv)

The New York Times is releasing a series of data files with cumulative counts of coronavirus cases in the United States, at the state and county level, over time. We are compiling this time series data from state and local governments and health departments in an attempt to provide a complete record of the ongoing outbreak.

- date: from Jan. 21, 2020 and is being updated constantly (2020-07-11 for this set)
- fips =a specific code for counties, this may vary for metro areas
- county
- state
- cases: total cases to the date
- deaths: total deaths to the date

I am implementing a multi-state LSTM where we aim to predict the cases by state. We will turn the total cases into daily new cases for the predictions.

Additionally the states will be labeled with a corresponding code number:

dictionary = {['Alabama':1, 'Alaska':2, 'Arizona':3, 'Arkansas':4, 'California':5, 'Colorado':6, 'Connecticut':7, 'Delaware':8, 'District of Columbia':9, 'Florida':10, 'Georgia':11, 'Guam':12, 'Hawaii':13, 'Idaho':14, 'Illinois':15, 'Indiana':16, 'Iowa':17, 'Kansas':18, 'Kentucky':19, 'Louisiana':20, 'Maine':21, 'Maryland':22, 'Massachusetts':23, 'Michigan':24, 'Minnesota':25, 'Mississippi':26, 'Missouri':27, 'Montana':28, 'Nebraska':29, 'Nevada':30, 'New Hampshire':31, 'New Jersey':32, 'New Mexico':33, 'New York':34, 'North Carolina':35, 'North Dakota':36, 'Northern Mariana Islands':37, 'Ohio':38, 'Oklahoma':39, 'Oregon':40, 'Pennsylvania':41, 'Puerto Rico':42, 'Rhode Island':43, 'South Carolina':44, 'South Dakota':45, 'Tennessee':46, 'Texas':47, 'Utah':48, 'Vermont':49, 'Virgin Islands':50, 'Virginia':52, 'Washington':52, 'West Virginia':53, 'Wisconsin':54, 'Wyoming':55]}
