# Project Description
Using Python and Python libraries for data science to predict user churn for Waze app.

# Project Overview
The objective of the project is to create a machine learning model that is able to predict user churn for Waze app. By identifying the users who are most likely to stop using the app, the business stakeholders and app management team can engage these users more and create offers and solutions specifically tailored to them so as to minimize user churn.
</b></b>
The dataset used was a CSV file that contained details on the  ID, label(churn status), sessions, drives,total_sessions,n_days_after_onboarding, total_navigations_fav1, total_navigations_fav2, driven_km_drives, duration_minutes_drives, activity_days, and driving_days of 14,999 users.      
</b></b>
To accomplish the task, the data was cleaned, and EDA was performed. Different features were engineered, and later on, different machine learning models were fit to the data. The models used were RandomForest and XGBoost.

The data was split into training, validation, and testing sets in a 0.6:0.2:0.2 ratio, respectively.

After hyper-parameter tuning, the best parameters for the RF model were;

* {'max_depth': None,
 'max_features': 1.0,
 'max_samples': 1.0,
 'min_samples_leaf': 2,
 'min_samples_split': 2,
 'n_estimators': 300}
 
 While the best parameters for the XGBoost model were;
 * {'learning_rate': 0.1,
 'max_depth': 12,
 'min_child_weight': 3,
 'n_estimators': 300}

 </b></b>
 The model was fitted to the data using the best parameters and using recall as the refit metric, the two models had a recall score of 13% and 16% respectively on the validation dataset.
The overall performance of the two models on the different data sets is as follows;
</b></b>
* Performance
  </br> model	         precision	recall		F1			accuracy</b></b>
	
0	RF1 CV			 0.452647	0.109730	0.176090	0.818860</b>
0	XGB1 CV			 0.387959	0.149801	0.215607	0.807320</b>
0	RF VAL PREDS	 0.540323	0.132150	0.212361	0.826224</b>
0	XGB VAL PREDS	 0.425641	0.163708	0.236467	0.812587</b>
0	XGB1 TEST PREDS	 0.378109	0.149901	0.214689	0.805594</b>

</b></b>
The XGBoost model was chosen because it performed better than the RF model. However, neither model produced satisfactory results because the data features were limited and could not produce a robust model.
</b>
The strongest features were km_per_hour, n_days_after_onboarding, percent_sessions_in_last_month, and duration_minute_drives, all which had been feature engineered.

# Recommendations
To improve the model, New features could be engineered to try to generate a better predictive signal, as they often do if you have domain knowledge. In the case of this model, the engineered features made up over half of the top 10 most-predictive features used by the model. It could also be helpful to reconstruct the model with different combinations of predictor variables to reduce noise from uninformative features.
</b></b>
Additional features that could be used to improve model performance include the e drive-level information for each user (such as drive times, geographic locations, etc.). It would probably also be helpful to have more granular data to know how users interact with the app. For example, how often do they report or confirm road hazard alerts? Finally, it could be helpful to know the monthly count of unique starting and ending locations each driver inputs.



 
