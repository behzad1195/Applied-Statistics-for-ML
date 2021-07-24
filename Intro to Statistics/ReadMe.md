### Two Main Branches of Statistics in ML
    - Descriptive Statistics: provides information that describes our data in some manner e.g. mean, median, distribution, etc. There are lots of visualization techniques involved in descriptive statistics e.g. Histogram, bar chart, scatter plot, etc.
    - Inferential Statistics: The main focus of inferential statistics is to find the charechteristics of populatioin based on our samples. Additionally test hypotheses about the data using various techniques such as z-test, t-test, p-value to name just a few.

### Data Types:
    - Quantitative (numerical): Descrete -> can't be divided to smaller pices (1, 2, 3 ,4) and continues (1, 1.1, 1.11, 1.111) 
    - Categorical (qualitative): Nomial -> Non-numeric without any order (Gender), Ordinal -> Non-numeric but with order (educational degree)

### Measurment Scale:
    - Nominal: Use for labeling variables without any quantitative value (also known as labels) ->  Gender and Race
    - Ordinal: The order of values is important, however the difference between values are not really known -> Eduction or Income level
    - Interval: are variables that we know their orders and their exact differences. Interval scales are very useful because we can use them in almost any statistical methods   -> SAT and Credit Scores 
    - Ratio: they tell us about the order and exact values between units, additionally they have absolute zero which allow us to use wide range of descriptive and inferential statistical methods to be applied -> Weight and Length

### Population Vs. Sample
    - Sample : is only a part (usually small) part of population. In ML almost all the data that we used are samples. The most famous sample examples in ML are -> Train/Test Datasets and Performance Scores
    - Important Note: Because in ML we always deal with samples, it means there are always some uncertainty involved in our understanding about the whole population and hence is very important to report these uncertainty with measurments such as model accuracy, MSE, Confusion Matrix and etc. 

### Guassian (normal, bell shape) Distribution:
    - A distribution of data refers to the shape it has when you graph it, such as with a histogram or box plot. The most well-known type of distributions for continuous values is bell curve -> people's hight and body tempruter 
    - For more notes and python codes -> Applied Stats in Python - Normal Distribution.ipynb

### Central Tendency:
    - A measure of central tendency is a summary statistics that represents the center point or typical value of a dataset. These measures indicate where most of our values fall and also refers to a central location of a distribution. you can think of it as a tendency of data to be close to the middle value. 
    - Three core measures of central tendency: mean, median and the mode 
    - For codes looks at -> Applied Stats in Python - Measures of Central Tendency.ipynb

### Measure of Variability:
    - it measure the spread of data within an existing range of observations. The most popular measures are range, IQR(interquartile range), variance and standard deviation. 
    - STD is very important measure because together with the mean can tell us what shape of distribution we are looking at.   
    - For codes looks at -> Applied Statistics - Variation.ipynb

### Randomness in Machine Learning:
    - In order to understand the need for statistical methods in machine learning, you must understand the source of randomness in machine learning. 
    - The source of randomness in machine learning is a mathematical trick called a pseudorandom number generator. 
    - There are many source of randomness in applied machine learning space. Randomness is use as a tool to help learning algorithms to be more rebust and ultimatly results in a better predictions and more acurate models.  

#### Randomness in Machine Learning:
    - Randomness in Data: the noises in our sample train data (mistakes(duplicates), errors(outlier), and any types of data that prevent us to see the crystal clear relation between our variables) 
    - Randomness in Evaluation: As we don't havee access to all observations(population) in our domain, we harness randomness from evaluating our model such as Kfold Cross Validation to see the acuuracy of model in a different sets of our sample
    - randomness in Algorithms:  ML algorithms also use randomness when learning from the sample of data. This is a feature where the randomness allow the algorithm to achieve better performing mapping of the data compare to the absence of randomness. Algorithms that use randomness often called as stochastic algorithms rather than just algorithms. This is because when randomness is being used the resulting model is limited to more narrow range.
    - Some example of using randomness in algorithms are:
        - The shuffling of training data prior to each training epoch in stochastic gradient descent. 
        - The random subset of input features chosen for split points in a Random Forest algorithm.
        - The random initial weights in an artificial neural network.  
    - For codes in python standard library looks at -> Applied Statistics - Randomness with Python.ipynb  
    - For codes in Numpy library looks at -> Applied Statistics - Randomness with Numpy.ipynb 

### When to Seed  
    - There are times in a project when you want to seeding the random number generator, here we look at two common cases 
        - Data Prepration: It may use randomness such as shuffle the data or selection of values. data prepration must be consistent so the data is always prepared in a same way during fitting, evaluation and making prediction with the final model.
        - Data Splits: Train/Test split and Kfold Cross-Validation must be made consistently to ensure that each algorithm is trained and evaluated in a same way and on the same sub-sample of data. you may wish to see a pesudorandom number generatoer(random seed) one before each task or before performing a bach of tasks. It doesn't matter which number you choose for your seed.    
    

### Controlling for Randomness:   
    - Yet a stochastic ML algorithm will learn slightly differently each time it is run on the same data. This will result in a model with slightly different performance each time is trained. As you've learned you can fit the model to the same sequence of random number each time however once calculating the model this is a bad practice as it's high inherent uncertainty within the model -> A better approach is to evaluate the algorithm so that the reported performance includes the measured uncertainty in the performance of the algorithm. You can do that by repeating the evaluation of the algorithm multiple times with the different sequence of numbers (different seeds). It could be seeded once in the beginning of the calculation or it can be seeded differently at the beginning of each evaluation. 
    - There are two core aspects regarding the uncertainty to be considered here.
        - Data Uncertainty: Evaluating the model with the different split of data gives you insight about how the algorithm performance varies with the changes in train/test data
        - Algorithm Uncertainty: Evaluating an algorithm multiple time on the same split of data will provide you with the insight about how the algorithm performance varies alone. 
    - As a general rule it would be better if we report the performance for each source of uncertianty combined.

### Law of Large Numbers:
    - The Law of Large Numbers states that as we increase the number of observations of the random process, the proportion of observing a particular outcome converges to probability of that particular outcome -> This is the reason why in ML we say the larger the data better the results.
    - Hence as much as the size of our sample increases the mean of our sample would be closer to the population mean.

### Central Limit Theory: 
    - The Central Limit Theory says that as the size of the sample increases, the distribution of the mean across multiple samples will approximate a Gaussian distribution.
    - For understanding the central limit theory and it's distinction with the Law of Large number let's assume role a die, in this case the chance of each number between 1 to 6 is equal to 1/6 hence we will have a unified distribution, now when we have 2 dice the probability is not equal anymore beacuse for instance the chance of rolling both dice with sum of 1 is zero and 2 is 1/36 but sum of 3 is 3/36 and 4 is 4/36 and so on and so forth, if we add the third die the probability will change even more. Hence by addine more dice the probablity distribution become closer and closer to a normal distribution.
    - For codes looks at -> Applied Statistics - Central Limit Theory.ipynb 

    



 