# Business Report

# Executive Summary:
This project investigates the complexities of FoodieBay's restaurant dataset in an effort to unearth insightful information and build prediction models in response to the analytical requirements of FoodsAnalytics. The project's goal was to identify the variables that affect restaurant reviews on India's FoodieBay website. We combined supervised and unsupervised machine learning approaches with careful data investigation. 
The method involves thorough data preparation, including pre-processing and cleaning procedures. Table reservations, online ordering, the average bill for two people, and user review rankings were all shown to have a substantial link by using exploratory data analysis (EDA). Two prediction models that provide granular understanding of restaurant evaluations were created and carefully tested. Additionally, to cluster comparable eateries and help identify different market categories, unsupervised machine learning methods were used.
In the analysis we suggest a prediction model that makes use of the important criteria we've uncovered to reliably anticipate restaurant evaluations based on our data. The selected model has exceptional performance indicators, which guaranteed its dependability for FoodsAnalytics. To preserve accuracy for future encounters, we recommend regular upgrades and model improvements. We also provide technical information, such as information on the development environment and a thorough schematic of the machine process, to help with model deployment. This research paves the way for next data-driven projects using FoodsAnalytics while also addressing the analytical demands of the present.
I would like to express my gratitude to Ms. XYZ, Head of Data Analytics and her fantastic team for proper coordination and management throughout the process.
Note: Codefile in the whole report refers to the python notebook for this assignment.

# Introduction:
This investigation has been commissioned by FoodsAnalytics, a well-known data analytics consulting organisation, with the intention of providing a solution to an urgent operational challenge that the company is now facing. The FoodieBay dataset is a subset of data from the well-known Indian restaurant aggregator FoodieBay. FoodsAnalytics has been working to decipher the intricacies of the restaurant rating system that is included inside the dataset. 
The task at hand is to determine the fundamental elements that influence restaurant evaluations on the FoodieBay platform, with a particular emphasis on partner restaurants in India. By gaining a knowledge of these components, FoodsAnalytics intends to provide its clientele with vital information that will assist restaurants in boosting the experiences of their patrons, optimising the services they provide, and eventually raising their ratings.
The value proposition of this project is that it will be able to provide FoodsAnalytics and their customers with information that can be put into action. This research helps strategic decision-making by illuminating the subtle interaction of factors such as table booking availability, online ordering possibilities, average cost for two, and user review rankings. Restaurants may use these information to better adapt their menus, hence increasing customer happiness and, as a direct result, their ratings on the FoodieBay platform. 
FoodsAnalytics is in a position to equip restaurants with data-driven solutions by solving this significant obstacle, which will in turn stimulate growth and improve overall consumer engagement. This research not only improves FoodsAnalytics' analytical skills but also helps to solidify the company's standing as a reliable adviser within the data analytics consulting industry's increasingly cutthroat competitive environment.

# Approach:
In totality 3 models were developed:
1.	Decision Tree
2.	Random Forest Regressor
3.	KNN-Classifier

After observing the performance of the initial two models, conclusion came to only one model which was decided to be more useful in making predictions after looking at different parameters.
The first two were developed in order to predict the ratings of the restaurants. The later classifier was constructed for classifying the restaurants based on whether they provide table booking or not.
For the first two, the predictors were all the attributes having useful numerical values (for example the phone column, address column were ignored because they won’t contribute any significant values in the predictive modelling). The rate column was kept as the label attribute for the first two models.

# Data Preparation and Analysis:
In the very initial steps in order to bring the data and import all the libraries in the environment, the commands has been used.
Using the ‘records’ command the dataset was printed in the environment. It was seen that the data had a sample size of 40130 rows and there were 17 columns, post which, ‘print(records.isnull().sum())’ command has been brought into action and the result were as follows:

![image](https://github.com/user-attachments/assets/9c1b2b4d-e39e-4c96-84e2-a68961d7c9eb)

Since, rate’ is the label column and there is no point in having missing values in the label attribute as this don’t give proper picture of the prediction, all the rows with missing values in rate columns were removed.
Dealing with the missing values (columns):
1.	‘phone’: Replaced with the “Ph Missing” string.
2.	‘dish_liked’: Replaced with “No Dish” string.
3.	‘ave_review_ranking’: Replaced with "median” of the values in the column.

# EDA:
The series of codes were run in codefile	under Question 1, 2, 3, 4 and 5 in to understand more about the dataset and answer the questions of the client. The following visualizations support this argument.

![image](https://github.com/user-attachments/assets/76277b06-ab29-4d7f-8281-f6d4d314f738)
![image](https://github.com/user-attachments/assets/91d1d887-ad15-4c6c-818e-61ff2e934150)
![image](https://github.com/user-attachments/assets/c2bc7da1-8374-47d5-b097-e1694908e0ef)
![image](https://github.com/user-attachments/assets/bd9c638f-05cd-4a57-a049-8b3b2dcced91)
![image](https://github.com/user-attachments/assets/719356e2-aea2-4915-a4b5-74097badf8f5)

Important service patterns in restaurants are shown, along with how they affect customer reviews. Less than 5000 restaurants provide table reservations, compared to more than 25000 that do not. Also, businesses that offer this service have ratings that are 0.5 points better. More than 20,000 eateries provide online ordering, compared to 10,000 that don't, with minimal impact on reviews. A thorough correlation analysis, shown in a confusion matrix, reveals a weak positive correlation between the average cost for two people and the review rating (0.1072), a moderate positive correlation between the average cost for two people and the rate (0.3878), and a strong positive correlation between the review rating and the rate (0.4672). Notably, restaurant evaluations across all sorts range from 3.5 to 4, while the average price for two people ranges between INR 250 and 600. This concise research emphasises the importance of services like online ordering and table reservations, throwing light on their impact on customer reviews and the connections between important features, and offering insightful information for the restaurant business.
Dummy coding of all the categorical variables was done.

# Model's Evaluation and Development:
  
  A.	Supervised ML:
  Decision Tree and Random Forest Regressor:
  i.	Features (Predictor Attributes):  ‘online_order’, ‘book_table’, ‘ave_cost_for_two’, ‘votes’, ‘ave_review_ranking’.
  ii.	Label: ‘rate’.
  
    # Model Evaluation:
    Parameter	Value
    Mean Squared Error (MSE)	0.80
    R Squared (R^2)	0.566
  
  B.	Unsupervised ML:
  Random Forest Regressor:
  
    # Model Evaluation:
    Parameter	Value
    R-Squared Value (R^2)	0.87
    Mean Squared Error (MSE)	0.023

# Solution
Decision tree and random forest regression models were used in the investigation, which yielded important new information about the variables affecting FoodieBay restaurant evaluations. The decision tree model, while having an average R-squared value of 0.5663, identified key elements that affect ratings, such as online ordering, reservations for tables, the average cost for two people, votes, and average review ranking. Given the substantial association between the chosen characteristics and restaurant evaluations, the random forest regression model, which had a much higher R-squared value of 0.8747, exhibited greater predictive ability. The complex interplay between service offers, user experience, and overall ratings is shown by these models taken as a whole.
We advocate rolling out the Random Forest Regressor Model to FoodsAnalytics and its clientele based on the thorough study and exceptional forecasting performance. The prediction of restaurant evaluations using this model was consistently more accurate than the decision tree approach. The random forest regressor provides a strong and trustworthy solution for forecasting restaurant ratings on the FoodieBay platform by using the features "online_order," "book_table," "ave_cost_for_two," "votes," and "ave_review_ranking." Because of its precision and readability, it is the best tool for directing strategic choices focused at raising partner restaurants' customer happiness and ratings.
We recommend constant observation and model improvement for future engagements. To maintain the model's accuracy and applicability over time, regular changes should be done when new data becomes available. To further improve forecasting skills, we also advise looking at cutting-edge methodologies like neural networks and ensemble approaches. A more flexible and quick-response approach may be made possible by working with FoodieBay to have access to real-time data and by directly incorporating user input into the model. FoodsAnalytics will also be able to remain ahead of new trends by doing regular reviews and analyses, ensuring that their customers obtain the most current and useful information for making strategic decisions.

# Technical Solution
1. Environment:
The analysis and the model building and testing was done with the help of Python, used for deep machine learning and statistical analysis	and various other things.
The libraries used includes the following:
a.	Pandas
b.	Matplotlib
c.	NumPy
d.	Scikit-Learn 

2. Data Preprocessing:
The dataset comprising vital information about to restaurants was gathered from FoodieBay and was used in the data collection process.
The process of cleaning the data consisted of addressing issues such as missing numbers, outliers, and inconsistencies in the dataset. For the sake of model compatibility, categorical variables such as "online_order" and "book_table" were given numerical values instead of their usual meanings.
Feature Selection: The features 'online_order,' 'book_table,' 'ave_cost_for_two,' 'votes,' and 'ave_review_ranking' were chosen because of their significance to restaurant ratings and the influence they have on those ratings.
Data Splitting: In order to train the models and evaluate how well they work, the dataset was first divided into training and testing sets using a ratio that is commonly 80-20 or 70-30.
Training of the Models: Using the training data, both the decision tree and the random forest regression models were trained.
Evaluation of the Models: In order to evaluate the models, we used the Mean Squared Error (MSE) and R-squared (R2) metrics to determine how accurate the models were and how well they could predict the future.

3. For Maintaining relevance and accuracy:
Updates to the Dataset Occurring Periodically Ensuring That Models Are Trained on the Most current Data Regular updates to the dataset will guarantee that models are trained on the most current data, which will enhance accuracy.
Continuous Monitoring: Put in place a monitoring system that will look for variations in the performance of the model. If there is a large disparity between the two, this might point to changes in the tastes of customers or trends in the market.
input Loop: Incorporate the input received directly from customers into the model. Model retraining may benefit from the usage of real-time consumer feedback and ratings, which helps ensure relevancy.
Technologies Ahead of Their Time: Maintain an awareness of the most recent breakthroughs in machine learning. Exploring more complex algorithms and methods might result in more accurate forecasts.
Establishing a Collaborative partnership with FoodieBay It is necessary to establish a collaborative partnership with FoodieBay in order to have access to real-time data streams. This has the potential to offer a dynamic data source for the continuous development of the model.
Assuming these suggestions are put into action, it will be easier to maintain accuracy and relevance, which will ensure that the models continue to be useful tools for forecasting and improving restaurant ratings.

# References:

1. Apte, C. (2010). The role of machine learning in business optimization. In Proceedings of the 27th International Conference on Machine Learning (ICML-10) (pp. 1-2).
2. Prasad, D., Goyal, S. K., Sharma, A., Bindal, A., & Kushwah, V. S. (2019). System model for prediction analytics using k-nearest neighbors algorithm. Journal of Computational and Theoretical Nanoscience, 16(10), 4425-4430.
3. Priya, J. (2020, February). Predicting restaurant rating using machine learning and comparison of regression models. In 2020 International Conference on Emerging Trends in Information Technology and Engineering (ic-ETITE) (pp. 1-5). IEEE.
4. Jonathan, B., Sihotang, J. I., & Martin, S. (2019, October). Sentiment analysis of customer reviews in zomato bangalore restaurants using random forest classifier. In Abstract Proceedings International Scholars Conference (Vol. 7, No. 1, pp. 1719-1728).























