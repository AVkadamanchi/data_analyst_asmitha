# Project Description
Estimating the project value year to year growth percentage of new buildings in Kengiston between October 2022 and 2023.   
# Objective 
Data Analytical Question Formulation : 
To estimate the project value, what is the year-over-year growth percentage of new buildings constructed in Kensington, the neighbourhood of Vancouver in October between 2022 and 2023? 
This analysis helps the city of Vancouver to identify the growth patterns in new building constructions to plan its urban development strategies, infrastructural changes, and economic development and make data-driven decisions to enhance the quality of services for the residents. 
# Dataset Discovery  
The City of Vancouver’s historical datasets on issued building permits in the years 2022 and 2023 are used for the analysis of the metric. The operational datasets provide information such as:  
Permit Number: The unique ID of the project permit. 
Applicant: Property owner who applied for the building permit.  
Type of Work: The construction type (New building) 
Issue Year: The year the building permit is issued and printed. 
Geo Local Area: The local specification address of the building.  
GEOM: the map coordinates of the property address.  
Project Value: The budget involved in the construction or the value of the building.  
Project Description: The whereabouts of the project like storey type etc. 
# Methodology 
# Data Storage Design

<img width="468" alt="image" src="https://github.com/user-attachments/assets/b3ba4796-930d-4f2f-a5dd-cc9072d5c54f">

The Data Storage Design is designed using the AWS cloud services. The required operational datasets from the City of Vancouver database for the metrics are stored in the S3 storage buckets under the title – IBP_cityofvan_asmitha for further exploration. 
The data identified from the city of Vancouver consists of structured and unstructured data types. The volume of data stored on AWS is used on a weekly, monthly, quarterly and yearly basis. Amazon Cloud Services provides exclusive security measures for monitoring data integrity. The historical datasets on new building permits for October 2022 and October 2023 are stored in the storage structure – Landing. 

# Data Ingestion

<img width="468" alt="image" src="https://github.com/user-attachments/assets/a3716a37-dcb0-455e-b7d0-785aeb18782e">

The operational data set is imported to the Data Analytical platform – AWS. Firstly, the data is inputted into the AWS storage package – S3. Here, we created a storage bucket to upload the operational files to the cloud network.

# Data Storage

<img width="215" alt="image" src="https://github.com/user-attachments/assets/540eb1df-44cd-4edd-81c1-fe8cf7a9543e">

<img width="249" alt="image" src="https://github.com/user-attachments/assets/27176485-cbfb-422a-ad75-9e7ee0b50311">

The Excel format operational datasets are stored in the AWS S3 package. The configuration is as follows.
‘S3 > ibp_cityofvan_asmitha > newbuildings >  2022 & 2023 > landing .’
These datasets are further used by AWS to explore and analyze the defined metrics. 
After data exploration, the AWS packages bifurcate the information in various formats. To make it easy, it is essential to name the storage folders as brief and simple as possible to easily access.

# Data Pipeline Design


![image](https://github.com/user-attachments/assets/f569deeb-a95b-4173-83f7-3493b45a733c)

The data lineage design is the reference for my data analysis pipeline which I will be structuring in AWS using the package- Glue. This is the base structure which helps me to visualize my outputs beforehand to the analysis. The pipeline is the replicate of the ETL for finding the Year over Year growth of building permits/new buildings in Kensington over October from 2022 to 2023.

# Data Cleaning

<img width="468" alt="image" src="https://github.com/user-attachments/assets/bef39565-8ee3-45be-a437-f5ed78e2d3ee">

To get the accurate results of analysis, it is essential to clean the data. There were a few missing values in the datasets I wanted to explore. I used AWS – Glue Databrew to clean by data by filling in the missing rows with the most frequently used value(mode of the column). The cleaning is done on both datasets by importing them from S3 to Glue Databrew.

# Data Structuring

<img width="468" alt="image" src="https://github.com/user-attachments/assets/586f21cb-868b-4a9e-8cfd-2f40a97e2b85">

After cleaning the data, using the AWS Glue Databrew, the data is structure by filling in the null values and renaming the column titles. The data type of the variables has been changed according to perform the ETL pipeline design and analysis.

# Data Pipeline Implementation

<img width="483" alt="image" src="https://github.com/user-attachments/assets/873490e3-08cd-41dd-835b-900c4ab709fe">

The ETL pipeline by AWS Glue helps to visualize the extraction, transformation and Loading of the data to derive the metric. Here, I have used the data which I extracted from the AWS – Databrew. The CSV format data has been imported to the AWS- Glue to perform the analysis. The analysis aims to find the Year-over-year growth metric. Starting with cleaning and structuring the information, it is imported to AWS-Glue from the storage bucket – Raw folder (where the AWS shared the cleaned jobs) to visualize the ETL. In this step, the defined metric is calculated and stored back in the S3 storage service for future use. 

# Data Analysis

<img width="468" alt="image" src="https://github.com/user-attachments/assets/f69217e0-c1ee-46e0-b8d0-fd6ada22efe4">

<img width="468" alt="image" src="https://github.com/user-attachments/assets/5604457d-dce9-4dad-890f-dae43d343af3">

<img width="468" alt="image" src="https://github.com/user-attachments/assets/92e1e77d-e31a-4401-9142-3cb6d5bd8f46">

Using the AWS-Athena, the data analysis is run through the SQL queries to find the YOY of the data.The table is created in the Athena Services, to run the SQL query.

# Data Visualization

<img width="407" alt="image" src="https://github.com/user-attachments/assets/45675c9c-58c8-42ed-a49f-195090111d79">

From the results of ETL, I derived the Year-over-year growth of new buildings built in Kensington from 2022 to 2023. Microsoft Excel is used to visualize the growth in 2023. 
The bar plot is the year-to-year growth of 2023 from 2022 which is 225.69%. 
Further, I have created two files – PDF and CSV formats for Data Publishing. 

# Data Publishing

<img width="216" alt="image" src="https://github.com/user-attachments/assets/088138e1-f417-4ed7-ab59-6b6521535737">

<img width="229" alt="image" src="https://github.com/user-attachments/assets/9bee85b1-7226-462f-b18d-c5cbb0da4b57">

Using the AWS – EC2, the instances for General Server and Webserver were created. 
The General Server is useful to store and use the information internally among the data team. The Webserver gives access to the internet or the residents of the City of Vancouver to view the Year over year growth. The Webserver information is accessible to the users through the web IP address. 

# Data Protection 

 Key Management Service – AWS KMS Key Creation for Encryption

<img width="468" alt="image" src="https://github.com/user-attachments/assets/8a08f81b-7f62-4012-8c1b-352589fa0170">

AWS KMS service provides the encryption and decryption tools to secure the data storage services. It is the key component to use when dealing with sensitive data. This helps in protecting the data from third-party users like AWS or any hackers. This key can be used in other AWS services like S3 to protect the data. The key ‘ ibp-cityofvan-key-asmitha01’ will be further used to decrypt and encrypt the data for security issues.

Default Encryption for S3 bucket

<img width="468" alt="image" src="https://github.com/user-attachments/assets/0cb00aa3-8099-4a99-8915-fb35abee2dc5">

Note: From my analysis of building permits for Vancouver, all my data was stored in the Amazon storage service – S3. Using the key management tool - KMS, I have encrypted the data. To create this function, firstly I sorted the bucket which needs data protection and then using the properties on the storage bucket, I edited and changed the default encryption to make it stronger using the KMS key which was created.

 Replication Rule 

<img width="468" alt="image" src="https://github.com/user-attachments/assets/758ecdaf-35d4-4a28-b054-670ff3938254">

Furthermore, it is necessary to store the usable data as a backup to revise the changes. As the data I am working on is divided among the data team, it is crucial for backup information. Using the replication rule from the management services on storage service S3, I have created a replication rule to copy and update the information automatically to another duplicate storage cloud as a backup.

# Data Governance

Visualization – using AWS Glue

<img width="468" alt="image" src="https://github.com/user-attachments/assets/ea42a2f5-8cd0-4e4d-b0d5-e47549e59169">

Though, the KMS key secures the storage information. It is necessary to ensure the data quality, data protection and security are in place. Using the AWS Glue, I have extracted and loaded the data from the raw folder of S3 to get the required outputs with no issues related to security and quality. 
Firstly, I have detected the sensitive information from the data, using the transform tool – ‘Detect sensitive data’ to mask the private information from data using the REDACT function. This tool masks the sensitive data using ‘*****’. Further on, the data quality check has been done. Using the conditional router and Change Schema functions, the data is manipulated and transformed for easy interpretation. Finally, the cleaned data is stored in the S3 storage cloud in the folder – ‘Trusted’ for future use.

 Data Quality Report – AWS Glue

<img width="468" alt="image" src="https://github.com/user-attachments/assets/1485cf2a-1f6d-4660-8dbb-01307fd81334">

AWS Glue not only enables users to visualize but also check the data quality report. The above screenshot is the quality report of the visualization done. It shows that the statistics in the data have passed and quality check, which represents that the data does not have any security issues or failures.

Trusted folder – S3 service.

<img width="468" alt="image" src="https://github.com/user-attachments/assets/d0dd22af-9512-483c-868e-a58a22775757">

Figure  is the data that has been inputted by the AWS after running the AWS Glue job – ‘ibp-cityofvan-QRPR-asmitha01’. It is stored in Folder – Trusted. 

 Workflow creation & Adaptation using the schedule function

<img width="471" alt="image" src="https://github.com/user-attachments/assets/aeee035f-e606-44df-b9df-441a639f9626">

The workflow has been created to the ETL pipeline to ensure the data quality and protection to enable for future uploads.

# Data Monitoring

 CloudWatch – Dashboard 

<img width="468" alt="image" src="https://github.com/user-attachments/assets/ffd0f337-1452-4027-a234-6d6df284df8b">

CloudWatch enables the data team to monitor and evaluate the data usage. The dashboards help in understanding the total charge and estimated charges incurred on the service usage. The CloudWatch gives elaborative metrics on every metric that has been used throughout the analysis. 
CloudWatch dashboard that is created helps in understanding the 
Estimated Charges: The amount that is charged on using the AWS storage service – S3. 
Call Count: This is the metric which aggregate the total number of calla that are inputted for running the analysis. 
Alarm:‘ibp-alarm-asmitha01’ is enabled to monitor service usage. The limit 35 dollars USD is set for budgeting and limiting for cost efficiency. 

 Trail creation on CloudTrail

<img width="468" alt="image" src="https://github.com/user-attachments/assets/19a2b60f-6474-49b3-889a-86bb70fd6de1">

The CloudTrail service enables the feature to track down the users using the services on AWS. This is a crucial factor as it audits and manages the users and the call history. This helps in evaluating the activities of each individual who is authorised to use the services or the calls done. 

# Tools and Technologies (AWS)
 S3: Object storage for storing and retrieving data.
   
Glue DataBrew is a visual data preparation service that allows you to clean, normalize, and enrich data for analytics and machine learning.

AWS Glue is a serverless data integration service that automatically builds ETL pipelines for data transformation and analysis.
RDS: Managed relational databases.

Athena: Serverless SQL query engine for S3 data.

QuickSight is a cloud-based business intelligence service that provides interactive data visualization and analytics.

IAM: Identity and access management for controlling access to AWS resources.

KMS: Key Management Service for generating, storing, and managing cryptographic keys.

CloudWatch: A monitoring service that provides metrics, logs, and alarms for AWS resources.

CloudTrail: A service that records API calls made to AWS services, providing audit logs for security and compliance.

In conclusion, our project has successfully implemented a steady and efficient Data Analytics Platform via integrating multiple AWS services and making use of quality practices in cloud architecture. By specializing in key areas such as encryption with KMS, facts replication for redundancy, and real-time monitoring with CloudWatch and CloudTrail, we ensured that our answer meets excessive standards of security, operational excellence, and sustainability. The platform's scalability is better through computerized workflows and scheduled approaches, which reduce operational overhead and make sure steady statistics management. We additionally addressed price optimization through using wise features together with S3 bucket key and server-side encryption, which lowered the cost of encryption requests without compromising records.




























