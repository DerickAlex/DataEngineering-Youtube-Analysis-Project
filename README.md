# DataEngineering-Youtube-Analysis-Project

### Introduction
In this project, I Built an ETL(Extract,Transform,Load) pipeline using a Dataset from Kaggle in regards of trending youtube videos. The pipeline will retrieve data from the dataset, transformed it to a desired format(parquet) and load data at the end. After the data has been loaded, a glue crawler will be used to crawl upon to create a glue catalog which will be used later on for analytics in Athena.



## Architecture

![Architecture diagram](https://github.com/DerickAlex/spotify-end-to-end-data-engineering-project/blob/main/Architecture%20Diagram.PNG)

### Dataset Used/API
This dataset includes several months (and counting) of data on daily trending YouTube videos. Data is included for the US, GB, DE, CA, and FR regions (USA, Great Britain, Germany, Canada, and France, respectively), with up to 200 listed trending videos per day. [Dataset-Link](https://www.kaggle.com/datasets/datasnaek/youtube-new).



### Services Used

1. **S3** - Amazon S3 is object storage built to store and retrieve any amount of data from anywhere. S3 is a simple storage service that offers industry leading durability, availability, performance, security, and virtually unlimited scalability at very low costs.
2. **AWS Lambda** - AWS Lambda is a serverless, event-driven compute service that lets you run code for virtually any type of application or backend service without provisioning or managing servers.
3. **CloudWatch** -  Amazon CloudWatch collects and visualizes real-time logs, metrics, and event data in automated dashboards to streamline your infrastructure and application maintenance.
4. **Glue Crawler** -  A crawler is a job defined in Amazon Glue. It crawls databases and buckets in S3 and then creates tables in Amazon Glue together with their schema.Then, you can perform your data operations in Glue, like ETL.
5. **Data Catalog** - A data catalog uses metadata—data that describes or summarizes data—to create an informative and searchable inventory of all data assets in an organization.
6. **Amazon Athena** -  Amazon Athena enables users to analyze data in Amazon S3 using Structured Query Language (SQL). The tool is designed for quick, ad hoc and complex analysis


