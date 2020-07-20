# Day 7

## Data Drift

- Data Drift is a change in input data for a model.
- Overtime, data drift causes degradation in model performance, as the input data drifts farther and farther from the data on which the model was trained.

######  Here are a couple different types of comparisons you might want to make when monitoring for data drift:

- Comparing input data vs. training data. This is a proxy for model accuracy; that is, an increased difference between the input vs. training data is likely to result in a decrease in model accuracy.
- Comparing different samples of time series data. In this case, you are checking for a difference between one time period and another. For example, a model trained on data collected during one season may perform differently when given data from another time of year. Detecting this seasonal drift in the data will alert you to potential issues with your model's accuracy.


### Parameters and Hyperparameters

When we train a model, a large part of the process involves learning the values of the parameters of the model. For example, earlier we looked at the general form for linear regression:

`Y = B0 + B1*X1 + B2*X2 +.......+ Bn*Xn`

The coefficients in this equation, `B0....Bn`, determine the intercept and slope of the regression line. When training a linear regression model, we use the training data to figure out what the value of these parameters should be. Thus, we can say that a major goal of model training is to learn the values of the model parameters.

In contrast, some model parameters are not learned from the data. These are called hyperparameters and their values are set before training. Here are some examples of hyperparameters:

- The number of layers in a deep neural network
- The number of clusters (such as in a k-means clustering algorithm)
- The learning rate of the model
- We must choose some values for these hyperparameters, but we do not necessarily know what the best values will be prior to training. Because of this, a common approach is to take a best guess, train the model, and then tune adjust or tune the hyperparameters based on the model's performance.

### Splitting the Data

We typically want to split our data into three parts:
- Training data
- Validation data
- Test data

We use the training data to learn the values for the parameters. Then, we check the model's performance on the validation data and tune the hyperparameters until the model performs well with the validation data. For instance, perhaps we need to have more or fewer layers in our neural network. We can adjust this hyperparameter and then test the model on the validation data once again to see if its performance has improved.

Finally, once we believe we have our finished model (with both parameters and hyperparameters optimized), we will want to do a final check of its performance and we need to do this on some fresh test data that we did not use during the training process.
