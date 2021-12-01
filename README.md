# Neural_Network_Charity_Analysis

### Overview

The purpose of this analysis is to create a model which will predict whether or not a beneficiary of Alphabet Soup Charity will be successful in acheiving the objective for the donation they receive.

### Data Preprocessing

The target variable, therefore, is the "IS_SUCCESSFUL" column of the dataframe. 

![image](https://user-images.githubusercontent.com/84299125/140449978-a8f3e0c8-c9b2-40a7-b923-5e05ef45edf7.png)


There are two features in the model; y is the target variable and X is the compilation of the rest of the dataset minus some unnecessary columns.

After removing the "EIN" and "Name" columns, from the Dataset, I do believe the rest of the data contains possible factors connected with the success or failure of a beneficiary. I would not drop any further columns.

![image](https://user-images.githubusercontent.com/84299125/140449910-a5803a9e-7049-4876-88c8-32cf77624a40.png)


### Compiling, Training, and Evaluating the Model

At first, I selected two layers, with 6 neurons in the first and 4 in the second. I was following the 3:1 ratio which is a rule of thumb. However, I was not impressed with the result, so I changed it to 8 neurons in the first and 5 in the second. This acheived slightly better results. I used the relu activation functions for the hidden layers due to the complexity of the data. I selected sigmoid for the output because the target is binary. I also tried the tanh function, but this reduced the accuracy of the model  (I had not yet read ahead to see that we would be testing different models for deliverable 3, or I would have saved these other attempts).

I was not able to acheive the desired 75% performance rate. ![image](https://user-images.githubusercontent.com/84299125/140450061-bb559e78-0015-4245-98d9-2d08ccb41aec.png)


To optimize the model, I added a third hidden layer. This acheived only slightly better results, but I kept it. Then I changed the activation function for the hidden layers to sigmoid, so that all functions would be alike. This again yielded marginal improvement. 

![image](https://user-images.githubusercontent.com/84299125/140450289-126fb157-f61e-43bf-a968-d835cf86151f.png)


Finally, I increased the number of bins for the application types. I chose to do this because the code from the module only left 2 bins. There are 17 different application types, with tens of thousands of values. It seemed that more bins would be appropriate when there is so much variation.

![image](https://user-images.githubusercontent.com/84299125/140450485-a3f8d826-93bd-4acf-84b4-666759b29b1e.png)


This netted me significant improvement of 2%, which is far more than I acheived with any other changes.

![image](https://user-images.githubusercontent.com/84299125/140450364-d31b1554-767c-41eb-8a17-ccc8e7b7d2a2.png)


## Summary

The overall performance of this model on this dataset was unimpressive, with a number of variations all ending with lower than 73% accuracy. What is more, each variation ceased to improve performance significantly after 45 epochs or less. An increased number of epochs would likely not lead to improvement of the model. I would suggest a Random Forest Model. There are a lot of variables within the dataset, and Random Forest would use them in a more balanced fashion, I believe. It's a little bit like adding neurons, but without giving too much favor to any one variable.
