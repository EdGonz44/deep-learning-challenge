# deep-learning-challenge
Module 21 Challenge

# Overview:
The purpose of this project was to create a binary classifier that could predict whether applicants would be successful if funded by Alphabet Soup. A provided dataset with multiple features was used to create this model, and was preprocessed into features and targets for the model. After preprocessing the data, the model was created to establish a baseline in accuracy in successfully predicting if an applicant would be succesful when funded by Alphabet Soup. This baseline model would then undergo multiple alterations in order to achieve a model accuracy of at least 75%.

## Results: 

### Data Preprocessing: 
- The variable that would act as the target for the model was the IS_SUCCESSFUL variable, which was essentially a yes or no categorical variable. A "yes" signified that the money was effectively used, while a "no" meant that the funding was squandered on the applicant.

- The variables that would act as the features in this model include: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT. These features provide both categorical and continuous values that can be used in the model.

- Of the feature variables, CLASSIFICATION and APPLICATION_TYPE were altered in the number of bins they had. This was done in order to condense the multiple unique values that comprised of an extremely small percentage of the dataset when considered seperately. They were then condensed into smaller bins in order to give them more relevance, and to help with preventing the data from being too skewed. 




- The variables that would be dropped in order to keep from cluttering the model would be the EIN and NAME identification columns, as it would be unnecessary for the model to consider these identifiers as they have no relevance in determining if they would be successful with their funding.

  
### Compiling, Training, and Evaluating the Model

In order to optimize the model: the model was increased to have two extra hidden layers with 50 neurons each. At the same time, the first two hidden layers were increased by 20 neurons to 100 and 50 neurons respectively. After these modifications were made, four different activation function combinations were used. These combinations included all relu, alternating leaky relu to relu, tanh to relu, and then elu to relu. The last activation function for the output layer was kept at sigmoid due to the nature of the model acting as a binary classifier.
![Model Alterations](https://github.com/EdGonz44/deep-learning-challenge/blob/main/Images/Activation_attempts.png)

At the very end of testing the model, the amount of epochs was also increased from 100 to 200.
![Epoch change](https://github.com/EdGonz44/deep-learning-challenge/blob/main/Images/Epoch_change.png)

These were all done in order to help with overcoming the moderate loss and low accuracy that we continuously encountered. It was believed that perhaps the model was not given enough capability in analyzing the data, possibly resulting in underfitting. The solution was then to increase the neurons used, the possible hidden layers, and to try different combinations of activation functions. 
![Last Model Build](https://github.com/EdGonz44/deep-learning-challenge/blob/main/Images/Last_model_build.png)

In order to further optimize the model, attempts were made to drop more unimportant features such as STATUS and SPEICAL_CONSIDERATIONS as they only had to unique values, which were essentially yes or no. One of these values eclipsed the amount of existing rows in the dataset they each had, so it was deemed unnecessary to keep the feature due to its lack of creating any meaningful distinctions for the model.
![Features Dropped](https://github.com/EdGonz44/deep-learning-challenge/blob/main/Images/Column_drops.png)


Afterwards, further condensing in the number of bins was done for the AFFILIIATION, ORGANIZATION, and USE_CASE as they also had a few categories that were very small on their own. Therefore it felt it would be prudent to merge these categories into one larger, singular category such as "Other".
![Affiliations Condensed](https://github.com/EdGonz44/deep-learning-challenge/blob/main/Images/Affiliation_condensing.png)
![Organizations Condensed](https://github.com/EdGonz44/deep-learning-challenge/blob/main/Images/Organizations_condensed.png)
![Uses Condensed](https://github.com/EdGonz44/deep-learning-challenge/blob/main/Images/Uses_condensed.png)

After modifying the model through altering its structure, and then modifying the features themselves, we were not able to achieve the target model performance. Throughout the eight attempts in optimizing the model, each experienced similar loss and accuracy values. The loss that each test hovered with the 0.55-0.60 range, while the accuracy never breached past 0.73. These values indicate that the model could benefit from increasing the complexity of the model's structure amongst other options.

## Summary:
The binary classifier created for this project, despite multiple attempts at optimizing, was not able to improve the target model performance of 0.75 accuracy. Despite these numerous modifications, the loss and accuracy of the model maintained consistent values. The combination of these values suggest that the model could be improved through adding to the complexity of the model itself. This could be done either through increasing the amount of hidden layers used in the model, increasing the testing epochs, or even adding features that could possibly combine seemingly disparate current features into ones that better represent the data.

Summary: Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.
