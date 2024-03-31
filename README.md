

# Weather Data Retrieval: API call, ETL pipeline, data lake

## Table of Contents
1. [Introduction](#1-introduction)
   - [Technologies used](#technologies-used)
3. [Implementation Overview](#2-implementation-overview)
4. [Design](#3-design)

## 1. Introduction 
An API call is a request made by one software application to another, typically over a network, to access its functionality or retrieve data. It enables different software systems to communicate and interact with each other, facilitating integration and interoperability.

This project features an automatic system that gathers data from a third party source (open weather) and store in a data lake that will be use later for other purpose. This gathering of data occurs daily to update on current day weather data. This can be useful for companies or individual who needs to use daily weather data for their purpose (for example: weather forecast or make decisions based on current weather conditions like airflight control)

<b>Open Weather API: </b> [https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset?resource=download](https://openweathermap.org/api)

Data includes a single csv file : <b> <i> Telco_customer_churn.csv </i> </b>

### Technologies used
- Python
- Airflow
- AWS services: EC2, S3

## 2. Implementation overview 
An ETL pipeline to collect raw data from Open Weather API. After that, the data is transform to fit with csv format and remove redundant information. Afterward, the data is loaded to Amazon s3 Data Lake.
![architecture](https://github.com/minWang916/weatherDataRetrieval/assets/116493016/1eaeef81-7168-44a5-ba58-fd7242811d4e)





## 3. Design 

#### Airflow system
![graph](https://github.com/minWang916/weatherDataRetrieval/assets/116493016/b27a011e-ece6-48c7-8dce-5ee1d4b36e29)






