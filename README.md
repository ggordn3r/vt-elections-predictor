# vt-elections-predictor
A set of machine learning models predicting 2020 U.S. presidential election results based on socioeconomic factors, COVID statistics, and civil unrest.

## Data Analytics Final Project Proposal:
# Classifying U.S. Counties by Election Outcome

### Members:
Gerald Gordner
Niloofar Shadab

### Problem Statement – the major problem(s) being tackled. Any sub-problems investigated.

We will compare up to 3 models that predict whether the majority of votes in a given U.S. county went to Biden or Trump. Our question is, what explains election results more accurately, socioeconomic factors, COVID events, or civil unrest? We will also compare our models to the outputs of a traditional election forecast based on polling data.

### Data Description – describe the data in detail (including some basic statistics and exploration)

For each model, we will join county-level outcomes for the upcoming 2020 presidential election (for example, from MIT’s Election Lab) to a dataset that describes that county. The data will be used to classify a county as “D” or “R” for Democrat or Republican.

#### Model A: Socioeconomics
This model will be trained on 2018 5-year American Community Survey estimates from the U.S. Census. At a minimum, we will explore tables DP02 (Social Characteristics) and DP03 (Economic Characteristics).

#### Model B: COVID Statistics
This model will be trained on county-level COVID data prior to Election Day from the COVID-19 Open-Data repository, including outcome data (cases, deaths), static covariate data (health statistics), and dynamic covariate data (mobility, search trends, and government interventions) as available.

#### Model C: Civil Unrest
This model will be trained on created features built from the ACLED US Crisis Monitor’s weekly data on political violence and demonstrations across the country. More on this below.

### Data Pre-processing – any data transformation performed (if needed)

#### Model A
-	Reduce dimensions using PCA
-	Transform categorical variables (e.g. race)
-	Normalize features to account for differences in scale (e.g. household income vs. number of individuals in household) and population size between counties

#### Model B
-	Normalize features to account for differences in scale (e.g. cases vs. deaths) and population size between counties

#### Model C
-	ACLED data is reported by latlong, which we will crosswalk to county names
-	The data is also incident-level and time-series, so we will create features of type, frequency, and intensity of protest, e.g. “violent protest occurred in 2020 (0 or 1)”

### Data Exploration – provide a way to summarize the data

We will build a 4-color choropleth map (TP, FP, TN, and FN) for each model to facilitate exploration and identify patterns of error. We may also overlay the margin of victory to highlight races that were particularly difficult to predict.

### Model Building – algorithms used and evaluated

We are framing our project as a classification problem, with the actual election results as class labels (e.g. "D" for democrat if a county goes for Biden vs. "R" for Trump). We intend to use either a decision tree or tree-assisted naïve Bayes (TAN) to make our results explainable and account for the strong dependencies in our datasets (e.g. poverty levels and household incomes, COVID cases and deaths). The algorithm used will be consistent across all three models to facilitate comparison. For each model we will perform cross-validation with 10 folds.

### Model Evaluation – evaluate the results and maybe show comparisons

We will evaluate the models with typical metrics (accuracy, precision, recall, f-measure) across all counties. In addition to our internal comparisons between models, we will compare our results with the publicly available outputs of the most prominent conventional model of political opinion and activity: FiveThirtyEight.

### COVID- DATA PYTHON RUN

In order to run the COVID-19 based prediction, run COVID-data.ipynb. You should run all the sections of importing related dataframes from the beginning of the code. Then you can run either section of model training or all of them. For getting the US map, you need to run the last two sections of the file.

### CIVIL-UNREST DATA PYTHON RUN

In order to run the Civil-unrest based prediction, run civil_unrest_data.ipynb. You should run all the sections of importing related dataframes from the beginning of the code. Then you can run either section of model training or all of them. For getting the US map, you need to run the last section of the file.

### Combined Data of COVID and civil unrest

In order to run the combined data, run the combined.ipynb. The procedure is the same as the COVID-data.ipynb and civil_unrest_data.ipynb files.
