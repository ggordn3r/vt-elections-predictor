# vt-elections-predictor
A set of machine learning models predicting 2020 U.S. presidential election results based on socioeconomic factors, COVID statistics, and civil unrest.

## Data Analytics Final Project Proposal:
# Classifying U.S. Counties by Election Outcome

### Members:
Gerald Gordner
Niloofar Shadab

### Problem Statement – the major problem(s) being tackled. Any sub-problems investigated.

We compare 3 models that predict whether the majority of votes in a given U.S. county went to Biden or Trump. Our question is, what explains election results more accurately, socioeconomic factors, COVID events, or civil unrest?

### Data Description – describe the data in detail (including some basic statistics and exploration)

For each model, we  join county-level outcomes for the 2020 presidential election to a dataset that describes that county. The data is used to classify a county as “D” or “R” for Democrat or Republican.

#### Model A: Socioeconomics
This model is be trained on 2018 5-year American Community Survey estimates from the U.S. Census. We explore tables DP02 (Social Characteristics), DP03 (Economic Characteristics), and DP05 (Demographic and Housing Estimates).

#### Model B: COVID Statistics
This model is trained on county-level COVID data prior to Election Day from the COVID-19 Open-Data repository, including outcome data (cases, deaths) and mobility data.

#### Model C: Civil Unrest
This model is trained on created features built from the ACLED US Crisis Monitor’s weekly data on political violence and demonstrations across the country. More on this below.

### COVID- DATA PYTHON RUN

In order to run the COVID-19 based prediction, run COVID-data.ipynb. You should run all the sections of importing related dataframes from the beginning of the code. Then you can run either section of model training or all of them. For getting the US map, you need to run the last two sections of the file.

### CIVIL-UNREST DATA PYTHON RUN

In order to run the Civil-unrest based prediction, run civil_unrest_data.ipynb. You should run all the sections of importing related dataframes from the beginning of the code. Then you can run either section of model training or all of them. For getting the US map, you need to run the last section of the file.

### Combined Data of COVID and civil unrest

In order to run the combined data, run the combined.ipynb. The procedure is the same as the COVID-data.ipynb and civil_unrest_data.ipynb files.
