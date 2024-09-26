# Airline Delay and Cancellation Analysis
In the fast-paced world of air travel, airlines must handle delays and cancellations. The project explores a complex dataset from [Kaggle](https://www.kaggle.com/datasets/yuanyuwendymu/airline-delay-and-cancellation-data-2009-2018?select=2015.csv) with 28 features and 5.81M instances describing diverse aspects of flight information crucial in determining the performance and reliability of air transportation.

## Contents of the repository 
Please refer to the main branch only.  
- `509_EDA.ipynb`: Exploratory Data Analysis notebook with preprocessing strategies.  
- `Airline_Final.csv`: Final dataset after merging datasets and pre-processing.  
- `Airline_Preprocessing.ipynb`: Notebook covering preprocessing for regression and classification tasks.
- `CODE_OF_CONDUCT.md` : Code of conduct document for this repository (NOT ONE OF THE PROJECT DOCUMENTS).
- `FAA_TDI_Report_Final_10_6_10.pdf`: Paper detailing the Total Delay Impact Study.
- `LICENSE`: MIT License for this repository (NOT ONE OF THE PROJECT DOCUMENTS).
- `MATH 509_Project Presentation_Final.pptx`: PowerPoint presentation for the project.  
- `MATH509 Proposal.pdf`: Initial proposal document for the MATH 509 project.
- `MATH509 Report.pdf` : Final report for this project.
- `MATH509_Modelling.ipynb`: Notebook containing the modelling code.  
- `README.md`: README file.
- `Weather_Data_Notebook.ipynb` : Python code used for scraping and using the weather data for the airports.
- `airport_weather_dataset_Updated.csv`: Dataset containing airport weather information.   

## Data
The dataset under consideration comprises diverse features that capture crucial aspects of airline operations and performance.   
Time-related variables, such as scheduled departure and arrival times, actual departure and arrival times, and associated delays, offer an overall understanding of temporal dynamics in flight schedules.   
Specific information related to aircraft, such as carrier details, flight numbers, and diversion indicators, helps identify distinctive patterns for different carriers and instances of unexpected route changes.   
Metrics indicating operational efficiency, like taxi times and elapsed times, provide insights into the effectiveness of ground operations and the total duration of flights.   
Moreover, the dataset details geospatial information, including the origin and destination airports and other influential factors such as the regional weather conditions.   
The classifications for delays, for example, carrier delay, weather delay, and late aircraft delay offer a detailed breakdown of delay factors which enable a detailed analysis of the underlying causes behind disruptions in airline schedules.  

## Research Question and Objectives:   
The primary aim of this research initiative is to delve into the intricate dynamics of historical airline data, unravel the underlying patterns, and identify the multifaceted factors that contribute to delays and cancellations in air travel.  

By thoroughly studying the dataset, we aim to gain insights into the relationships among variables, covering both external factors like weather conditions and internal ones such as airline operations.  
In this study, we will employ advanced statistical and machine learning techniques, with a primary focus on time series analysis and predictive modelling.   
Time series analysis will be a pivotal tool in uncovering temporal patterns and trends within our historical airline dataset, enabling us to discern recurring patterns in delays and cancellations.  
Additionally, predictive modelling will play a central role in our methodology.   
By establishing relationships between the diverse set of features and key outcome variables, such as delays and cancellations, our models aim to quantify the impact of various factors.   
Through this approach, we aspire to develop accurate predictive models that offer valuable insights for airlines and passengers alike.  

## Data Overview

The dataset includes over 5.8 million records and 28 features, covering various aspects of flights, such as departure and arrival times, delays, cancellations, and weather data. Key features include:

| Feature             | Description                                              |
|---------------------|----------------------------------------------------------|
| FL_DATE             | Date of the flight                                        |
| OP_CARRIER          | Airline carrier code                                      |
| DEP_DELAY           | Departure delay in minutes                                |
| ARR_DELAY           | Arrival delay in minutes                                  |
| TAXI_OUT/TAXI_IN    | Taxi times between gate and runway                        |
| WEATHER DELAY       | Delay caused by weather                                   |

## Exploratory Data Analysis (EDA)

We performed an extensive EDA to uncover trends and patterns in flight delays and cancellations. Several visualizations were generated to provide insights into temporal and carrier-specific dynamics.

### Monthly Flight Count
![Flights Count Per Month](<link_to_image>)

*Insight:* The flight counts exhibit seasonal trends, with a clear peak during July, reflecting increased travel demand during the summer. A dip in February suggests lower demand after the holiday season, while the decrease in September corresponds to the shoulder travel season. November sees a slight increase, likely due to holiday travel, followed by a dip in December, reflecting reduced flight activity toward the end of the year.

### Average Departure Delay Per Month
![Average Departure Delay Per Month](<link_to_image>)

*Insight:* Departure delays tend to spike during June and December. These months correspond with high travel periods—summer vacations and year-end holidays—which are often associated with congestion, weather disturbances, and operational strain. The steep drop in September suggests fewer delays due to lower air traffic, providing airlines with more flexibility in operations.

### Departure Delay Over Days of the Week
![Departure Delay Over Day of the Week](<link_to_image>)

*Insight:* Mondays experience the highest average delays, indicating operational challenges at the beginning of the week when travel demand rises after the weekend. Mid-week (Wednesday) shows reduced delays, likely due to lighter travel schedules. A spike is observed on Friday, aligning with increased end-of-week travel. The sharp drop on Saturday can be attributed to lower travel demand, which results in smoother operations and fewer delays.

### Average Departure Delay by Carrier
![Average Departure Delay by Carrier](<link_to_image>)

*Insight:* Airlines like Spirit Airlines (NK) and United Airlines (UA) exhibit the highest average departure delays, suggesting that these carriers may face greater operational challenges or handle a higher volume of flights in congested hubs. In contrast, Alaska Airlines (AS) and Hawaiian Airlines (HA) have significantly lower delays, possibly due to their more streamlined operations, smaller networks, or less congested routes. These disparities highlight the importance of operational efficiency in managing delays.

### Average Departure Delay by Airport
![Top 20 Airports by Average Departure Delay](<link_to_image>)

*Insight:* ILG (Wilmington Airport) shows the highest average departure delay among major airports, indicating that smaller regional airports may face challenges in managing flights. Major hubs like ORD (O’Hare International Airport) and EWR (Newark Liberty International Airport) also show high delays, likely due to congestion and complex flight schedules. Airports like BWI (Baltimore/Washington) perform relatively better, suggesting more efficient operations despite being a major hub.

### Flight Cancellation Reasons
![Flight Cancellation Reasons](<link_to_image>)

*Insight:* Weather-related issues are the leading cause of flight cancellations, emphasizing the significant impact of adverse meteorological conditions on airline operations. Carrier-related cancellations, the second most common, reflect internal airline issues such as crew shortages or maintenance problems. National Airspace System (NAS)-related cancellations further highlight infrastructural challenges. Security-related cancellations, while minimal, underscore the effectiveness of security measures in minimizing disruptions.

## Data Preprocessing

To prepare the dataset for model training, we applied the following steps:
- **Null Value Handling:** Missing values in important features like weather data (e.g., temperature, wind speed) were filled using mean values to maintain data continuity.
- **Feature Engineering:** We extracted temporal features such as 'day of the week' and 'hour of the day' from the flight schedule data. These features capture the temporal variations in delays, such as peak-hour and weekday delays.
- **Feature Scaling:** Standard Scaler was applied to normalize features like weather and flight times, ensuring consistent model performance.

## Modeling Techniques

Four machine learning models were used to predict flight delays:
1. **Logistic Regression**
2. **K-Nearest Neighbors (KNN)**
3. **Random Forest**
4. **XGBoost**

We optimized each model using GridSearchCV for hyperparameter tuning. The performance of each model was evaluated using metrics like accuracy, precision, recall, and F1-score.

## Results and Analysis

### Logistic Regression
![Logistic Regression ROC Curve](<link_to_image>)
*AUROC Score:* 0.66

*Insight:* Logistic regression achieved moderate performance, with an AUROC score of 66%. While the model was able to generalize reasonably well, its performance was limited by its linear nature, which may not capture the complex relationships between features like weather conditions and delays.

### K-Nearest Neighbors (KNN)
![KNN ROC Curve](<link_to_image>)
*AUROC Score:* 0.62

*Insight:* The KNN model struggled with overfitting, as evidenced by the notable gap between the training and cross-validation scores. Despite achieving an AUROC score of 62%, the model’s performance suggests it was overly influenced by noisy data, failing to generalize well on unseen data.

### Random Forest
![Random Forest ROC Curve](<link_to_image>)
*AUROC Score:* 0.67

*Insight:* The Random Forest model performed better than KNN and Logistic Regression, with an AUROC score of 67%. The model effectively handled complex relationships between features due to its ensemble nature, but still exhibited a slight overfitting tendency, as indicated by a small gap between training and validation performance.

### XGBoost
![XGBoost ROC Curve](<link_to_image>)
*AUROC Score:* 0.68

*Insight:* XGBoost outperformed all other models, achieving the highest AUROC score of 68%. Its ability to iteratively improve predictions through boosting allowed it to capture more nuanced patterns in the data, such as the combined effect of weather and flight schedules on delays. The small gap between training and validation performance also indicates minimal overfitting.

## Feature Importance

Using XGBoost’s built-in feature importance function, we generated a plot to highlight the most influential features in predicting flight delays.

![Feature Importance Plot](<link_to_image>)

*Insight:* Weather-related features, such as average temperature, wind speed, and precipitation, were among the most critical factors influencing delays. These insights underscore the significant impact of weather conditions on flight punctuality, particularly in airports subject to frequent adverse weather. Additionally, temporal features such as 'day of the week' and 'hour of the day' also ranked highly, confirming that peak travel periods are prone to higher delays.

## Conclusion

Among the models tested, XGBoost demonstrated the highest predictive accuracy, achieving an AUROC score of 68%. This model successfully captured complex interactions between features like weather conditions and flight schedules, making it a reliable choice for predicting flight delays.

## Recommendations

- **Operational Adjustments:** Airlines should adjust their schedules based on patterns identified in the data, particularly during peak travel periods (summer and holidays) when delays are more frequent.
- **Weather Monitoring:** Incorporating real-time weather monitoring at major hubs could help mitigate delay risks by enabling more proactive decision-making.
- **Resource Allocation:** Airlines should consider optimizing their resources, such as staffing and maintenance, during identified periods of high delays to improve operational efficiency and customer satisfaction.

## Files

The project code and associated files are available in the following notebooks:
- [Exploratory Data Analysis](<link_to_EDA_notebook>)
- [Data Preprocessing](<link_to_preprocessing_notebook>)
- [Modeling](<link_to_modeling_notebook>)
