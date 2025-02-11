# SPAM E-mail Database



1. Introduction
2. Import the libraries
3. Data Cleaning adn Preparation
4. Data Exploration EDA
5. Principal Component Analysis (PCA) 
6. Machine Learning Method
7. Conclusion 
8. References

 ## 1) Introduction

In this assessment, we explore a dataset containing 4601 rows and 59 columns, aiming to uncover insights while addressing common challenges such as missing values, data type inconsistencies.
The primary focus of this assessment is to process the dataset through key steps of Data Cleaning and Preparation and apply Principal Component Analysis (PCA) to optimize its usability for machine learning. By systematically cleaning and transforming the data, we ensure its integrity and prepare it for advanced analytical techniques.
Data Cleaning and Preparation: This involves resolving issues like missing or inconsistent data types, removing duplicate rows, and verifying the dataset's readiness. The importance of these steps lies in improving data reliability and eliminating noise that could hinder model performance.Principal Component Analysis (PCA): PCA is implemented to reduce the dimensionality of the dataset while retaining its essential features. This step addresses the challenge of high-dimensional data by summarizing it into a manageable number of principal components.

## 2) Data Cleaning and Preparation

I noted that the dataset contains 4601 rows and 59 columns, and several columns have missing values. Some columns, such as word_freq_our, word_freq_000, word_freq_hpl, and word_freq_labs, are of object type but should likely be numeric.

I started by removing the first column, 'Unnamed', and converting all object columns to numeric using a function. After that, I filled the null values with 0 to complete Nan rows. To check for any issues, I used the info() function to verify if all the information was correct.
duplicated rows
 
Data Cleaning Steps:
1. Drop the Unnamed: 0 column.
2. Convert object columns to numeric (handling any errors).
3. check and handle missing values (fill NaN with 0).
4. Check for duplicate rows and remove them if any.
5. Verify data integrity after cleaning.


#### Explained Variance 

In this step, I create a graph to understand which principal component is most suitable for applying PCA. The column spam (from the spam_dataset) is the independent variable that has been removed from the dataset. The explained_variance_ratio_ is an attribute of the PCA object that indicates the proportion of variance explained by each of the principal components. The graph shows the relationship between the number of components (ranging from 2 to 10) and the performance of the analysis. In this case, I tested around 10 different numbers of components, and 10 components proved to be the optimal choice for achieving better analytical performance.

1. Get the cumulative explained variance
2. Create a graph to check the number of component for analyct


## 5) Principal Component Analysis (PCA) 

PCA is a technique to reduce the number of features while retaining as much variance as possible. This is useful when dealing with high-dimensional data. The StandardScaler was applied to the dataset, and After normalization technique has been applied, as shown in the class on 18/11 (StandardScaler). With this, it was possible to apply PCA and reduce the dimensionality, obtaining 10 independent components (columns) and 1 dependent column to better use the data in machine learning.

1. Apply the StandardScaler to all the columns of the DataFrame.
2. Normalize Data
3. Apply PCA
4. Created a New columns to replace the data frame
5. Replace the names of spam column "True" and "False" to numbers 0 and 1.
6. A new DataFrame is created with the columns from spam_pca (independent variables) and the column df["is_spam"] (dependent variable).


## 6) Machine Learning Method 

In this part of the project, I imported some libraries for machine learning tests to identify which one best fits to achieve 99% accuracy. The Random Forest model stood out, as mentioned on the scikit-learn website.

A Random Forest is a meta-estimator that fits a number of decision tree classifiers on various sub-samples of the dataset and uses averaging to improve predictive accuracy and control overfitting{8}.

This method showed the highest level of accuracy, indicating that the model achieved an average performance of 98.72%. The small standard deviation (0.75%) suggests that the model is consistent. A box plot was created to better visualize each test.

Explanation
1. Train-Test Split: The dataset is split into 80% training and 20% testing data.
2. Predictions: The model predicts the is_spam class for the test data.
3. Model Training: some models is fitted on the training data and test.
4. Boxplot has been ploted to undertand whic model is better.
5. The Random Florest model has shown better performance and was implemented.

## 7) Conclusion

The dataset consists of 4601 rows and 59 columns, with some missing values. After cleaning the data (removing the 'Unnamed' column, converting object columns to numeric, and filling missing values), I verified the dataset using the info() function.
To determine the optimal number of principal components for PCA, I removed the 'spam' column (the independent variable) and analyzed the explained_variance_ratio_. I tested various numbers of components and found that 10 components provided the best analytical performance. PCA was applied to reduce the dimensionality, and StandardScaler was used for data normalization.
For machine learning, I tested multiple models to achieve 99% accuracy. The Random Forest model, which uses decision trees and averaging to improve accuracy, stood out. It achieved an average accuracy of 98.72% with a low standard deviation (0.75%), indicating high performance and consistency. A box plot was used to visualize the results.
In conclusion, Random Forest was the most effective model, and PCA helped improve the analysis by reducing dimensionality obtain a significant result bellow:

- **540** is the number of non-spam correctly classified as non-spam (true negative).
- **12** is the number of non-spam classified as spam (false positive).
- **16** is the number of spam classified as non-spam (false negative).
- **353** is the number of spam correctly classified as spam (true positive).


## 8) References

{1} Stack Overflow (2016) Better way to drop NaN rows in pandas. Available at: https://stackoverflow.com/questions/36370839/better-way-to-drop-nan-rows-in-pandas (Accessed: 20 June 2024).

{2}Stack Overflow (2014) Selecting pandas columns by dtype. Available at: https://stackoverflow.com/questions/21271581/selecting-pandas-columns-by-dtype (Accessed: 20 December 2024).

{3}Pandas Documentation (n.d.) pandas.DataFrame.select_dtypes. Available at: https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.select_dtypes.html (Accessed: 20 December 2024).

{4}Pandas Documentation (n.d.) pandas.to_numeric. Available at: https://pandas.pydata.org/docs/reference/api/pandas.to_numeric.html (Accessed: 20 December 2024).

{5}Stack Overflow (2014) How to convert column to numeric in pandas. Available at: https://stackoverflow.com/questions/21997808/how-to-convert-column-to-numeric-in-pandas (Accessed: 20 December 2024).

{6}Ryan & Matt Dataset. (7 de set. de 2023). Title of video. Website name. Available at: URL (Accessed: 10 December 2024).
PCA Analysis in Python Explained (Scikit - Learn).YouTube. Available at: https://www.youtube.com/watch?v=6uwa9EkUqpg (Accessed: 10/12/2024).

{7}Ryan & Matt Data Science. 2023r).Python Feature Scaling in SciKit-Learn (Normalization vs Standardization)o. YouTube. Available at: https://www.youtube.com/watch?v=6eJHk8JYK2M (Accessed 19 December 2024r).

{8}scikit-learn (2024) sklearn.ensemble.RandomForestClassifier, version 1.5. Available at: https://scikit-learn.org/1.5/modules/generated/sklearn.ensemble.RandomForestClassifier.html (Accessed: 20 June 2024).

{9}Ryan & Matt Data Science. 2023).Random Forest Algorithm Explained with Python and scikit-learn (Normalization vs Standardization)o. YouTube. Available at: https://www.youtube.com/watch?v=_QuGM_FW9eo (Accessed 19 December 2024).
