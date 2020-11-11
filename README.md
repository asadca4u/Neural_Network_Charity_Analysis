# Neural_Network_Charity_Analysis

### Overview of the analysis:
- Alphabet Soup is a large charity organization that funds various initiatives across the globe. However it maintains no control over how the funds are used after they have been disbursed to the clients, often resulting in funds being used unsuccessfully for the stated objectives.
- In this analysis, we will employ a deep learning neural network classification model, based on a series of features about a potential client, to predict whether or not they will be successful to a reasonable degree in acheiving their objectives if they were to receive funding from Alphabet Soup. 
- The objective of this analysis is to optimize the disbursments from Alphabet Soup's perspective, so that more funds are given to clients that are likely to be successful in acheiving their objectives.

### Results:

#### Data Preprocessing:

What variable(s) are considered the target(s) for your model?
- The IS_SUCCESSFUL column, that describes whether or not the client was successful is the target.  

What variable(s) are considered to be the features for your model?
- APPLICATION_TYPE: Alphabet Soup application type
- AFFILIATION: Affiliated sector of industry
- CLASSIFICATION: Government organization classification
- USE_CASE: Use case for funding
- ORGANIZATION: Organization type
- STATUS: Active status
- INCOME_AMT: Income classification
- SPECIAL_CONSIDERATIONS: Special consideration for application
- ASK_AMT: Funding amount requested

What variable(s) are neither targets nor features, and should be removed from the input data?
- EIN and NAME: are just identification columns and should be removed. 

#### Compiling, Training, and Evaluating the Model:

How many neurons, layers, and activation functions did you select for your neural network model, and why?
- I used 3 hidden layers, with the first layer having 8 neurons, the second layer having 6 neurons and the third layer having 4 neurons. 
- all three hidden layers used a relu activation function due to its ability to simplify the output that will serve as the input for our final output layer, which uses a sigmoid function. 

![NNM](https://github.com/asadca4u/Neural_Network_Charity_Analysis/blob/main/Challenge/Images/1.png)

Were you able to achieve the target model performance?
- Unfortunately we were not able to acheive the desired accuracy score of 75%, instead remaining stuck at just over 72%. 

![Acc_Score](https://github.com/asadca4u/Neural_Network_Charity_Analysis/blob/main/Challenge/Images/2.png)

What steps did you take to try and increase model performance?
- In addition to adding an another hidden layer to the neural network model, I made some adjustments at the preprocessing phase. 
- I dropped the INCOME_AMT column, as this column's dataset was inconsistently recorded, with various ranges, rather than actual numbers, and the vast majority of the entries were recorded as 0, as you can see in the image below.

![INCOME_AMT](https://github.com/asadca4u/Neural_Network_Charity_Analysis/blob/main/Challenge/Images/5.png)

- I also dropped the ASK_AMT column, as this column contained 8747 unique values, and was liable to confuse the model. 

![ASK_AMT](https://github.com/asadca4u/Neural_Network_Charity_Analysis/blob/main/Challenge/Images/6.png)

![Columns_Dropped](https://github.com/asadca4u/Neural_Network_Charity_Analysis/blob/main/Challenge/Images/3.png)

- I also altered the binning for the APPLICATION_TYPE and CLASSIFICATION columns, both of which contained more than 10 unique values, this resulted in more values being placed into the "Other" bin, and having less bins overall. 
- As you can see in the image below, in the APPLICATION_TYPE column, any unique value with a frequency of less than 1000 was placed in the "Other" bin, this was increased from 500 in the previous model. The same transformation was applied to the CLASSIFICATION column. 

![Columns_Dropped](https://github.com/asadca4u/Neural_Network_Charity_Analysis/blob/main/Challenge/Images/4.png)

### Summary: 

Summarize the overall results of the deep learning model. 
- The deep learning model performed relatively poorly, especially considering the effort and resources this model takes to setup. This was a fairly simple classification problem, however the features provided to the model were relatively suspect with regards to how well they might correlate with a successful outcome from a client who has received funding.
- As such, I beleive the model was handicapped from the outset, and that features such as application type and classification type have less to do with success in acheiving the stated goals than other metrics that are more closely related to the functioning of each individual client, rather than how they are classified within the context of Alphabet Soup itself. 

Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.
- Another model, such as a Machine Learning classification tree may be able to classify with greater accuracy than the Neural Network, however it would be at a risk of overfitting, especially due to the poorly chosen features that were avaliable to input to the model. 
- As a result, for any classification model to be meaningfully successful, it would require input that was meaningfully related to the operations of client organizations and how successful they are at acheiving their stated goals. 
