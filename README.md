# Baltimore City Birth Weight Disparities

## Background
For this analysis, we study disparities in birth weights with respect to variables like household poverty, race, domestic violence, and prenatal care.  According to the article, [Why America’s Black Mothers and Babies Are in a Life-or-Death Crisis](https://www.nytimes.com/2018/04/11/magazine/black-mothers-babies-death-maternal-mortality.html) by Linda Villarosa, “black infants are more than twice as likely to die as white infants”.  This is a huge problem that needs to be solved, so we decided to dig a little deeper to explore the variables playing a role in this disparity, specifically in Baltimore City.  Low birth weight is a main [cause](https://www.ncbi.nlm.nih.gov/books/NBK214473/#:~:text=Low%20birthweight%20is%20a%20major,of%202%2C500%20grams%20or%20less) of infant death.  [Stress](https://www.nature.com/articles/1601526) can cause this low birth rate.  Chronic stress creates health conditions like [hypertension and preeclampsia](https://www.nytimes.com/2018/04/11/magazine/black-mothers-babies-death-maternal-mortality.html) which can lead to babies being born with low birth weights.  Higher death rates in black infants [can be attributed to weathering](https://www.nytimes.com/2018/04/11/magazine/black-mothers-babies-death-maternal-mortality.html), a phenomenon frequently experienced by black women in the United States.  [Weathering](https://www.self.com/story/weathering-and-its-deadly-effect-on-black-mothers) is when racism, both societal and systematic, produces chronic stress in the body.  Therefore, we apply this research to Baltimore City by exploring how satisfactory birth weights are distributed through a series of analyses.  Since we do not have quantitative weathering or racism data, we use household poverty and domestic violence as metrics to measure stress.  Prenatal care has been shown to help pregnant mothers deliver healthy babies, so this metric is also investigated.  Identifying groupings and associations between these variables are essential for advocating for policies that will help to decrease the black infant death rate. 

## Business Question
_Are there birth weight disparities in Baltimore City??_

## Data Question
_How are birth weights distributed in Baltimore City based on race, household poverty, domestic violence, and prenatal care?_

## Data Sources   


## Data Analysis


First use data analyses that show that a disparity does exist.  

Then wanted to dive deeper into each individual variable to explore why this birth weight disparity exists.  Looked to see how household poverty and birth weights are related as shown in this scatterplot below

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Scatter_Plot_povertyandweight.png)

It appears in this graph that for both the predominantly black and white communities, percent of babies born with a satisfactory birth weight is higher when the household poverty rate is lower.  This lead to the question, is this because people in poverty cannot afford prenatal care, or is it from the health conditions created by the chronic stress from living in poverty?

Made a bubble plot to explore prenatal care, poverty, and birth weight at the same time (the bubble size is the poverty rate - larger bubble = higher poverty)

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Bubble_Plot.png)

In this bubble plot, it appears that the percent of babies born with a satisfactory birth weight is increasing with prenatal care for white neighborhoods.  However, there does not appear to be an association for black neighborhoods.  

To investigate this further, did two linear regressions as shown below:

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Weight_Prenatalcare_BlackCommunities.png)

![alt text](https://github.com/shannonpowelson/Baltimore-City-birth-weight-disparities/blob/main/Weight_Prenatalcare_WhiteCommunities.png)

Based on the R-squared values, we can see that for white communities, 42% of the data fits the linear regression model.  However, for black communities, 6.8% of the data fits the linear regression model.  Therefore, we are more certain of a positive association between prenatal care and percent of babies born with a satisfactory birth weight for white neighborhoods than we are for black neighborhoods.  

Probably use this in the summary - the reason for this difference could be due to systematic racism in healthcare - prenatal care might work for white mothers, but not for black mothers due to racism - that is why other forms of prenatal care - like doulas - need to be available for black mothers

## Summary 




