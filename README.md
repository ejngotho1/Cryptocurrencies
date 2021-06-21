# Cryptocurrencies

## Overview of Project

Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

## Deliverables:

1. ***Deliverable 1:*** Preprocessing the Data for PCA
2. ***Deliverable 2:*** Reducing Data Dimensions Using PCA
3. ***Deliverable 3:*** Clustering Cryptocurrencies Using K-means
4. ***Deliverable 4:*** Visualizing Cryptocurrencies Results


## Deliverables:
### Resources

* Data Source: `crypto_data.csv`
* Data Tools:  `crypto_clustering_starter_code.ipynb`.
* Software: `Python 3.9`, `Visual Studio Code 1.50.0`, `Anaconda 4.8.5`, `Jupyter Notebook 6.1.4` and `Pandas`

### Unsupervised Machine Learning and Cryptocurrencies
#### Using Unsupervised Learning to Discover Unknown Patterns

##### Challenges of Unsupervised Learning

**IMPORTANT**
> Unsupervised learning isn't the solution for every data analytic challenge. Just because supervised learning might not work for one situation doesn't mean unsupervised learning will work instead. Understanding the data and what can be done with it is an important first step before choosing an algorithm.

Recall that unsupervised learning does not take in any pairing of input and outcomes from the data—it only looks at the data as a whole. This can cause some challenges when running the algorithm. Since we won't know the outcome it's predicting, we might not know that the result is correct.

This can lead to issues where we're trying to decide if the model has provided any helpful information that we can use to make decisions in the real world. For example, our store owner might run a model that ends up grouping the type of people by how much they're buying. This could be useful in some contexts—for example, knowing who the top spenders are—but it might not help the store owner better organize the store for maximum purchases per person, or understand the differences in product preferences between top purchasers.

The only way to determine what an unsupervised algorithm did with the data is to go through it manually or create visualizations. Since there will be a manual aspect, unsupervised learning is great for when you want to explore the data. Sometimes you'll use the information provided to you by the unsupervised algorithm to transition to a more targeted, supervised model.

As with supervised learning, data should be preprocessed into a correct format with only numerical values, null value determination, and so forth. The only difference is unsupervised learning doesn't have a target variable—it only has input features that will be used to find patterns in the data. It's important to carefully select features that could help to find those patterns or create groups.

The next section will cover data preprocessing and data munging, and provide a refresher on Pandas and data cleaning. First, you'll need to install the necessary libraries for practice.

##### Install Your Tools
Install the tools that were not installed in other modules

##### Scikit-learn

Run the following command:

`conda install scikit-learn`

##### Plotly

Run the following command:

`conda install plotly`

##### hvPlot

Run the following command:

`conda install -c pyviz hvplot`

##### Steps for Preparing Data
**After** digging into unsupervised learning a bit, you realize that your first step in convincing Accountability Accountants to invest in cryptocurrency is to preprocess the data.

You and Martha open up the dataset to get started preprocessing it. Together, you will want to manage unnecessary columns, rows with null values, and mixed data types before turning your algorithm loose.

##### Data Selection
Before moving data to our unsupervised algorithms, complete the following steps for preparing data:

1. Data selection
2. Data processing
3. Data transformation

Data selection entails making good choices about which data will be used. Consider what data is available, what data is missing, and what data can be removed. For example, say we have a dataset on city weather that consists of temperature, population, latitude and longitude, date, snowfall, and income. After looking through the columns, we can readily see that population and income data don't affect weather. We might also notice some rows are missing temperature data. In the data selection process, we would remove the population and income columns as well as any rows that don't record temperatures.

##### Data Processing
Data processing involves organizing the data by formatting, cleaning, and sampling it. In our dataset on city weather, if the date column has two different formats—mm-dd-yyyy (e.g., 01-23-1980) and month-data-year (e.g., jan-23-1980)—we would convert all dates to the same format.

##### Data Transformation
Data transformation entails transforming our data into a simpler format for storage and future use, such as a CSV, spreadsheet, or database file. Once our weather data is cleaned and processed, we would export the final version of the data as a CSV file for future analysis.

# Deliverable 1:  
## Preprocessing the Data for PCA
### Deliverable Requirements:

Using your knowledge of Pandas, you’ll preprocess the dataset in order to perform PCA in Deliverable 2

**Follow the instructions below:**

Follow the instructions below and use the `crypto_clustering_starter_code.ipynb` file to complete Deliverable 1.

Open the `crypto_clustering_starter_code.ipynb` file, rename it `crypto_clustering.ipynb`, and save it to your **Cryptocurrencies** GitHub folder.

1. Read in the `crypto_data.csv` to the Pandas DataFrame named `crypto_df`.

**NOTE**
The `crypto_data.csv` was retrieved from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist).

2. Keep all the cryptocurrencies that are being traded.
3. Keep all the cryptocurrencies that have a working algorithm.
4. Drop the `IsTrading` column.
5. Remove rows that have at least one null value.
6. Filter the `crypto_df` DataFrame so it only has rows where coins have been mined.
7. Create a new DataFrame that holds only the cryptocurrency names, and use the crypto_df DataFrame index as the index for this new DataFrame.
8. Remove the `CoinName` column from the `crypto_df` DataFrame since it's not going to be used on the clustering algorithm.

Cryptocurrency df will look like this

![image](https://user-images.githubusercontent.com/57301554/122838024-c7a28900-d2ba-11eb-9586-32f9fa6062e7.png)


9. Use the `get_dummies()` method to create variables for the two text features, `Algorithm` and `ProofType`, and store the resulting data in a new DataFrame named `X`.
10. Use the StandardScaler `fit_transform()` function to standardize the features from the `X` DataFrame.

**IMPORTANT**
Using the `StandardScaler()` sklearn library to standardize the features is required before attempting Deliverables 2 and 3.

Save your `crypto_clustering.ipynb` file to your **Cryptocurrencies** folder.

#### Deliverable 1 Requirements

* The following six preprocessing steps have been performed on the `crypto_df` DataFrame:
    - All cryptocurrencies that are not being traded are removed
    - All cryptocurrencies that do not have a defined algorithm are removed
    - The `IsTrading` column is dropped 
    - All the rows that have at least one null value are removed 
    - All the rows that do not have coins being mined are removed 
    - The `CoinName` column is dropped
* A new DataFrame is created that stores all cryptocurrency names from the CoinName column and retains the index from the `crypto_df` DataFrame 
* The `get_dummies()` method is used to create variables for the text features, which are then stored in a new DataFrame, `X` 
* The features from the `X` DataFrame have been standardized using the StandardScaler `fit_transform()` function 

### DELIVERABLE RESULTS:
## Deliverable 1
### Preprocessing the Data for PCA
The following was done to preprocess the data:

1. Remove cryptocurrencies not being traded.

![image](https://user-images.githubusercontent.com/57301554/122838308-6dee8e80-d2bb-11eb-9c1c-0dfd8e67e012.png)

3. Keep all the cryptocurrencies that have a working algorithm

![image](https://user-images.githubusercontent.com/57301554/122838338-7e066e00-d2bb-11eb-8425-17a895d76840.png)

5. The `IsTrading` column it was dropped.

![image](https://user-images.githubusercontent.com/57301554/122838370-8fe81100-d2bb-11eb-927f-242dd5a8b23f.png)

7. Rows that have null value were dropped.

![image](https://user-images.githubusercontent.com/57301554/122838388-9d050000-d2bb-11eb-9c10-765a54d8f17b.png)

9. Filter dataset with only mined coins.

![image](https://user-images.githubusercontent.com/57301554/122838422-adb57600-d2bb-11eb-8fdd-97c9f1ece0fd.png)

11. Create a new DataFrame `CoinNames`, and use the index from the previous dataset as the index for this new DataFrame `cc_names_df`  

![image](https://user-images.githubusercontent.com/57301554/122838265-4f889300-d2bb-11eb-8837-91eec0132ff3.png)














