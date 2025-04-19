# Data Handling and Analytics - Part II


- Data Analytics is the process of examining data sets in order to draw conculsions about the info they contain,with the aid of specialized system and software.
- used  to make more informed business decision 
- used by scientists and researchers to verify or disprove the scientific models,theories and hypotheses.
- ex: admin's guide to AWS data management 
- types: Qualitative Analysis(categorical in nature) and Quantitative Analysis(process by which numerical data is analysed)

> Qualitative Analysis(data is observed)

- Not described through numerical values 
- described by some sort of descriptive context such as text 
- data gathered by interviews,videos,audio,field notes,recordings ,etc..
- data interpreted
- grouping of data into identifiable themes 
- Three principles(seidel,1998): Notice things,collect things,think about things 
- ex: color,smell
> Quantitative Analysis(data is measured)

- involves descriptive statistic such as mean,median,standard deviation 
- Ex:Statistical models,Analysis of variance,Data dispersion,Analysis of relationships between variables,Contingence and correlation,Regression analysis,Statistical significance,Precision,Error limits
- ex: volume,weight

> Advantage of Data Analytics

- Allows for the identification of important (and often mission‐critical) trends
- Helps businesses identify performance problems that require some sort of action
- Can be viewed in a visual manner, which leads to faster and better decisions
- Better awareness regarding the habits of potential customers
- It can provide a company with an edge over their competitors

## Statistical Models

- The statistical model is defined as the mathematical equation that are formulated in the form of relationships between variables.
- A statistical model is represented as the ordered pair (X:set of possible observation  , P: set of probability distributions on X)
- types : Complete(no of var= no of eq),incomplete models(no of var != no of eq)

> steps to build a statistical model 

- Data Gathering
- Descriptive Methods
- Thinking about Predictors
- Building of model
- Interpreting the result 

## Analysis of Variance (ANOVA)

- Analysis of Variance (ANOVA) is a parametric statistical technique used to compare
datasets
- ANOVA is best applied where more than 2 populations or samples are meant to be
compared.
>  When to Use ANOVA?
  
- A continuous dependent variable (e.g., test score, sales, height)
- At least one categorical independent variable (e.g., gender, city, ad type)
- The groups have 2 or more levels (e.g., Male/Female, or Location 1, 2, 3)
- Independence of Cases-	Observations in each group should be independent (e.g., different people, different locations).
- Normality-	Data in each group should be approximately normally distributed.
- Homogeneity of Variance- Each group should have equal variance (spread). You can't compare a wealthy city with a poor slum directly.

> Types of ANOVA
 
- One-Way ANOVA - One independent factor with multiple levels	Comparing average sales in 3 cities
- Two-Way ANOVA	- Two factors (e.g., gender and ad type)	Measuring weight loss by diet and exercise type
- K-Way ANOVA - 	More than two factors involved	Studying impact of age, location, and ad type on product purchase

> ANOVA Measuring Techniques 

- Total Sum of Squares (TSS or SST)
  - Measures total variability in the dataset.
  - Example: If you’re analyzing test scores across schools, TSS represents the total spread of scores around the overall mean.
-  F-ratio
  - compares variance between groups to variance within groups.
  - ≈ 1.0	No significant difference (null hypothesis likely true)
  - > 1.0	Groups differ significantly (null hypothesis likely false)
- Degrees of Freedom (df)
  - Reflects how many values are free to vary when calculating statistics.

## Data Dispersion

- A measure of statistical dispersion is a nonnegative real number that is zero if all the data are the same and increases as the data becomes more diverse.

> Dispersion measures 

- Range
  - The range is calculated by simply taking the difference between the maximum and minimum values in the data set.
- Average absolute deviation
  - The average absolute deviation (or mean absolute deviation) of a data set is the average of the absolute deviations from the mean.
- Variance
  - Variance is the expectation of the squared deviation of a random variable from its mean
- Standard deviation
  - Standard deviation (SD) is a measure that is used to quantify the amount of variation or dispersion of a set of data values

## Contingence and correlation

> Contingence Table 

- A contingency table (also called a cross tabulation or crosstab) is a table used in statistics to show the relationship between two categorical variables.
ex: 
Device Type	   Satisfied	  Not Satisfied	   Total
Mobile 	           80	         20	           100
Desktop	           60	         40	           100
Total	             140	       60	           200

> correlation 

- Correlation is a technique for investigating the relationship between two quantitative, continuous variables.
- Pearson's correlation coefficient (r) is a measure of the strength of the association between the two variables 

## Regression Analysis

- In statistical modeling, regression analysis is a statistical process for estimating the
relationships among variables
- The estimation target is a function of the independent variables called the regression function
- Characterize the variation of the dependent variable around the regression function which can be described by a probability distribution
- Regression analysis is widely used for prediction and forecasting, where its use has substantial overlap with the field of machine learning
- Regression analysis is also used to understand which among the independent variables are related to the dependent variable 

## statistical Significance 

- Statistical significance tells us whether a result is likely due to a real effect or just random chance.
- Baseline - The control group (what you compare your change against)

> Important Factors 

- Sample size - A large sample makes your test more reliable and less noisy.
- Effect size - Measures how big the change is.A small effect size may require a larger sample to be detected as significant.


## Precision andd error limits

> precison

- Precision refers to how close estimates from different samples are to each other
- The standard error is a measure of precision 
- Precision is inversely related  to standard error 

> Error Limits 

- Error limits define how much uncertainty we accept in our results due to: sampling and non sampling error (like data entry mistakes, survey bias, etc.)

- margin of error -It's the range above and below a statistic (like the mean or percentage) that we're confident the true value lies within.
- Limit of Error=Critical Value×Standard Deviation of the Statistic
- Critical Value (Z or t)	Based on confidence level (e.g., 1.96 for 95% confidence

# Case Study: Agriculture

- Ex: Soil moisture and water level monitoring, Automated irigation system ,automation in Recycling of Organic Waste and Vermicomposting ,Automate sowing and weeding system

##  smart water management using IOT (AgriSens)

> Proposed architecture 

- sensing and actuating layer(sensors and actuators and cluster node and sensor node ) 
- processing,storage and service layer(repository data server,web server,multi users server)
- application layer(farmers and persons with smart phones)

> Remote Server layer

- Repository data server: Communicates with the deployed IoT gateway in the field by using GPRS technology
- Web server: To access field data remotely
- Multi users server: Sends field information to farmer’s cell using SMS technology and also executes farmer’s query and controlling messages

> challenges 

-Noises: Air flow,Temperature, Solar radiation,Rain

# Case Study : Healthcare

- Automation reduces error
- lowers cost of healthcare 

> Components of IOT Healthcare 

- Sensing layer: Consists of all sensor, RFIDs and wireless sensor networks (WSN). E.g: Google glass, Fitbit tracker
- Aggregated layer: Consists of different types of aggregators based on the sensors of sensing layer. E.g: Smartphones, Tablets
- Processing layer: It consists of servers for processing information coming from aggregated layer.
- Cloud platform: All processed data are uploaded in cloud platform, which can be accessed by large no. of users

## Use- case of healthcare system using IOT (Ambusens)

> Problems and Solutions

- Problem: Physical presence necessary
  - solution:wireless sensors
- Problem: Not equipped to deal with complication 
  - Solution: instant remote monitoring
- Problem : Lck of collaboration
  - Solution:Real-time monitoring 
- Problem: Inconsistent physical records
  - Solution:cloud based digital keeping system 


- ambusens Physiological Parameters: HEart rate,ECG,Temp,GSR(galvanic skin response)

>Ambusens Development of WBAN (wireless body area network)

- communication protocol used bluetooth IEEE 802.15.1
- Power management and data rate tuning 
- calibration of data
- filtering and noise removal

> Ambusens : web interfaces 

- doctor portals 
- allows sensors  initialization and data streaming 

# Activity Monitoring - Part -I

- wearable sensors are popular 
- utilization of sensors of handheld devices 
  - accelerometer
  - gyroscope
  - GPS
  -others

- types of sensors: camera,smart phone,activity tracker band 

