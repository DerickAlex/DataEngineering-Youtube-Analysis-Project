# DataEngineering-Youtube-Analysis-Project

### Introduction
In this project, I Built an ETL(Extract,Transform,Load) pipeline using a Dataset from Kaggle in regards of trending youtube videos. The pipeline will retrieve data from the dataset, transformed it to a desired format(parquet) and load data at the end. After the data has been loaded, a glue crawler will be used to crawl upon to create a glue catalog which will be used later on for analytics in Athena.



## Architecture

![Architecture diagram](https://github.com/DerickAlex/DataEngineering-Youtube-Analysis-Project/blob/main/architecture.jpeg)

### Dataset Used/API
This Kaggle dataset contains statistics (CSV files) on daily popular YouTube videos over the course of many months. There are up to 200 trending videos published every day for many locations. The data for each region is in its own file. The video title, channel title, publication time, tags, views, likes and dislikes, description, and comment count are among the items included in the data. A category_id field, which differs by area, is also included in the JSON file linked to the region.[Dataset-Link](https://www.kaggle.com/datasets/datasnaek/youtube-new).



### Services Used

1. **S3** - Amazon S3 is object storage built to store and retrieve any amount of data from anywhere. S3 is a simple storage service that offers industry leading durability, availability, performance, security, and virtually unlimited scalability at very low costs.
2. **AWS Lambda** - AWS Lambda is a serverless, event-driven compute service that lets you run code for virtually any type of application or backend service without provisioning or managing servers.
3. **CloudWatch** -  Amazon CloudWatch collects and visualizes real-time logs, metrics, and event data in automated dashboards to streamline your infrastructure and application maintenance.
4. **Glue Crawler** -  A crawler is a job defined in Amazon Glue. It crawls databases and buckets in S3 and then creates tables in Amazon Glue together with their schema.Then, you can perform your data operations in Glue, like ETL.
5. **Data Catalog** - A data catalog uses metadata—data that describes or summarizes data—to create an informative and searchable inventory of all data assets in an organization.
6. **Amazon Athena** -  Amazon Athena enables users to analyze data in Amazon S3 using Structured Query Language (SQL). The tool is designed for quick, ad hoc and complex analysis
7. **IAM** - AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources
8. **Quicksight** - Amazon QuickSight is a cloud-scale business intelligence (BI) service that you can use to deliver easy-to-understand insights to the people who you work with, wherever they are.


### Project Execution Flow
Create an S3 Bucket for Raw Data --> Load data using the CLI commands -->Create a Crawler and Crawl Open the Data --> Create Glue Catalog --> Error with the Json Format(Serde) --> Pre-processing the data --> Json-to-paruqet-transformation --> Run a crawler again --> query in Athena for analytics --> Create a new DB for the Target --> Crate a new Glue Job(Do neccessary transformations such as dropping null fields, and arranging the schema) --> Add a S3 Trigger to Orchestrate --> Create a Glue Job To Join(inner) tables --> Load data to Final Target --> Quicksight for Visualizations

