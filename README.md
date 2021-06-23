# **COVID 19 Global Visualization and Forecasting**

Crime rates are ever growing in the US. This study will analyze which variables are the best predictors of crimes. Analyzing such variables can help alleviate socioeconomic circumstances for communities which experience high crime rates.

![](Capstone%203%20(Modeling)/Geographical Scatterplot.PNG)

### **1. Data**

The dataset is from the UCI Machine Learning Repository. The dataset is real and authentic. It was prepared using real data from socio-economic data from 1990 US Census, law enforcement data from the 1990 US LEMAS survey, and crimedata from the 1995 FBI UCR [13].
UCI Machine Learning Repository contains free datasets which can be used by anyone trying to hone their Machine Learning/Data Science skills. The dataset was originally acquired from Kaggle (another website which hosts Machine Learning competitions) and was cleaned through the various steps of the Capstone.
This dataset contains a total number of 147 attributes and 2216 instances.
For the purposes of the Capstone, only 15 of the attributes were used to see which variable performed as the best predictor of crime rates across the US.

> * [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/communities+and+crime)

> * [Kaggle](https://www.kaggle.com/kkanda/communities%20and%20crime%20unnormalized%20data%20set)


### **2. Data Wrangling**
The Data Wrangling portion features steps in order to get acquainted with the dataset. 
* **Step 1:** All the appropriate features such as unemployment rates, race, education, vacancy, and type of crime were observed, along with basic statistical details such as percentile, mean, max, min, and std. Furthermore, each column was checked for the percentage of missing values. 
* **Step 2:** The dataset's categorical attributes were checked for unique values and any duplicate values under 'communityname'. Communities with the same names were checked which states they are from and were validated that the duplicates belonged to different states. Then the attributes of interest were averaged and grouped by state to see how each attribute differed from state to state. The distributions were also visualized through horizontal bargraphs. Boxplots were also used to visualize the distribution of Violent and NonViolent Crimes for each state.
![](Capstone%20Two%20(Data%20Wrangling)/CrimeBoxPlot.png)

* **Step 3:** The entire dataset was checked for the number of missing values occurring in each column. The attributes of focus were not missing much values. Different methods of dropping the missing values were approached to see which method contained most data (shape of the dataset).
* **Step 4:** Scatter plots were created for the target features to analyze the correlation between the socioeconomic variables and crime variables, in order to gain a premature understanding of which attribute is highly correlated with the occurrence of crime.

### **3. EDA**
The EDA focuses on the relationship between the socioeconomic and crime variables through graphical representation. Histograms were used to visualize the distributions of Violent Crimes, Non-Violent Crimes, and Incomes of different races. Regression Plots were used to visualize the correlation between target variables and crime variables. A heatmap was used to provide a concise way of visualizing the correlation coefficient between all variables.
![](Capstone%20Two%20(EDA)/CrimeHeatmap.png)

### **4. Preprocessing**
The Preprocessing step focuses on cleaning the dataset and creating dummy variables for further analysis. All missing values were dropped rather than filled. Dummy Variables were created for states identifying which state each row is related to. A few regression models were tried on the dataset to see whether the models were working or not. The cleaned dataset was  uploaded into a new csv file for modelling.

### **5. Modelling**
The Modelling step purely focuses on Machine learning. For this process, different Regression models were used on the dataset. The models consist of: Linear Regression, Gradient Boosting, Random Forest, Lasso Regression, Ridge Regression, K Nearest Neighbors, and SVM. The models were fit and tested. Each model was tested twice, once for Violent Crimes and Non Violent Crimes. The scores were compared to see which model did the best. The models were also fit with a cross-validation score to avoid overfitting and estimate the skill of the model on the new data.

* **Violent Crimes:** Linear Regression and Random Forest are the top performers with Violent Crimes as the dependent variable.
![](Capstone%20Two%20(Modelling)/ViolCrimes%20Predictor%20Comparison.PNG)

* **Non Violent Crimes:** Linear Regression and Lasso Regression are the top performers with Non-Violent Crimes as the dependent variable.
![](Capstone%20Two%20(Modelling)/NonViolCrimes%20Predictor%20Comparison.PNG)

The best performing models were fit with optimal hyperparameters to get the R^2 score and cross_val_score. Feature importance for the best performers was also calculated in order to see which variable is the best predictor of crime rates. 
