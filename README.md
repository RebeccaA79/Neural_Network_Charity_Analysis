# Neural_Network_Charity_Analysis

## Analysis Overview
The purpose of this project is to use deep-learning neural networks with the TensorFlow platform in Python, to analyze and classify the success of charitable donations.

The project is comprised of the following steps:

- preprocessing the data for the neural network model
- compile, train and evaluate the model
- optimize the model


## Results

### Data Preprocessing

- The column 'IS_SUCCESSFUL' is considered the target variable for this model. 

- Variables considered features for this model include the following columns: 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS', and 'ASK_AMT'.

- The columns `EIN` and `NAME` were considered neither targets nor features and were removed from the dataset. 

### Compiling, Training, and Evaluating the Model

- This neural network model is made of two hidden layers, containing 80 and 30 neurons, respectively. Both the first and second layer use the "relu" activation function. The output layer uses the Sigmoid function.

![define_the_model](https://github.com/RebeccaA79/Neural_Network_Charity_Analysis/blob/main/images/define_the_model.png)

- The model was not able to achieve the 75% target model performance and only reached an accuracy of 53.7%.

![model evaluation](https://github.com/RebeccaA79/Neural_Network_Charity_Analysis/blob/main/images/model_evaluation.png)

#### Attempts at increasing model performance

Attempt 1:
The following changes were made to the model:

 - Removed additional features in the model including 'USE_CASE' and 'SPECIAL_CONSIDERATIONS'
 - Changed the application_type replacement value count by increasing the count from less than 500 to less than 1,000.
 - Changed the classification replacement value count by decreasing the count from less than 1,000 to less than 500.
 - Added a third hidden layer to the model and increased the number of neurons to 100/50/15, respectively. 
 - Changed the activation function of the hidden layers to sigmoid/relu/relu, respectively.
 - Increased the number of epochs from 100 to 150

Attempt 1 Results: The model accuracy score increased to 64% from 53.7%

![attempt 1 results](https://github.com/RebeccaA79/Neural_Network_Charity_Analysis/blob/main/images/attempt1_model_accuracy.png)

Attempt 2:

All changes made in attempt 1 were retained with the exception of the following:
 - Increased the number of neurons to 100/85/50, respectively
 - Increased the number of epochs from 150 to 200

Attempt 2 Results: The model accuracy dropped significantly to 46.7%.

![attempt 2 results](https://github.com/RebeccaA79/Neural_Network_Charity_Analysis/blob/main/images/attempt2_model_accuracy.png)

Attempt 3:
The following was changed in the model from Attempt 2:
 - Used 'AFFILIATION' and 'ORGANIZATION' counts for binning rather than APPLICATION_TYPE and CLASSIFICATION.

Attempt 3 Results: The model accuracy increased slightly to 48.8% but is still well below the initial and first attempt accuracy scores.

![attempt 3 results] (https://github.com/RebeccaA79/Neural_Network_Charity_Analysis/blob/main/images/attempt3_model_accuracy.png)

## Summary
The model ended up with the accuracy score of 48.8% after the third attempt at optimization. The highest score received was in attempt 1 with an accuracy score of 64% though I never reached the target goal of 75%. It would be beneficial to return to the parameters set for attempt 1 optimization and determine how they could be tweaked to continue an upward trend in accuracy. Additionally, it would be worth evaluating the models with other alternatives such as Random Forest Classifier to see how the model responds under a supervised machine learning approach.
