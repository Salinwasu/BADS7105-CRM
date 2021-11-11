# A/B Testing
What is [A/B Testing](https://hbr.org/2017/06/a-refresher-on-ab-testing) ? 
> A/B testing, at its most basic, is a way to compare two versions of something to figure out which performs better.
# What we do in this class ?
> Objective : We want to know which pen color is better in our survey. 
* A/B testing for two version of pen.
  * Orange color
  * Blue color
* Collect data through Google Form with 5 variables to get ranking of pen color.
  * Gender
  * Age
  * Purpose of these pens
  * Orange pen color
  * Blue pen color
* Use T-Test to Analyst 
# What is T-Test 
> The paired sample t-test, sometimes called the dependent sample t-test, is a statistical procedure used to determine whether the mean difference between two sets of observations is zero. In a paired sample t-test, each subject or entity is measured twice, resulting in pairs of observations. Common applications of the paired sample t-test include case-control studies or repeated-measures designs. Suppose you are interested in evaluating the effectiveness of a company training program. One approach you might consider would be to measure the performance of a sample of employees before and after completing the program, and analyze the differences using a paired sample [t-test](https://www.statisticssolutions.com/free-resources/directory-of-statistical-analyses/paired-sample-t-test/).
# Data Visualization with [Tableau](https://public.tableau.com/app/profile/prant1075#!/)
> 50 people in total of survey
  * 38 Male
  * 12 Female 


 ![A:B Testing](https://user-images.githubusercontent.com/69904258/141298226-27db505f-044f-482d-9fe0-ea466c479ed8.png)
 
 # Paired T-Test in Excel
 
<img width="666" alt="Screen Shot 2564-11-11 at 19 37 59" src="https://user-images.githubusercontent.com/69904258/141299395-df0151ce-c1c1-42e6-8a48-a49418dfc906.png">

### Set Up
* u1 : The populaiton mean of Satisfaction score of Orange pen
* u2 : The populaiton mean of Satisfaction score of Blue pen

Confidence interval 95% (Alpha =0.05)
#### HYPOTHESIS
* H0 : u1 = u2
* H1 : u1 != u2

# Conclusion
* P-value  at two tail < 0.05, Reject Ho.Therefore,So,the populationf confidence interval mean of Satisfaction score of orange pen and blue are significantly different at 0.95 % of Confidence interval.
* Most of people prefer Blue pen color

## The Winner Is :

![1](https://user-images.githubusercontent.com/69904258/141300643-ecaeefcc-8d8e-4895-b0e5-533eed844304.jpg)
