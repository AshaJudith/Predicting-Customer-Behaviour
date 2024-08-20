PREDICTING CUSTOMER BUYING BEHAVIOUR

PROJECT OVERVIEW

PROJECT: PREDICTING CUSTOMER BUYING BEHAVIOUR

PROBLEM STATEMENT
The goal of this project is to develop a predictive model that can forecast customer buying behaviour, specifically whether a customer will make a booking or not. The project involves exploring and preparing a dataset, training a machine learning model, and evaluating its performance. The dataset contains various features related to customer behaviour, and the target outcome is a binary variable indicating whether a customer makes a booking.

Background
Understanding customer buying behaviour is crucial for businesses to develop effective marketing strategies, improve customer satisfaction, and increase revenue. With the rise of e-commerce and online booking platforms, businesses have access to vast amounts of customer data, which can be leveraged to build predictive models that can identify patterns and trends in customer behaviour.

Objectives
Explore and prepare the dataset for modelling.
Train a machine learning model to predict customer buying behaviour.
Evaluate the performance of the model using cross-validation and evaluation metrics.
Create visualizations to interpret the contributions of each variable to the model.
Summarize the findings in a single slide for presentation to stakeholders.

Methodology
Load and explore the dataset using pandas and data visualization tools.
Clean and preprocess the data by handling duplicates, converting categorical variables, and creating new features.
Train a machine learning model using a suitable algorithm, such as a RandomForest.
Evaluate the model's performance using cross-validation and evaluation metrics.
Create visualizations to interpret the contributions of each variable to the model.
Summarize the findings in a single slide for presentation to stakeholders.

DATASET OVERVIEW

Source
The dataset is provided in a CSV file named "Predicting customer buying behaviour.csv" and is loaded into a Pandas dataframe using the pd.read_csv function.

Features
The dataset contains various features related to customer buying behaviour, including:
sales_channel: categorical variable representing the sales channel
trip_type: categorical variable representing the type of trip
flight_day: categorical variable representing the day of the flight
route: categorical variable representing the route
booking_origin: categorical variable representing the booking origin
purchase_lead: numerical variable representing the lead time for purchase
length_of_stay: numerical variable representing the length of stay
flight_hour: numerical variable representing the hour of the flight
booking_complete: binary target variable indicating whether a customer made a booking or not
lead_time_category: categorical variable created by binning purchase_lead into categories
flight_time_category: categorical variable created by binning flight_hour into categories

DATA CLEANING
The first step in preparing the dataset for analysis is to clean the data. This involves checking for and removing any duplicate rows, as well as handling any missing or erroneous data.

Checking for Duplicate Rows
To check for duplicate rows, we use the duplicated() function in pandas, which returns a boolean Series indicating whether each row is a duplicate of a previous row. We then sum up the number of duplicate rows using the sum() function.

Removing Duplicate Rows
If there are any duplicate rows, we remove them using the drop_duplicates() function. This function returns a new DataFrame with the duplicate rows removed.

Checking for Remaining Duplicate Rows
After removing the duplicate rows, we check again to make sure that there are no remaining duplicate rows.

DATA PREPROCESSING
Data preprocessing is an essential step in machine learning, as it involves transforming the raw data into a format that is suitable for modeling. In this project, we employed several data preprocessing techniques to prepare the dataset for analysis.

One-Hot Encoding For Categorical Variables
One-Hot Encoding is a technique used to convert categorical variables into numerical format. This is necessary because many machine learning algorithms cannot handle categorical variables directly. We used the pd.get_dummies() function to perform One-Hot Encoding on the following categorical variables: sales_channel, trip_type, flight_day, route, and booking_origin. The drop_first=True parameter was used to avoid multicollinearity by dropping one of the dummy variables for each category.

Creating New Features Using Pd.Cut()
We created two new features, lead_time_category and flight_time_category, using the pd.cut() function. This function is used to bin continuous variables into categorical variables. We binned the purchase_lead variable into six categories based on the number of days before the flight, and the flight_hour variable into four categories based on the time of day.

One-Hot Encoding For Newly Created Categorical Features
After creating the new features, we performed One-Hot Encoding on them using the pd.get_dummies() function again. This is necessary because the new features are categorical and need to be converted into numerical format for modeling.

OUTLIER DETECTION
Outlier detection is an essential step in data preprocessing, as it involves identifying and handling data points that are significantly different from the rest of the data. In this project, we used the Interquartile Range (IQR) method to detect outliers in the purchase_lead and length_of_stay columns.

Defining A Function To Detect Outliers Using The Iqr Method
We defined a function detect_outliers that takes a DataFrame df and a column name column as input. The function calculates the first quartile (Q1), third quartile (Q3), and Interquartile Range (IQR) of the column. It then uses the IQR method to identify outliers, which are data points that fall below Q1 - 1.5 * IQR or above Q3 + 1.5 * IQR.

Identifying Outliers In Purchase_lead And Length_of_stay
We applied the detect_outliers function to the purchase_lead and length_of_stay columns of the preprocessed dataset df_encoded. The function returned the outliers in each column, which we stored in the outliers_purchase_lead and outliers_length_of_stay variables. We then printed the number of outliers in each column using the shape[0] attribute.

Exploratory Data Analysis (EDA)
Exploratory Data Analysis (EDA) is an essential step in the machine learning workflow, as it involves exploring and understanding the characteristics of the dataset. In this project, we performed EDA to gain insights into the distribution of the target variable, relationships between variables, and correlations between features.

Univariate Analysis: Distribution Of The Target Variable (Booking_complete)
We performed univariate analysis to understand the distribution of the target variable booking_complete. We used a count plot from the Seaborn library to visualize the distribution of booking_complete. The plot shows the number of bookings that were completed (1) and not completed (0).

Bivariate Analysis: Relationship Between Booking Completion And Lead_time_category
We performed bivariate analysis to understand the relationship between booking_complete and lead_time_category. We used a bar plot from the Seaborn library to visualize the relationship between the two variables. The plot shows the proportion of bookings that were completed for each lead time category.

Correlation Analysis: Heatmap Of Correlation Between Features
We performed correlation analysis to understand the relationships between all features in the dataset. We used a heatmap from the Seaborn library to visualize the correlation matrix. The heatmap shows the correlation coefficients between each pair of features.

VISUALIZATIONS
The following visualizations are created:

Distribution Of Booking Completion
This visualization shows the distribution of the target variable booking_complete. The count plot displays the number of bookings that were completed (1) and not completed (0).

Booking Completion Vs Lead Time Category
This visualization shows the relationship between booking_complete and lead_time_category. The bar plot displays the proportion of bookings that were completed for each lead time category.

Correlation Heatmap
This visualization shows the correlation between all features in the dataset. The heatmap displays the correlation coefficients between each pair of features.
