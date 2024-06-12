# used-cars

A study on what features affects the price of a used car. This is part of the course work for [UC Berkeley Professional Certificate in Machine Learning and Artificial Intelligence](https://exec-ed.berkeley.edu/professional-certificate-in-machine-learning-and-artificial-intelligence/). 

You can follow the detailed analysis done in the [Jupyter notebook](https://github.com/cdungca/used-cars/blob/main/prompt_II.ipynb).

## Objective

The main objective of this study is to identify features which are considered valuable by used car buyers. What are these features that can drive the price higher? And on the other hand, what are the features on lower priced cars. 

## Data Analysis

To start the analysis, we've looked at the data distribution and performed pre-processing or cleaning of data. Here are some of the data distributions:

![alt text](https://github.com/cdungca/used-cars/blob/main/images/drive.png "Drive Distribution")

![alt text](https://github.com/cdungca/used-cars/blob/main/images/condition.png "Condition Distribution")

![alt text](https://github.com/cdungca/used-cars/blob/main/images/fuel.png "Fuel Distribution")

![alt text](https://github.com/cdungca/used-cars/blob/main/images/transmission.png "Transmission Distribution")

Based on these distributions and after converting categorical values to numeric, we've kept data with the following criterias:

- only gas powered cars
- automatic transmissions
- title status should be clean
- condition of the car should be good, excellent, or like new
- only keep cars made after 2012

![alt text](https://github.com/cdungca/used-cars/blob/main/images/correlation.png "Correlation")

Looking at the correlation of the numeric data to price, we can observe the following:

- both year and cylinder have positive correlations, which means price will increase when both values are higher
- odometer has a negative correlation, the higher the odometer reading, the lower the price

![alt text](https://github.com/cdungca/used-cars/blob/main/images/pairplot.png "Pairplot")

Here are some observations that we can see from the pairplot for cars with prices higher than 50k:

- cars made after 2015
- cars with cylinders greater than 5
- odometer reading less than 50k 

To further our analysis, we've created 3 different models that predicts price based on the features. The training of the model was done on 80% of the data and it was validated using the remaining 20%. Comparing the error on the prediction on the test data, we were able to identify the model with the least error, which is the one where we've used Lasso Regression.

We've used this model to identify the most important features that drive the price higher or lower. Here are the top features based on this model:

![alt text](https://github.com/cdungca/used-cars/blob/main/images/topcoefficients.png "Top Coefficients")

## Recommendation

When looking for cars to buy, the following features should have higher priority since you can sell them at a higher price:

- Manufacturer = Porsche, Rover, Volvo, Mercedes Benz, Lexus, Jaguar, Audi, BMW, Cadillac
- Cylinders >= 6
- Year >= 2015
- Type = coupe
- Odometer < 50k
- Condition = good, excellent, or like new
- Title status = clean
- automatic transmissions

For existing cars in your inventory with the following features, they should be sold right away:

- Manufacturer = Mitsubishi, Fiat, Chrysler, Dodge, Nissan
- Odometer > 50k
- Type = sedan








