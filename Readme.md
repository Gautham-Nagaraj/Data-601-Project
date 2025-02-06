#  Data 601 Project breast cancer statistics in females

## Introduction and Datasets:
  We will be using 2 datasets in this project: 
  1) SEER dataset [IEEE dataport](https://ieee-dataport.org/open-access/seer-breast-cancer-data)
  2) Survivability estimate for cancer [statCan](https://www.statcan.gc.ca/search/results/site-search?q=13100158&fq=stclac:2&wb-srch-sub=search)

  The key guiding questions that will help preprocess and shape this dataset are:
  1) What is the survivability rate for different demographics(race), in the SEER datasets
  2) What is the survivability rate of breast cancer in Canada vs USA
  3) What is the survivability rate of Married vs Un-Married(Single, Divorced, Widowed) pateients


## Data pre-processing:
  ### Calculating overall survivability rate of patients
  1) First read the datasets using the read_csv() function of pandas.
  2) Get a brief of the dataset using the head/tail function.
  3) The describe function gives us the count, mean, standard deviation, the quantiles and min and max of the dataset.
  4) Check for missing values using the .isna() which returns a boolean. Calling the sum() on the boolean values gives us the sum of missing values.
     ![image](https://github.com/user-attachments/assets/14777c0a-ba26-4f72-89db-3bd1f8f8e7c6)
  5) It is clear that the cloumn 'Unnamed: 3' has no values and can be omitted.
  6) Use the drop() in pandas to remove the column from the dataframe.
     ![image](https://github.com/user-attachments/assets/7109909e-83fc-4d12-9838-223f13893062)
  7) Use the shape coulmn to verify that the coulmn has been removed.
  8) Further inspect the column to check the data types. We may run into roadblocks if we try to perform numerical operations on categorical values.
     ![image](https://github.com/user-attachments/assets/9a5a7976-c481-4254-9225-7c5692151399)
  9) A simple way to do this is to use the columns method on the data frame and iterate through each of them, calling the .dtype individually.
  10) THe next step, as per the guiding question defined, is to calculate the survivability rate of the patients.
  11) We can see that the column 'Status' has data type object, meaning we cannot use numerical methods to calculate the rate.
  12) Using the .replace method on the Status column, we replace 'Alive' with 1 and 'Dead' with 0 along with using the astype(int). Converting the column into a numerical data type.
      ![image](https://github.com/user-attachments/assets/88a7ee0d-ac87-487c-b7a5-edb515aafe58)
      
  ### Calculating overall survivability rate of patients based on race
  1) 
