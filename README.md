# Neural Network Charity Analysis
Chapter 19 Challenge

## Overview: 

The purpose of this analysis is to use a neural network to create a binary classifier that will determine if applicants will be successful if funded by Alphabet Soup. 
The network will analyze 34000 past applications that received funding over the years. The dataset contains information about the organization's affiliated industry, government
classification, type of organization, income amount, special considerations, amount of funding requested, active statu and if they are successful.

## Results:

### Data Preprocessing:

-The target variable for this model was "IS SUCCESSFUL"
-The feature variables are STATUS, ASK_AMT, APPLICATION_TYPE, SPECIAL_CONSIDERATIONS, CLASSIFICATION, AFFILIATION, USE_CASE, ORGANIZATION, INCOME_AMT. Preprocessing and binning  were done on APPLICATION_TYPE and CLASSIFICATION in order to rebin the data. 
-The variables to be dropped are EIN and NAME

### Compiling, Training and Evaluating the Model:

-Initially, 2 hidden layers with 80 and 30 nodes were used with an output activation function of sigmoid and hidden layer activation functions of relu. The sigmoid output was
used because the model is a binary classifier and relu were used for the hidden layers to help the model learn faster. This yielded a loss of about 0.556 and accuracy of 0.725
![image](https://user-images.githubusercontent.com/78934120/124954799-78f82d00-dfe4-11eb-9e16-9f9eb912db19.png)

-I was not able to achieve the target model performance of 75% but was close with about 73%.
-The 3 steps I took to increase the model performance were:
1. Increase the epochs. I changed the epochs of the model from 100 to 1000. This achieved a loss of 0.621 and an accuracy of 0.726
![image](https://user-images.githubusercontent.com/78934120/124955014-b0ff7000-dfe4-11eb-9b6e-3efe7ef97b56.png)

2. The second attempt I tried to add more nodes per the 2 layers I started with. I changed the first hidden layer from 80 to 300 nodes and the second hidden layer from 50 to 200.
This achieved a loss of 0.573 and an accuracy of 0.726. 
![image](https://user-images.githubusercontent.com/78934120/124955168-d9876a00-dfe4-11eb-923f-a9b1155f6b6e.png)

3. The third attempt I added more hidden layers and kept the node count from the second attempt. I used 5 hidden layers with 300, 200, 100, 75, 50 nodes respectively. This 
yielded a loss of 0.573 and an accuracy of 0.726. 
![image](https://user-images.githubusercontent.com/78934120/124956041-95e13000-dfe5-11eb-9e17-3332b32186e2.png)

## Summary:

The deep learning model did ok as it predicted about 73% of the data correctly. It didn't show much room for improvement with the three different attempts. I suspect the large
variability in the asking amount and income amounts of the different charities are throwing the weights off in the neural network. However, since the data is tabular it might be 
better to try using a Random Forest Classifier to obtain at least similar results. Since this is a classification problem with tabular data, the RFC should be able to handle
the classification with appropriate results. 
