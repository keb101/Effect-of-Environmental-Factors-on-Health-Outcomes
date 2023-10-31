Environmental Factors vs. Health Outcomes
==============================

## 1. Goal
There is a push in the U.S. to address environmental injustices. Overburdened communities are defined as “minority, low-income, tribal, or indigenous populations or geographic locations in the United States that potentially experience disproportionate environmental harms and risks.” To determine which are the most pressing environmental problems, the harm from particular environmental problems should be quantified in terms of health effects.  
 
The goal of this research was to predict specific negative health outcomes: asthma prevalence, cancer, chronic kidney disease, chronic obstructive pulmonary disease (COPD), coronary heart disease (CHD), and stroke from a variety of environmental factors. This prediction would allow these outcomes to be linked to specific environmental factors in overburdened communities.  

## 2. Data
The dataset with the eleven environmental indicators came from the [EJScreen](https://gaftp.epa.gov/EJSCREEN/2021/) (environmental justice screen) 2020 of the U.S. Environmental Protection Agency . The data on the health outcomes were obtained from the U.S. Centers for Disease Controls and Prevention’s [Local Data for Better Health 2022](https://chronicdata.cdc.gov/500-Cities-Places/PLACES-Local-Data-for-Better-Health-Census-Tract-D/cwsq-ngmh), which is based on 2020 information. The EPA data was collected at the census block level and the CDC data was collected and the census tract level; these were combined by taking a weighted average per population of each census block within a census tract for the EPA data.

The six health outcomes:
+ Asthma 
+ Cancer
+ Chronic Kidney Disease
+ Chronic Obstructive Pulmonary Disease (COPD)
+ Coronary Heart Disease (CHD)
+ Stroke


The environmental indicators:
+ PM25 = Particulate matter 2.5 level in air
+ OZONE = Ozone level in air
+ DSLPM = Diesel particulate matter level in air
+ CANCER = Air toxics cancer risk
+ RESP = Air toxics respiratory hazard index
+ PTRAF = Traffic proximity and volume
+ PRE1960PCT = % pre-1960 housing (lead paint indicator)
+ PNPL = Proximity to National Priorities List (NPL) [superfund] sites
+ PRMP = Proximity to Risk Management Plan (RMP) facilities, facilities that use extremely hazardous substances PTSDF = Proximity to Treatment Storage and Disposal facilities (TSDF)
+ PWDIS = Indicator for major direct dischargers to water

## 3. EDA
Histograms of the prevalence of each health outcome:

<p align="center">
  <img src="reports/for readme/hists.png" width="400">
</p>

 ## 4. Preprocessing

 The decision tree ensemble methods do not need data to be normalized, but SVM does. Below are histograms showing the distribution of data for reach environmental factor before normalization (blue) and after normalization (red): 

<p align="center">
  <img src="reports/for readme/hist.jpg" width="400">
  <img src="reports/for readme/hist1.jpg" width="400">
</p>

## 5. Modeling

The following models were used to predict each health outcome based on the environmental factors.
+ Random forest
+ Adaptive boosting
+ Gradient boosting
+ Extreme gradient boosting
+ Light gradient boosting machine
+ Support vector machine

Hyperparameters were optimized using randomized and Bayesian searching.

Below is a graph of the predicted values versus actual values for COPD using random forest with hyperameters tuned with a randomized search.

<p align="center">
  <img src="reports/figures/COPD_graph_best_model.png" width="600">
</p>

## 6. Metrics

The table below shows the metrics for the best model for each health outcome.

<p align="center">
  <img src="reports/figures/metrics.png" width="700">
</p>


## 7. Conclusion
None of the models used in this research were good predictors of any of the health outcomes.

Likely reasons:
+ The health outcome data used were self-reported.
+ While certain environmental factors are known to increase one’s chances for certain diseases, there is a time factor. Comparing health and environmental data from the same year and geographical area intuitively makes sense, but it does not consider the environment in which the people were over time prior to getting the diseases.


## 8. Future Work
+ Obtain objective health data
+ Only include only people who have been living in the same census tract for at least 10 years
+ Use multiple years of environmental data.
