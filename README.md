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
