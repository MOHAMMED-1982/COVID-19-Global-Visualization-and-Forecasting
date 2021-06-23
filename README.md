# COVID-19 Time Series Analysis & Forecasting

The current pandemic caused by the COVID-19 virus has affected the socioeconomic circumstances of numerous people globally. The purpose of this project will be to analyze the time series and forecast outcomes of the pandemic.

![](Capstone%203%20(Modeling)/Geographical%20Scatterplot.PNG)

### **1. Data**

The Johns Hopkins dataset from Kaggle. This dataset is real and is curated from several different, notable health organizations such as WHO, ECDC, and US CDC. This dataset has daily level information on the number of affected cases, deaths and recovery from 2019 novel coronavirus. Also, this is a time series data and so the number of cases on any given day is the cumulative number. The data is available from 22 Jan, 2020 and goes on till 09/23/2020.

> * [Kaggle](https://www.kaggle.com/sudalairajkumar/novel-corona-virus-2019-dataset)

### **2. Data Wrangling**

* I explored the data to see the type of data for each column, the size of the data, and checked the dataset for missing values. The dataset contains a total of 116805 entries and 7 columns. Overall, there are no missing values other than the Province/State column. This can be due to several factors such as the country not having any provinces or data being recorded for the entire country. For this project, I am just focusing on the data from each country, so it is a good sign that the other columns are not missing any values.
* To start off, I dropped columns which were not necessary, such as ‘Province/State’, ‘Last Updated’, and ‘Sno’. Furthermore, I uploaded a population dataset which had the population for each country. I renamed a few countries in the covid dataset in order for a smooth merge with the population dataset. The population dataset is being used to understand the severity of the covid virus in each country. Just seeing which country has the most number of cases or deaths is not a very efficient way of understanding the data. For a better analysis, the number of cases, deaths, and recovered will be divided by the population, to see which country has the highest density in each case.
* The dataset was also checked for duplicate values.
* Also, there a whole lot of datasets which were used for analysis. There is an entire dataset which records the number of cases and deaths for US counties. 
* After all the data wrangling, the updated dataset was saved for EDA.

### **3. EDA**

* The EDA portion is one of the largest portions of this project due to the variety of datasets provided by Johns Hopkins University. This section analyzes global data and US states data.
* **Step 1:** Created Time Series Plots to visualize the Top 10 countries with the most confirmed, deaths, and recovered.

![](Capstone%203%20(EDA)/Time%20Series%20of%20Top%2010%20Confirmed.PNG)

![](Capstone%203%20(EDA)/Time%20Series%20of%20Top%2010%20Deaths.PNG)

![](Capstone%203%20(EDA)/Time%20Series%20of%20Top%2010%20Recovered.PNG)

* **Step 2:**  Created Choroplethmaps and ranking for all the cases (confirmed, recovered, deaths, active) and their density globally.

  - **Confirmed**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20confirmed.PNG)

  ![](Capstone%203%20(EDA)/Rank%20map%20of%20confirmed.PNG)
  
  - **Confirmed per Million**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20confirmed%20per%20million.PNG)
  
  ![](Capstone%203%20(EDA)/Rank%20map%20of%20confirmed%20per%20million.PNG)
  
  - **Deaths**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20deaths.PNG)
  
  ![](Capstone%203%20(EDA)/Rank%20map%20of%20deaths.PNG)
  
  - **Deaths per Million**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20deaths%20per%20million.PNG)
  
  ![](Capstone%203%20(EDA)/Rank%20map%20of%20deaths%20per%20million.PNG)
  
  - **Recovered**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20recovered.PNG)
  
  ![](Capstone%203%20(EDA)/Rank%20map%20of%20recovered.PNG)
  
  - **Recovered per Million**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20recovered%20per%20million.PNG)
  
  ![](Capstone%203%20(EDA)/Rank%20map%20of%20recovered%20per%20million.PNG)
  
  - **Active**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20active.PNG)
  
  ![](Capstone%203%20(EDA)/Rank%20map%20of%20active.PNG)
  
  - **Active per Million**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20active%20per%20million.PNG)
  
  ![](Capstone%203%20(EDA)/Rank%20map%20of%20active%20per%20million.PNG)

* **Step 3:** Created Time Series Plots to visualize the Top 10 US states with the most confirmed, deaths, and recovered.

![](Capstone%203%20(EDA)/Time%20Series%20of%20Top%2010%20US%20States%20confirmed.PNG)

![](Capstone%203%20(EDA)/Time%20Series%20of%20Top%2010%20US%20States%20deaths.PNG)

* **Step 4:** Created Choroplethmaps and ranking for all the cases (confirmed and deaths) and their density for US States.
  - **Confirmed**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20US%20states%20confirmed.PNG)
  
  - **Confirmed per Million**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20US%20states%20confirmed%20per%20million.PNG)
  
  ![](Capstone%203%20(EDA)/US%20states%20rank%20map%20confirmed.PNG)
  
  - **Deaths**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20US%20states%20deaths.PNG)
  
  - **Deaths per Million**
  ![](Capstone%203%20(EDA)/Choropleth%20map%20of%20US%20states%20deaths%20per%20million.PNG)
  
  ![](Capstone%203%20(EDA)/US%20states%20rank%20map%20deaths.PNG)

### **4. Data Preprocessing**
* For this step, I created a dataframe containing confirmed cases for the US from the larger dataset and I also created date time features and lag features which are some classical ways of transforming a time series forecasting problems into supervised learning problems. However, I used the classical approach of using an ARIMA model since machine learning for time series analysis and forecasting is a highly time-consuming method. The datetime features and lag features are basically like creating dummy variables for time series analysis. I also created an expanding windows feature. I did some visualization by creating line plots, a histogram, and a density plot.
* I also created box and whisker plots and heat maps. I did this by monthly interval and daily interval for the month of September. 
* I also created a Lag Scatter plot. It’s linear characteristic shows that the data is not random and has high autocorrelation.

![](Capstone%203%20(Data%20Preprocessing)/Lag%20Scatter%20Plot.PNG)

* I also created an autocorrelation plot to see the correlation of the data for each day. Although it shows a decreasing correlation in the first couple of months, the line plot shows that the data was stationary for the first couple of months.
* I also decomposed the time series to identify any trends with the data. There seems to be no trend since there is only a year of data available and it’s a virus. Most of the actions are taken to reduce the virus.

![](Capstone%203%20(Data%20Preprocessing)/Seasonal%20Decompose.PNG)

### **5. Modelling**
* The Modelling step really focuses on preparing the data for forecasting. 

* Step 1:
  - The dataset was split into a training and validation dataset. Then the original dataset was split halfways and was used for a walk-forward validation, which uses the      training dataset to predict and the testing dataset to observe. 
  
* Step 2:
  - The training dataset was used to create a persistence model. Like the last step it was split halfways in a training set and test set. After the predictions were made, the model observed a RMSE of 28464.926, meaning that on average, the model was wrong by about 28465 confirmed cases for each prediction made. It may not seem like a big number, but it is a big error for such a weak model

* Step 3:
  - I manually configured the ARIMA model to check the stationarity of the training dataset.
  - After the configuration I found that the test statistic value -0.497328 is greater than the critical value at 5% of -2.881. Thus, we can reject the null hypothesis, meaning that the time series is non-stationary. It also makes sense that the time series is non-stationary since the data is not random and it has a high autocorrelation.
  
  ![](Capstone%203%20(Modeling)/Test%20Statistic.PNG)
 
* Step 4:
  - I ended up using Grid Search to find the optimal hyperparameters to be used in my ARIMA model for forecasting and found the best hyperparameter to be ARIMA(6, 2, 0) with a RMSE of 3230.321.
  - I also reviewed the residual errors.

* Step 5:
  - I used the Box-Cox transform to perform square root and log transforms and automatically optimize the transform for a dataset.
  
  ![](Capstone%203%20(Modeling)/Box%20Cox.PNG)
  
 * Step 6:
  - This entire step is getting the data ready for forecasting.
  - I finalized the model by applying ARIMA on the transformed data with an order of (6, 2, 0). Then I saved the model into separate datasets.
  - I made a prediction from the training dataset. The prediction was made for the next day and it was 2847059.243. This value was then used to compare with the first value in the validation dataset to check how accurate the prediction was.
  - I validated the model by checking the first value which was 2839436. The RMSE was 8102.135. So, it was not too far off and the predictions made from the training dataset almost matched up with the data from the validation dataset which means the model performed well.

  ![](Capstone%203%20(Modeling)/Prediction.PNG)
