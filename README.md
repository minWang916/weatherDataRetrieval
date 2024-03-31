

# Weather Data Retrieval: API call, ETL pipeline, data lake

## Table of Contents
1. [Introduction](#1-introduction)
   - [Technologies used](#technologies-used)
3. [Implementation Overview](#2-implementation-overview)
4. [Design](#3-design)


## 1. Introduction 
An API call is a request made by one software application to another, typically over a network, to access its functionality or retrieve data. It enables different software systems to communicate and interact with each other, facilitating integration and interoperability.

This project features an automatic system that gathers data from a third party source (open weather) and store in a data lake that will be use later for other purpose. This gathering of data occurs daily to update on current day weather data. This can be useful for companies or individual who needs to use daily weather data for their purpose (for example: weather forecast or make decisions based on current weather conditions like airflight control)

<b>Source of data: </b> [https://www.kaggle.com/datasets/yeanzc/telco-customer-churn-ibm-dataset?resource=download](https://openweathermap.org/api)

Data includes a single csv file : <b> <i> Telco_customer_churn.csv </i> </b>

But I split it into 3 seperate files ( <b> <i> Telco_customer_churn1.csv,Telco_customer_churn2.csv,Telco_customer_churn3.csv </i> </b>) to mimic real life usage as there might be multiple data sources and the pipeline should also be able to assemble the data (AWS Glue).

### Technologies used
- Python
- Airflow
- AWS services: EC2, S3, Glue Crawler, Glue Data Catalog, Redshift
- PowerBI 

## 2. Implementation overview 
An ETL pipeline to collect raw data into actionable insights to store them in Amazon S3 for staging. Then implement another Airflow (hosted with EC2) ETL pipeline which process data from S3 and load them to Amazon Glue Crawler for analyzing data structure and schema, which are then stored in Amazon Glue Data Catalog. After that, Airflow delivers the structured data to Amazon Redshift (Data warehouse) and ultimately loaded from there to powerBI for visualization. Amazon Athena is also used for querying data directly from s3 and it is just for checking purpose. 

![System design](https://github.com/minWang916/Batch-processing/assets/116493016/e49939ec-48cd-440c-9d3a-938a690ff270)




## 3. Design 

#### Airflow system
![Untitled](https://github.com/minWang916/Batch-processing/assets/116493016/34bbeb8b-2d04-4919-9507-568b6fbf0ad5)

#### Statistical charts and graphs
![graphs](https://github.com/minWang916/Batch-processing/assets/116493016/4daf2f09-a2d0-4747-8c61-ffc1d410573c)






## 4. Project Structure

```bash

Batch-Processing/
  ├── data/
  │   ├── Telco_customer_churn.csv
  │   ├── Telco_customer_churn.xlsx
  │   │── Telco_customer_churn1.csv
  │   │── Telco_customer_churn2.csv
  │   │── Telco_customer_churn3.csv
  │── customer_churn_dag.py 
  │── requirements.txt  
  │── README.md   

```
<br>
