# GooglePlaystoreAppData
Assignment from Udacity data scientist program
Link to the blog- https://medium.com/@akshatbhardwaj_33992/ever-wondered-launching-your-own-app-on-google-playstore-f1adecc5e2f

I selected this dataset from Kaggle for Udacity assignment where I had to analyse the data using my imagination and knowledge and write a blog which shall be evaluated.

Google app reviews clustering.ipynb- Jupyter notebook instance of my work on analysing and predicting using Linear Regression Model.
Google app reviews clustering.html - This file is html version of jupyter notebook with output from all cells.
googleplaystore.csv - This file contains all the details of the applications on Google Play. There are 13 features that describe a given app.
googleplaystore_user_reviews.csv
This file contains the first 'most relevant' 100 reviews for each app. Each review text/comment has been pre-processed and attributed with 3 new features - Sentiment, Sentiment Polarity and Sentiment Subjectivity.

3 Business questions I am trying to find answers about are-
1. What is important to know about Apps on Playstore?
2. Find a pattern of user reviews related to category of apps.
3. Predict pricing in relation to number of installations.

One additional thing I would like to do is run different models like Gaussian Naive and Stochastic models on this dataset. But the dataset is too parse to find good enough results.

Evaluation and Analysis of results

    Evaluate the mean squared error MSE- 
        Case One- Target Label = 'Rating' (1.3819674820377472e-08, 'Reviews'), (1.0710294006119369e-10,'Installs')
        with 'Rating' as target label, model has predicted with much higher coefficients of Reviews and Installs clearly because of high biases which does not show a correct picture.Category values should have been weighed higher -  (-0.0018024997071665536, 'Category'). To me this looks like a misprediction due to biased values.
    
    
    Case Two- Target Label = 'Price_in_dollars' - Mean Squared Error: 1.9064629909990272, MSE is not closer to 0 and highest in comparision to other target labels but the coefficients are equally distributed and it seems that there is no bias introduced during prediction. With maximum value of coefficient (0.19030847314185675, 'Type_Paid'), Linear Regression defines Price has an important feature for App selection. Which sould rational too.
    
    
    Case Three- Target Label = 'Installs' - Mean Squared Error: 0.4897947759940874, MSE is close to Zero which is a good sign and coefficients have correctly identified the weights of features as (0.6627852226270038, 'Reviews')(0.025157112715526838, 'Category'). This shows that Linear Regression model could predict success of an App better if the target label is set to Installs.
    
    It is even interesting to see corelation between predicted price and installs.
    
    Predicted Price vs Predicted Installs

    Linear Regression model shows that predicted price and number of installs are proportional and tends to increase together. (Small Blue line is predicted price and the large Orange line is predicted Installs).   Form Violin plot at the end it would be clear that for certain categories of Apps on playstore, consumers pay for the App.
    
    
    
    "An MSE of zero, meaning that the estimator predicts observations of the parameter with perfect accuracy, is the ideal, but is typically not possible."
        
    Reference link- https://en.wikipedia.org/wiki/Mean_squared_error
