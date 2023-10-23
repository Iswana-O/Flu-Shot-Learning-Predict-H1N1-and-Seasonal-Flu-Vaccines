
#  FLU SHOT LEARNING: PREDICT H1N1 AND SEASONAL FLU VACCINES
![](/images/vaccine.jpg)


## Project Overview
In the early years of the 21st century, the health landscape has been significantly influenced by the rise of new viruses and global outbreaks. Roughly ten years apart, the World Health Organization (WHO) announced two major pandemics: influenza A H1N1 in 2009 and COVID-19 in 2020. Additionally, the world has seen outbreaks of non-respiratory viruses such as Zika, Chikungunya, and Ebola, which have garnered significant attention from global health authorities. Given these occurrences, it's evident that viruses will increasingly shape the realm of infectious diseases in the coming decades.
The year 2020 was unexpectedly dominated by the COVID-19 pandemic, which first appeared in Wuhan, China, towards the end of 2019. This pandemic is attributed to a new coronavirus, SARS-CoV-2, known to cause severe acute respiratory syndrome (SARS), hence its classification within the SARS taxonomy. Notably, there had been prior alerts about coronaviruses being potential pandemic triggers. This was evidenced by the SARS-CoV outbreak in 2002-2003 and the Middle East Respiratory Syndrome (MERS) in 2012.

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

## MISSING VALUES AND DUPLICATES

From our merged data set we have no duplicates

Several columns have missing values. The columns employment_occupation, employment_industry, and health_insurance have notably high percentages of missing data, with 50.44%, 49.91%, and 45.96% missing respectively. To handle the missing data, we have a few options:

For categorical data: Fill missing values with the mode (most frequent value) of the column. Create a new category, e.g., "Unknown" or "Not Provided". For numerical data: Fill with mean, median, or a designated placeholder value. Use a model like KNN to impute the missing values. We shall use this as we fill the missing values

## Visualising categorical data
![](/images/h1%20concern%20and%20knowledge.png)


![](/images/behavioral.png)



we can observe:

The majority of respondents have a moderate level of concern (Level 2) about H1N1. The number of respondents with a high level of concern (Level 3) is slightly lower than those with a moderate level. Fewer respondents have low concern or no concern about H1N1 (Levels 0 and 1).

H1N1 Knowledge:

The majority of respondents have a moderate level of knowledge about H1N1 (Level 2). A significant number have a high level of knowledge (Level 1). Few respondents have no knowledge about H1N1 (Level 0). Behavioral Antiviral Meds:

Most respondents did not take antiviral medications. Only a small proportion took antiviral medications. Health Insurance:

A significant number of respondents have health insurance. However, there's also a considerable number of respondents without health insurance. Opinion on H1N1 Risk:

Many respondents believe they have a moderate risk of getting sick with H1N1 if they don't get vaccinated. Fewer respondents believe they have a high risk, while some believe they have a low risk or are not sure.

## Bivariate analysis for h1n1_concern', 'h1n1_knowledge', 'behavioral_antiviral_meds', 'health_insurance', 'opinion_h1n1_risk'


## Bivariate analysis for Age Group, Education, Income Poverty, Race and Sex
![](/images/age.png)

![](/images/agegroup.png)

![](/images/antiviral.png)

![](/images/agegroup.png)

## CORRELATION ANALYSIS

![](/images/contingency.png)

H1N1 Vaccine Correlations:

Doctor recommendations (doctor_recc_h1n1) have the highest positive correlation with getting the H1N1 vaccine. This suggests that individuals are more likely to get vaccinated if recommended by a healthcare professional. Respondents' opinions on the risks and effectiveness of the H1N1 vaccine (opinion_h1n1_risk, opinion_h1n1_vacc_effective, and opinion_h1n1_sick_from_vacc) also show significant correlations.

Seasonal Vaccine Correlations:

The age group of the respondent (age_group) has a strong positive correlation with receiving the seasonal vaccine. Doctor recommendations for the seasonal flu vaccine (doctor_recc_seasonal) and opinions about its risk and effectiveness are also significantly correlated. Interestingly, the correlation of h1n1_vaccine with the seasonal vaccine is also evident, reinforcing our earlier observation that the two are not independent.
## MODELLING
## FIRST MODEL: LOGISTIC REGRESSION
The model performs relatively well for both vaccines, but there's room for improvement, especially in recall for h1n1_vaccine. The lower recall indicates that the model might be missing a significant portion of individuals who actually received the H1N1 vaccine. The results for seasonal_vaccine are more balanced, with both precision and recall being in the mid-70s. These metrics provide a comprehensive view of the model's performance.

![](/images/class%20imbalance.png)

## SECOND MODEL: LOGISTIC REGRESSION AFTER HANDLING CLASS IMBALANCE h1n1_vaccine
![](/images/logreg%20confusion.png)

![](/images/logreg%20roc.png)


The model's accuracy after applying SMOTE is slightly lower than the model trained on the original imbalanced dataset. However, the recall for Class 1 (Vaccinated) has seen a significant improvement (from 43% in the original model to 72% in the SMOTE model). This improved recall indicates that the model is better at identifying individuals who actually received the H1N1 vaccine.

There is a trade-off in precision for Class 1, which has decreased to 49%. This means that the model now makes more false positive predictions (predicting someone received the vaccine when they didn't) in its attempt to capture more true positives (correctly predicting someone received the vaccine).

This illustrates the power of addressing class imbalance in datasets,

## THIRD MODEL: RANDOM FOREST CLASSIFIER

![](/images/rf%20confusion.png)

![](/images/rf%20roc.png)


The model's accuracy for the h1n1_vaccine target is quite high at 83.86%. For predicting individuals who did not receive the H1N1 vaccine (Class 0), the model performs exceptionally well with a high precision, recall, and F1-score. For predicting individuals who received the H1N1 vaccine (Class 1), while the precision is decent, the recall is relatively low, indicating that there are a significant number of false negatives (individuals who received the vaccine but were predicted as not receiving it). This is evident from the F1-score of 53% for Class 1, indicating that there's a balance to be achieved between precision and recall for this class.

## Final Model (Gradient Booster Classifier)
![](/images/gb%20confusion.png)

![](/images/gb%20roc.png)


For H1N1 Flu predictions, the model performs relatively well with an accuracy of 84%. It performs better at identifying true negatives than true positives.

For Seasonal Flu, the model has a lower overall accuracy of 63%. The model is very good at identifying negatives (high recall for class 0) but struggles significantly with identifying true positives (low recall for class 1).

In both cases, the model seems to be more biased towards predicting the negative class (either for H1N1 or Seasonal Flu), as indicated by the higher recall for class 0 in both models
## RESULTS AND CONCLUSIONS
### Predict probabilities and plot their distribution
![](/images//probabilities.png)

![](/images/comparison.png)

H1N1 Flu:

Overall: For predicting h1n1_vaccine, all three models offer competitive performance, with slight variations in precision, recall, and F1-score.

For predicting seasonal_vaccine, while Gradient Boosting offers the highest precision, its recall is significantly lower than that of Logistic Regression and Random Forest, leading to a much lower F1-score and overall accuracy.

## RECOMMENDATIONS
### Public Awareness and Education:
H1N1 Concern & Knowledge: Since a significant number of respondents have moderate to high concern and knowledge about H1N1, it suggests that public awareness campaigns have been somewhat effective. However, there's still room for improvement. Campaigns should be tailored to:Address the concerns of those at moderate and high levels to ensure they have accurate information.
Target the groups with low or no concern and knowledge to raise awareness and understanding.

Education Level: Vaccination rates are higher among those with higher education. Efforts should be made to target awareness campaigns to those with lower educational levels, possibly using easily accessible and understandable formats.

Income and Poverty: There's a need for targeted campaigns in areas with higher poverty rates, possibly combined with subsidies or free vaccination programs to encourage higher vaccination rates among this demographic.

### Health Infrastructure and Support:**

Health Insurance: A significant number of respondents do not have health insurance. Policymakers should consider expanding access to affordable health insurance, which could indirectly improve vaccination rates and general health outcomes.

### Targeted Interventions:

Race: There's a notable disparity in vaccination rates among racial groups. Targeted interventions and campaigns should be developed to address the specific concerns and barriers faced by the racial groups with lower vaccination rates.
Sex: While the difference is slight, efforts can be made to ensure that both males and females have equal access to information and vaccination opportunities.

### Model Recommendations for Predictive Analytics:
H1N1 Flu Predictions: Given that all three models (Random Forest, Gradient Boosting, and Logistic Regression) have competitive performance, it might be useful to consider an ensemble approach, leveraging the strengths of each model.
Seasonal Flu Predictions: Given the significantly lower recall of Gradient Boosting, it might not be the best choice for predicting seasonal_vaccine, especially if identifying actual positive cases is crucial. Logistic Regression seems to be a balanced choice for this task.
