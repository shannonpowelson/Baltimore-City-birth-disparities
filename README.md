# Baltimore City Birth Weight Disparities

## Background
For this analysis, we study disparities in birth weights with respect to variables like household poverty, race, domestic violence, and prenatal care.  According to the article, [Why America’s Black Mothers and Babies Are in a Life-or-Death Crisis](https://www.nytimes.com/2018/04/11/magazine/black-mothers-babies-death-maternal-mortality.html) by Linda Villarosa, “black infants are more than twice as likely to die as white infants”.  This is a huge problem that needs to be solved, so we decided to dig a little deeper to explore the variables playing a role in this disparity, specifically in Baltimore City.  Low birth weight is a main [cause](https://www.ncbi.nlm.nih.gov/books/NBK214473/#:~:text=Low%20birthweight%20is%20a%20major,of%202%2C500%20grams%20or%20less) of infant death.  [Stress](https://www.nature.com/articles/1601526) can cause this low birth rate.  Chronic stress creates health conditions like [hypertension and preeclampsia](https://www.nytimes.com/2018/04/11/magazine/black-mothers-babies-death-maternal-mortality.html) which can lead to babies being born with low birth weights.  Higher death rates in black infants [can be attributed to weathering](https://www.nytimes.com/2018/04/11/magazine/black-mothers-babies-death-maternal-mortality.html), a phenomenon frequently experienced by black women in the United States.  [Weathering](https://www.self.com/story/weathering-and-its-deadly-effect-on-black-mothers) is when racism, both societal and systematic, produces chronic stress in the body.  Therefore, we apply this research to Baltimore City by exploring how satisfactory birth weights are distributed through a series of analyses.  Since we do not have quantitative weathering or racism data, we use household poverty and domestic violence as metrics to measure stress.  Prenatal care has been shown to help pregnant mothers deliver healthy babies, so this metric is also investigated.  Identifying groupings and associations between these variables are essential for advocating for policies that will help to decrease the black infant death rate. 

## Business Question
_Are there birth weight disparities in Baltimore City??_

## Data Question
_How are birth weights distributed in Baltimore City based on race, household poverty, domestic violence, and prenatal care?_

## Data Sources   
All data from this analysis comes from the [Baltimore Open Data Hub](https://data.baltimorecity.gov/). Community statistical areas were used as indices to compile data. Relevant data files are as follows:

### Individual Datasets
- [% of Babies Born at Satisfactory Birth Weight](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Percent_of_Babies_Born_with_a_Satisfactory_Birth_Weight.xlsx)
- [Family Household Poverty Rate](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Percent_of_Family_Households_Living_Below_the_Poverty_Line.csv)
- [Racial Diversity Index](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Racial_Diversity_Index.csv)
- [% of population identifying as white](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Percent_of_Residents_-_White_Caucasian_(Non-Hispanic).csv)
- [% of population identifying as black](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Percent_of_Residents_-_Black_African-American_(Non-Hispanic).csv)
- [% of population identifying as hispanic](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Percent_of_Residents_-_Hispanic.csv)
- [Property crime rate](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Property_Crime_Rate_per_1%252C000_Residents.csv)
- [Violent crime rate](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Violent_Crime_Rate_per_1%252C000_Residents.csv)
- [Domestic violence rate](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Domestic_Violence_Calls_For_Service_per_1%252C000_Residents.csv)

### Compiled Datasets

A full explanation of methods can be found [here](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/data-analysis-workflow.md).

## Data Analysis
Since infant mortality could be caused by a wide range of issues, we first wanted to understand the relationship between infant mortality and percent of babies born below satisfacotry birth weight (SBW) using the scatterplot below. 

![a;t text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Birthweigth_InfantMortality.png)

This plot confirms a trend between the two variables where the R-squared value indicates 17.6% of the variance in infant mortality can be explained by SBW. This confirms our assumption that infant mortality is not the best metric for baby outcomes. We therefore attempt to identify factors influencing SBW going forward.

To identify metrics which contribute to SBW, we performed multiple linear regression using the percentage of births with prenatal care, household poverty rate, racial diversity index, property crime, violent crime, domestic violence, and percent of the population identifying as black/African American as the independent variables. Rationale for selecting these metrics came from issues raised in the [article](https://www.nytimes.com/2018/04/11/magazine/black-mothers-babies-death-maternal-mortality.html) as well as reasoning that crime/violence will contribute to maternal stress, negatively impacting the fetus.

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/MLR_all_variables.png)

For this regression, the only variables returned as being significant (p<0.05) were domestic violence and percent black/African American population. We reasoned that this may be due to the fact that several of these metrics are confounding and interrelated. We therefore looked at each metric using single linear regression using total life expectancy, infant mortality, and SWB as indepdnent variables.

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Simple_linear_for_three_outcomes.png)

The table above shows R-squared values between the indicated variables. Conditional formatting was used to identify moderate relationships (green), mild to moderate relationships (yellow) and no relationship (red). Based on this anaysis, SWB is at least mildly to moderately associated with prenatal care, poverty, domestic violence and percent black/African American. Since these variables do not show the same relationship with infant mortality, we use these variables for the remaining analyses.

To better understand how Baltimore communities fit into our vairalbes, we performed a three cluster analysis. The variables assessed were SWB, prenatal care, poverty rate, domestic violence, and the percentage of the three largest race populations: white, black/African American, and hispanic.

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/full_cluster_analysis.png)

The clusters produced were notably delineated by race, as indicated above the bars in the plot. From this, we draw broad conclusions for each race. White populations have a high SWB and prenatal care but low incidence of poverty and domestic violence. On the other hand, black populations have a low SWB and prenatal care with higher domesitc violence and poverty. Interestingly, hispanic populations has a reasonable SWB despite low prenatal care and higher poverty and domestic violence. It is worth noting that individuals identifying as hispanic can also fall into white or black popoulations. These results demonstrate clear disparities between white and black populations. Further, the positive outcomes for hispanic communities despite poorer social conditions indicates there are additional factors contributing to negative SBW outcomes for black communities.

We next wanted to dive deeper into each individual variable to explore why this birth weight disparity exists.

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Poverty_Birthweight.png)

This plot shows the relationship between poverty and SBW with points colored by cluster. There is a moderate correlation between these indicated by the R-squared value of 0.368. It is also apparent that clusters represent relatively distinct populations.

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Poverty_Birthweight.png)

This plot shows the relationship between domestic violence rates and SBW with points colored by cluster. There is a moderate correlation between these indicated by the R-squared value of 0.307. While the points belonging to respective clusters are a bit more dispersed for this plot, there are still noteable boundaries. Both plots indicate that outcomes for primarily black/African American communities are somewhat predictable and in the disfavorable range. To better understand the white/black divide (the two major racial demographics in Baltimore), we colored the poverty vs SBW plot by racial community majority using [Infogram](https://infogram.com/).

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Scatter_Plot_povertyandweight.png)

It appears in this graph that for both the predominantly black and white communities, percent of babies born with a satisfactory birth weight is higher when the household poverty rate is lower. There is also a moderately clear deliniation between the two populations on this plot, though these clusters were not by calculation. This lead us to ask if this relationship is more related to prenatal care or stress from living in poverty.

To get at this question, we created a bubble plot using [Infogram](https://infogram.com/) to explore prenatal care, poverty, and birth weight simultaneously. In this plot, bubble size increase is proportional to increase in poverty rate.

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Bubble_Plot.png)

Overall, whether or not prenatal care is obtained is less observed in impoverished areas. It appears that the percent of babies born with a satisfactory birth weight is increasing with prenatal care for white neighborhoods.  However, this outcome is not observed for black/African American communities where the associate appears more flat. To investigate this further, we analyzed white and black neighborhoods in individual single linear regressions as shown below.

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Weight_Prenatalcare_BlackCommunities.png)

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Weight_Prenatalcare_WhiteCommunities.png)

Based on the R-squared values, we can see that for white communities, 42% of the data fits the linear regression model.  However, for black communities, 6.8% of the data fits the linear regression model.  Therefore, we are more certain of a positive association between prenatal care and percent of babies born with a satisfactory birth weight for white neighborhoods than we are for black neighborhoods.

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Clusters_with_Percent_Black.png)

One final analysis we took was geographic, matching clustering of communities to their locations on the Baltimore map. These clusters take into account black/African American communities instead of all proportions, though a similar outcome is observed for the combined clusters. This model bears striking resemblance to the plot observed soley for race found in the article describing the ["black butterfly'](https://apps.urban.org/features/baltimore-investment-flows/). This indicates that outcomes for SBW follow trends in race and that racial inequalities may be the largest factor predictive of SBW.

Probably use this in the summary - the reason for this difference could be due to systematic racism in healthcare - prenatal care might work for white mothers, but not for black mothers due to racism - that is why other forms of prenatal care - like doulas - need to be available for black mothers

## Summary 
Our analyses reveal several key relationships and takeaways for SBW. First, Baltimore can be clustered based on birthweight, poverty, domestic violence and race, and this clustering mimics simple plots based on race. Second, black/African American communities are disproportionately experiencing negative SBW outcomes, despite having similar trends in community standards to Hispanic populations. This suggests that other factors, specific to black/African American communities, contribute to troubles with healthy childbirth. Finally, efforts to mitigate low SBW rates, like prenatal care, are more successful in primarily white communities than in black/African American communities. This points to a necessity to create mitigation efforts which are designed specifically for individual races.

Our data indicate that outcomes reported for other black/African American [populations](https://www.nytimes.com/2018/04/11/magazine/black-mothers-babies-death-maternal-mortality.html) are the similar in Baltimore. However, our data confirm that negative factors like poverty, domestic violence, and lack of prenatal care are not the sole predictors of SBW outcomes for black/African American babies. Indeed, it is highly likely that [weathering](https://www.self.com/story/weathering-and-its-deadly-effect-on-black-mothers) plays a significant role. For example, the [story](https://www.nytimes.com/2018/04/11/magazine/black-mothers-babies-death-maternal-mortality.html) of Simone Landrum demonstrates that even when care is proactively sought, it is unsatisfactory and can lead to the death of both the child and the mother. This means that specialized strategies are needed to improve SBW for black/African American communities. One potential route is to make prenatal care which includes support of a [doula](https://www.dona.org/what-is-a-doula/benefits-of-a-doula/) readily available to these communities. Making such care available would help black/African American mothers manage stress and improve SBW statistics. Not only would this have the immediate benefit to the babies, but the long term effects will be equally beneficial, as underweight babies are more prone to develop [mood and anxiety disorders](https://womensmentalhealth.org/posts/maternal-stress-and-low-birth-weight-predict-later-risk-for-mood-and-anxiety-disorders/#:~:text=In%20response%20to%20stress%2C%20blood,result%20in%20lower%20birth%20weight.). These efforts, in addition to initiatives to reduce poverty and crime, will turn the tides for the black/African American community and bring us one step closer to eliminating racial disparities in Baltimore.



