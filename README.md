Environmental Factors vs. Health Outcomes
==============================

There is a push in the U.S. to address environmental injustices. Overburdened communities are defined as “minority, low-income, tribal, or indigenous populations or geographic locations in the United States that potentially experience disproportionate environmental harms and risks.” To determine which are the most pressing environmental problems, the harm from particular environmental problems should be quantified in terms of health effects.  
 
The goal of this research was to predict specific negative health outcomes: asthma prevalence, cancer, chronic kidney disease, chronic obstructive pulmonary disease (COPD), coronary heart disease (CHD), and stroke from a variety of environmental factors. This prediction would allow these outcomes to be linked to specific environmental factors in overburdened communities.  
 
The dataset with the eleven environmental indicators came from the EJScreen [environmental justice screen] 2020 of the U.S. Environmental Protection Agency. The abbreviations for these indicators are defined in the appendix. The data on the health outcomes were obtained from U.S. Centers for Disease Controls and Prevention’s Local Data for Better Health 2022, which is based on 2020 information. 
 
Data Wrangling, EDA, and Pre-processing 
Since the health data was collected at the census tract level and the environmental data was collected at the census block level, data wrangling was needed in order to combine the two datasets. The environmental data was converted to census tracts by combining the blocks within each tract by population-weighted averaging. 
 
No correlation was found between the health outcomes and any one of the environmental risk factors. For example, Figure 1 shows a heat map of COPD. Only the lead paint indicator (PRE1960PCT) is greater than 0.10 positively correlated with the prevalence of COPD; however, this correlation is very, very small. Diesel fuel particulates (DSLPM), proximity to and volume of traffic (PTRAF), and proximity to treatment storage and disposal facilities (PTSDF) are all less 

Notebooks:

01.data_wrangling

02.EDA

03.Pre-processing_CHD

04.Pre-processing_COPD

05.Pre-processing_asthma

06.Pre-processing_cancer

07.Pre-processing_kidney

08.Pre-processing_stroke

09.Modeling_CHD

10.Modeling_COPD

11.Modeling_asthma

12.Modeling_cancer

13.Modeling_kidney

14.Modeling_stroke


