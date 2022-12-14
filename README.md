# MachineLearning-Challenge

## Background 
	Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system.
	
	Used Jupyter Notebook, Pandas, Matplotlib, and Scikit-Learn to create machine learning models capable of classifying candidate exoplanets from the raw dataset.

## Analysis
# Model-1 SVM
	*  The first step after reading the data to a dataframe is to decide which features to keep for the model. This exoplanet data has koi_tce_plnt_num column that was not useful as a feature. It was just giving the planets
	numbers as grouping them.
	*  Initially, I removed the features koi_fpflag_nt, koi_fpflag_ss, koi_fpflag_co, koi_fpflag_ec the assumption was since their values are mostly 0's removing them would increase the accuracy of the model, but that wasn't the case. Also removing err1 and err2 columns for all features didn't improve the accuracy but, decreased the accuracy dramatically.
	*  After deciding which features to keep next step was assigning X and y values for the model to perform split data to get train and test data for the model.
	*  Next step is to scale and normalize the data to create more accurate model that has less gap between data points so they all have acurate weights for the model. Initially, using MinMaxScaler to scale the data with SVM model, the training and testing scores were around 0.85. Changing to StandardScaler to scale the data resulted better numbers for the scores, Training Data Score: 0.8916650772458516 ,Testing Data Score: 0.8947368421052632.
	* Using GridSearchCV to tune the model's parameters and changing the grid parameters C and gamma didn't get any score improvement.
	
# Model-2 Logistic Regression
	*  For this model, data cleaning and preprocessing steps were the same as SVM model.
	*  Using StandardScaler resulted better scores that MinMaxScaler, so used StandardScaler to scale and normalize the data.
	*  The scores for training and testing data was :Training Data Score: 0.887659736791913, Testing Data Score: 0.8895881006864989.
	*  Using GridSearchCV to tune the model's parameters, and changing C values, and increasing the number of iterations max_iter didn't improve scores sufficiently.
As a result, the two models SVM and LogisticRegression didn't have any significant difference between them for this data, even hyperparameters tuning didn't help to differentiate the models. We can say SVM model performs slightly better.	


	
