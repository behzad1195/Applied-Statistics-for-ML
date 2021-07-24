### Intro
- Data alone is not interesting. Anytime we look at data we are trying to make a conclusion out of it. For instance when you looks at the education and income level you want to find out whether people with higher education earn higher income or not. In statistics we call it hypothesis testing in other words we want to test our assumption (hypothesis) by looking at the data that we have.
- Each time that we come up with one assumption as easy as the shape of our distribution or correlation we should test our assumption. This class of methods is called Statistical hypothesis testing, or significance tests. In statistics we test a hypothesis with looking at the quantitave value against the given data. The result of the test tell us whether our assumption is correct or not.

#### Two examples of hypothesis tests in ML
* Normal Distribution: make sure that our data follows the normal distribution or at least it's close to it -> That's the reason that we normalized/standardized our data before fitting it into the model. But if our data is not similar to normal distribution we should use power transform methods to make them normal.
* Same population: make sure that our samples are drawn from the same population 

#### The Null Hypothesis(H0)
* The assumption of statistical test is called the Null Hypothesis AKA H0 or defualt assumption.
* H1 AKA alternative hypothesis is the violation of H0, meaning that if we can't prove the H0 then H1 is correct.  

### Defining P-Value
- The result of a statistical hypothesis test must be interpreted for us to start making claims. There are two common forms that our results from the hypothesis can take and it must be interpreted in different ways. They are P-VALUE (the most common) and CRITICAL VALUE.
    - P-VALUE: This is a quantity that we can use to interpret or quantify the result of the test and either reject or fail to reject the H0. This is done by comparing P-VALUE with a given threshold or our significance level (it can be different from one project to another but the most common significance level is 95% or 0.95 followeed by 90% (0.9) and 99%(0.99)). Another way to explain is that for instance the probabilty of 99 heads in 100 flips is realtively small. The probability is called the P-VALUE.   

### Reject or Faill to Reject the H0
- Reject: rejecting the H0 is one of two possible outcome of a hypothesis test. The H0 states that there is no STATISTICALY SIGNIFICANT change. Rejecting the H0 means that you conclude that there IS a statistically significant change.  
- For exampple let's assume that a man want to propose to a women, and the women says that I reject the HO this means the she actually accepted his propose. Because before asking they were only friend yet after accepting they become engaged which is a big change -> There is a STATISTICALY SIGNIFICANT change in their relationship and hence rejecting the H0. 
- But if she says No then she failed to reject H0 which means that there is no STATISTICALY SIGNIFICANT change in their relationship and they remain friends which in my humble opinion in any case (yes or no) there would be a huge change in their relationship 😉. But you get what these statisticians mean by this example.

### Errors in Hypothesis Testing:
- In general there are two types of error in hypothesis testing namely, "Type I errors" and "Type II errors".
    - Type I errors: It's when you reject a True H0 -> False Positive (most serious error also known as alpha -> because the responsibility of choosing alpha is on you) -> in ML Type I error is same with PRECISION
    - Type II erros: It's when you accept (fail to reject) a False H0 -> False Negative (smaller probelm because it's not your fault. However if you chose your alpha wrong then it's somehow your problem as well but at job most of the time they tell you which kind of significance level they are looking for). -> in ML Type II error is same with RECALL
    - A kind of similar example is that assume a boy assumption is that a girl likes him but he's not sure whether to ask her out or not. So the H0 is that She likes him back. If the Truth is also that She likes HIM back then if he doesn't ask her out then it's Type I error (reject the True H0, False Positive). But if she doesn't like Him back and he asks her anyway then it's Type II error (Fail to reject(accept) the H0, False Negative).

### Statistical Distributions:
- Any sample of data has a form of distribution and as you know by now the most common one is the normal(Guassian) distribution. This distribution describe the groupping or density of observation which is called Probability Density Function(PDF). You can think of a distribution as a function that describes the relationship between observations and sample space. For example you may be interested in the age of humans with the individual age as observations in a domain and a age between 0 and 115 represeant a sample space. A DISTRIBUTION is a mathematical function that shows the realtionship between observations (individuall ages) and sample space (0 to 115). The mean, median, mode, Variance, STD, and etc. are all among the types of relationship you can find within a distribution. 
- A DISTRIBUTION is simply a collection of data, or scores, on a variable. Usually these scores are arranged in order from smallest to largest and then they can be presented graphically.

### Density Function
- it describes how the proportion of data change over the range of the distribution. There are two types of density function PDF and CDF (cumulative density function)
    - PDF: calculates the probabilty of observing a given value. It can be also used to summarize the likelihood of observations across the distribution of the sample space. Plots of PDF gives us normal distribution (in most cases) shape 
    - CDF: calculates the probabilty of an observation equal or less than a value. CDF gives back the probability of a observation and all observations below it together hence the cumulative probability. CDF plotted as a curve between 0 and 1 from the min to the max value of observations.
    - For more notes and python codes -> Applied Statsitics - Probability Density Functions.ipynb

### Student's T-Distribution:
- FUN Fact: The T-distributions were discovered by William S. Gosset in 1908. Gosset was a statistician employed by the Guinness brewing company which had stipulated that he not publish under his own name. He therefore wrote under the pen name 'Student'. http://statweb.stanford.edu/~naras/jsm/TDensity/TDensity.html#:~:text=The%20t%20distributions%20were%20discovered,publish%20under%20his%20own%20name.
- He devloped a way to extract small samples but still produce meaningful predictions. 
- A key difference between T- and normal-distribution is that the T-distribution has the fatter tails in the distribution, highleighting the increased likelihood of observations in the tails compared to that of the normal. As larger the size of sample closer would be its shape to the normal distribution. In fact any sample with larger than 30 degree of freedom (number of observations in a sample - 1) is considered as a normal distribution.  
- Although you may not use the T-distribution directly, you may estimate values from the distribution required as parameters in other statistical methods such as statistical significance test.
- The key to using the T-Distribution is knowing the number of degrees of freedom. The number of degrees of freedom describes the number of pieces of information used to describe a population quantity. For example the mean has n degrees of freedom as all observation in sample are used to calculate the estimatation of the population mean. However a statistical method that is being used in another statistical method must be subtracted by one -> hence degrees of freedom = n-1. 

### Chi-Squared (read as Kai-squared) Distribution:
- Chi-squared distribution is used for GOODNESS OF FIT of an observed distribution Vs. a theoritical distribution. It also used in statistical methods that are drawn from a normal distribution to quantify the 'Unceratinty'. For example it's used to find the statistical test for independence (opposite to multicolinarity). In fact it's used to derivation of Student T-Distribution. It has only one parameter and that is the degree of freedom. Where Chi is an observation that has Chi-squared distribution.    
- For more notes and python codes -> Applied Statsitics - Chi-Squared Distribution.ipynb 

### Critical Values:
- Not all implementation of statistical tests return P-Values. In some cases, you must se alternatives, such as CRITICAL VALUES. In addition the Critical Values are used when estimating the expected intervals for observations of our population such as tolerance intervals.
- The main methods for calculating Statistical Hypothesis Tests are Z-TEST, STUDENT'S T-TEST, CHI-SQUARED, and ANOVA.
- Critical value is a value which helps you to decide whether you are going to ACCEPT (fail to reject) or REJECT your H0. This value changes as we change level of confidence (alpha in p-value). For using the critical value we should satisfy three assumptions.
1. used in hypothesis testing
2. assumes a normal distribution
3. there is a pre-defined rejection and acception region
4. the line seprating above regions is critical value
- Steps for using Critical Value methos:
    - step 1: Find the critical value(defined by a person with the domain knowledge or the problem we are looking at, avg wage of data scientist in berlin assumed to be 50K).
    - step 2: Run Test (one of above tests to find out the sample mean of avg wage of data scientist in Berlin)
    - step 3: If your value (let's say the avg wage of data scientist in Berlin after running test would be 52K then you can reject the H0 of 50K).

### One-Tailed Vs. Two-tailed Test:
- When creating your data analysis plan or working on your results, you may have to decide if your statistical test should be a one-tailed test or a two-tailed test (also known as “directional” and “non-directional” tests respectively). 
- The tail refers to the end of the distribution of the test statistic for the particular analysis that you are conducting. For example, a t-test uses the t distribution, and an analysis of variance (ANOVA) uses the F distribution. Symmetrical distributions like the t and z distributions have two tails. Asymmetrical distributions like the F and chi-square distributions have only one tail. This means that analyses such as ANOVA and chi-square tests do not have a “one-tailed vs. two-tailed” option, because the distributions they are based on have only one tail.
    - Two-Tailed Test: A two-tailed test is appropriate if you want to determine if there is any difference between the groups you are comparing. For instance, if you want to see if Group A scored higher or lower than Group B, then you would want to use a two-tailed test. This is because a two-tailed test uses both the positive and negative tails of the distribution. In other words, it tests for the possibility of positive or negative differences.
    - One-Tailed Test: A one-tailed test is appropriate if you only want to determine if there is a difference between groups in a specific direction. So, if you are only interested in determining if Group A scored higher than Group B, and you are completely uninterested in possibility of Group A scoring lower than Group B, then you may want to use a one-tailed test. The main advantage of using a one-tailed test is that it has more statistical power than a two-tailed test at the same significance (alpha) level. In other words, your results are more likely to be significant for a one-tailed test if there truly is a difference between the groups in the direction that you have predicted. This is because only one tail of the distribution is used for the test.
- So, which kind of test should you use? When in doubt, it is almost always more appropriate to use a two-tailed test. A one-author davidtailed test is only justified if you have a specific prediction about the direction of the difference (e.g., Group A scoring higher than Group B), and you are completely uninterested in the possibility that the opposite outcome could be true (e.g., Group A scoring lower than Group B).
- For more notes and python codes -> Applied Statsitics - Calculating Critical Values.ipynb 

### Correlation:
- Correlation is essentially a measure of how closely two variables are related to each other. Higher the correlation, more closely the two variables are realted to each other.
- In ML correlation can tell us which independent variables can explain changes in dependent variables better as well as whether two independence variables are independence of each other or have multicolinarity. The latter could be used as a dimensional reduction technique in data prepration. 
- Three types of correlation: -> 0.7 to 1 (strong), 0.3 to 0.7 (moderate to weak) this numbers are the same for negative values. +/- 1 perfect, 0 no relationship
    - Positive: Both variables change in the same direction.
    - Neutral: No relationship in the change of variables.
    - Negative: Variableschange in opposite directionts
- For more notes and python codes -> Applied Statsitics - Strong Positive Correlation.ipynb 

#### Covariance:
- Variance measures how far our data is spread out. If variance is zero, it means that all the data points are same. This is why we may drop the feature with the very low variance in ML. Variance is the sum square of difference of values with the mean.
- Variables can be realted with a linear relationship. This is the relationship that is consistantly added across two data samples. This relationship can be summerized between two variables called COVARIANCE. If the dimension of our data is more than one, the mean and variance is not enough to visualize our data you need the orientation of the data as well. Covariance tells the orientation of those data points.
- As the interpretation of covaraince is hard and doesn't give us that much of information we usually use Pearson's R correlation instead of it.  
- For more notes and python codes -> Applied Statsitics - Calculate Covariance.ipynb  

#### Person's R correlation:
- The Pearson's correlation coefficient can be used to summarize the strength of the linear relationship between two data samples. It calculates as the covariance of two variables divided by the product of std of each sample. For instance there is a positive linear relationship between age and income which means by increasing the age we expect that the income goes up as well. This shows the positive strong correlation between age and income.
- For more notes and python codes -> Applied Statsitics - Pearson's R.ipynb 

#### Spearman Correlation:
- Pearson correlation evaluates the linear relationship between two continuous variables.
- Spearman correlation: Spearman correlation evaluates the monotonic relationship. The Spearman correlation coefficient is based on the ranked values for each variable rather than the raw data.

#### Kendall rank correlation coefficient:
- In statistics, the Kendall rank correlation coefficient, commonly referred to as Kendall's τ coefficient (after the Greek letter τ, tau), is a statistic used to measure the ordinal association between two measured quantities. A τ test is a non-parametric hypothesis test for statistical dependence based on the τ coefficient.
- Intuitively, the Kendall correlation between two variables will be high when observations have a similar (or identical for a correlation of 1) rank (i.e. relative position label of the observations within the variable: 1st, 2nd, 3rd, etc.) between the two variables, and low when observations have a dissimilar (or fully different for a correlation of −1) rank between the two variables.

#### More info and python code:
- For mathematical intuition for each method and their differences look here: https://datascience.stackexchange.com/questions/64260/pearson-vs-spearman-vs-kendall
- For coding in python look here: https://machinelearningmastery.com/how-to-calculate-nonparametric-rank-correlation-in-python/ 

### Parametric Statistical Tests
- Tests for statistical significance can be divided into two categories namely Parametric and Non-Parametric. 
- Parametric Tests: It is used mainly for data samples that have following criterias. Pearson's R correlation is an example of parametric test 
    * Normal Distribution (Mean and Median are the same)
    * Quantitative Data
    * Metric Scale
    * Very powerful and most common (because the majority of data follow a normal distribution)
    * For more notes and python codes -> Applied Statsitics - Parametric Tests Complete.ipynb  
- Non-Parametric Tests: It is used mainly for data samples that have following criterias. Spearman and Kendall rank correlation are examples of non-parametric test 
    * Skewed Distribution (Mean and Median are not the same)
    * Qulitative Data
    * Normal or ordinal scales
    * Less powerful and less common 

### Effect Size:
- Hypothesis tests do not comment on the size of the effect if the association or difference is statistically significant.
- Effect size methods refer to a suite of statistical tools for quantifying the size of an effect in the results of experiments that can be used to complete the resultsfrom statistical hypothesis tests. It is a way of describing in a normalized way the magnitude of the difference between two groups.
- Why they are important? It's a way to use the same measurement to show the importance of differences between one group and another group.
- There are two main group of methods for calculating Effect Size:
    - Association: quantifying an association between variables e.g. correlation
    - Difference: quantifying the difference between variables e.g. difference between the means
- The results of Effect Size should be interpreted and it depends on the specific statistical method used. A measure must be chosed according to the goal of interpretation. However there are three methods for calculating Effect Size.
    - Standardized Result: The effect sizes are in standard scale that allow us to be interpreted generally regardless of specific application.
    - Original Units Result: The effect size may use the original unit of the variable which can aim the interpretation within a domain e.g. difference in means.  
    - Unit Free Result: The effect size may not have a specific unit such as count of proportion e.g. correlation coefficient.

### Statistical Power:
- Statistical power, or the power of a hypothesis test is the probability that the test correctly rejects the null hypothesis. That is the probability of true positive and lower probabilty of Type II errors (false negative). However, statistical power has relevance only when the null is false. 
- Statistical power is simply the chance you wull be able to detect an effect if there really is one. There are two types of statistical power.
    - Low: Large risk of committing Type II error -> Experimental results with too low statistical power will lead to invalid conclusion about the meaning of results. Therefore you need a minimum level of Statistical Power. It is common to design a experiment with the statistical power of 80% or better (similar with model.score() in ML). This means that 20% of the probability of encounter is in TypeII area.  
    - High: Small risk of committing Type II error

### Power Analysis: The Core 4
- Statistical Power analysis is one piece of puzzle that has four related part.
    1. Effect Size: It quantifies the magnitude of result presented in the population such as Pearson Correlation Coefficient 
    2. Sample Size: Number of observations in a sample
    3. Significance: The significance level being used in our statistical tests (most common 0.05 or alpha = 0.05)
    4. Statistical Power: This is the probability of accepting H1 (alternative hypothesis) if it's true
- All above parameters are related to each other. For example larger sample size can make an effect (such as correlation) easier to detect, statistical power can be increased by increasing their significance level. 
- A power analysis involves estimating one of these four parameters given values for three other parameters. For instance statistical power can be calculated given the sample size, the effect size and the significance level. 
    - The most common practice in designing experiment is finding the minimum sample size. As a data scientist you can set the other three parameters by your own judgment together with the help of experts with the domain knwoledge (can be people from other departments e.g. sales, HR, Finance, etc.). As a practitioner, you can start with sensible defaults for some parameters, such as significance level of 0.05 and a power level of 0.80. 
    * For more notes and python codes -> Applied Statsitics - Student's t-Test Power Analysis.ipynb 
