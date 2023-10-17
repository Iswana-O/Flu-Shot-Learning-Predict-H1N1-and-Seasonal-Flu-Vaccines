
#  FLU SHOT LEARNING: PREDICT H1N1 AND SEASONAL FLU VACCINES
![](/images/vaccine.jpg)


## Project Overview
In the early years of the 21st century, the health landscape has been significantly influenced by the rise of new viruses and global outbreaks. Roughly ten years apart, the World Health Organization (WHO) announced two major pandemics: influenza A H1N1 in 2009 and COVID-19 in 2020. Additionally, the world has seen outbreaks of non-respiratory viruses such as Zika, Chikungunya, and Ebola, which have garnered significant attention from global health authorities. Given these occurrences, it's evident that viruses will increasingly shape the realm of infectious diseases in the coming decades.
The year 2020 was unexpectedly dominated by the COVID-19 pandemic, which first appeared in Wuhan, China, towards the end of 2019. This pandemic is attributed to a new coronavirus, SARS-CoV-2, known to cause severe acute respiratory syndrome (SARS), hence its classification within the SARS taxonomy. Notably, there had been prior alerts about coronaviruses being potential pandemic triggers. This was evidenced by the SARS-CoV outbreak in 2002-2003 and the Middle East Respiratory Syndrome (MERS) in 2012 .

To sum up, the two prominent pandemics of this century were caused by distinct viruses, yet shared similarities, such as being enveloped RNA viruses with typically spherical shapes. Another noteworthy observation is the frequent mutations of these viruses and the wide range of hosts they can infect. Recognizing the significance of understanding the epidemiology of these pandemics and grasping the interplay between individuals' backgrounds, beliefs, and health habits in relation to their vaccination decisions offers valuable insights for shaping future public health strategies concerning pandemics.

When we understand the intricate relationships and patterns within data, especially from the perspective of data classification and analysis, it offers valuable insights for several reasons:

**Historical Context:** By analyzing data from previous pandemics, we can identify patterns and trends that have emerged over time. This can provide a historical context to understand how and why certain populations reacted to vaccination campaigns in specific ways.

**Predictive Value:** Insights derived from past data can be used to predict future behaviors. For instance, if certain demographic groups consistently showed hesitancy towards vaccinations during past pandemics, targeted awareness campaigns can be developed for these groups in the future.

**Tailored Interventions:** Understanding personal vaccination patterns in relation to backgrounds and opinions allows for the creation of tailored public health interventions. If certain cultural or socio-economic groups have specific concerns or misconceptions about vaccines, interventions can be designed to address those specific issues.

**Resource Allocation:** Insights from data classification can guide where resources (like awareness campaigns, vaccination centers, or community health workers) might be most effectively deployed.

**Behavioral Insights:** By understanding health behaviors and opinions, public health officials can better comprehend the underlying reasons for vaccine acceptance or hesitancy. This can inform the design of more effective communication strategies.

**Refinement of Strategies:** Analysis of past data can help in refining strategies for future pandemics. By understanding what worked and what didn't, strategies can be adjusted for greater effectiveness in the future.

**Stakeholder Engagement:** By demonstrating an understanding of the concerns and behaviors of different groups, public health officials can build trust and engage more effectively with communities.


## Research Questions:
As the world struggles to vaccinate the global population against COVID-19, an understanding of how people’s backgrounds, opinions, and health behaviors are related to their personal vaccination patterns can provide guidance for future public health efforts. Your audience could be someone guiding those public health efforts.

This challenge: can you predict whether people got H1N1 and seasonal flu vaccines using data collected in the National 2009 H1N1 Flu Survey? This is a binary classification problem, but there are two potential targets: whether the survey respondent received the seasonal flu vaccine, or whether the respondent received the H1N1 flu vaccine. Please choose just one of these potential targets for your minimum viable project.


 **DATA SOURCE:** DrivenData. (2020). Flu Shot Learning: Predict H1N1 and Seasonal Flu Vaccines. Retrieved [10 /17/2023] from https://www.drivendata.org/competitions/66/flu-shot-learning.

## Data Exploration
We have two data sets that we have merged
training_set_features

contains information about the respondents, such as their level of concern about the H1N1 virus, knowledge about H1N1, behavioral habits, and demographic details.

training_set_labels

provides the target variables for each respondent, indicating whether they received the H1N1 vaccine (h1n1_vaccine) and the seasonal vaccine (seasonal_vaccine).

	Missing Values	Percentage
employment_occupation	13470	50.436215
employment_industry	13330	49.912008
health_insurance	12274	45.957989
income_poverty	4423	16.561201
doctor_recc_h1n1	2160	8.087767
doctor_recc_seasonal	2160	8.087767
rent_or_own	2042	7.645936
employment_status	1463	5.477965
marital_status	1408	5.272026
education	1407	5.268282
chronic_med_condition	971	3.635751
child_under_6_months	820	3.070356
health_worker	804	3.010447
opinion_seas_sick_from_vacc	537	2.010709
opinion_seas_risk	514	1.924589
opinion_seas_vacc_effective	462	1.729884
opinion_h1n1_sick_from_vacc	395	1.479013
opinion_h1n1_vacc_effective	391	1.464036
opinion_h1n1_risk	388	1.452803
household_adults	249	0.932340
household_children	249	0.932340
behavioral_avoidance	208	0.778822
behavioral_touch_face	128	0.479275
h1n1_knowledge	116	0.434343
h1n1_concern	92	0.344479
behavioral_large_gatherings	87	0.325757
behavioral_outside_home	82	0.307036
behavioral_antiviral_meds	71	0.265848
behavioral_wash_hands	42	0.157262
behavioral_face_mask	19	0.071142


