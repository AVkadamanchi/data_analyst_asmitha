# Project Description:
Estimating the project value year to year growth percentage of new buildings in Kengiston between October 2022 and 2023.   
# Objective : 
To estimate the project value, what is the year-over-year growth percentage of new buildings constructed in Kensington, the neighbourhood of Vancouver in October between 2022 and 2023? 
This analysis helps the city of Vancouver to identify the growth patterns in new building constructions to plan its urban development strategies, infrastructural changes, and economic development and make data-driven decisions to enhance the quality of services for the residents. 
# Dataset : 
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
The operationala datsets are migrated to the AWS cloud services to perform this analysis. 
1-	Data Collection and Preparation:
The Data Storage Design is designed using the AWS cloud services. The required operational datasets from the City of Vancouver database (Issued Building Permits, 2024) for the metrics are stored in the S3 storage buckets under the title – IBP_cityofvan_asmitha for further exploration.  
The data identified from the city of Vancouver consists of structured and unstructured data types. The volume of data stored on AWS is used on a weekly, monthly, quarterly and yearly basis. Amazon Cloud Services provides exclusive security measures for monitoring data integrity. The historical datasets on new building permits for October 2022 and October 2023 are stored in the storage structure – Landing. 
The datasets of years 2022 and 2023 for October respectively, are imported from the City of Vancouver Open Licence data page. The licensed authorized data of October 2022 consists of 129 records and October 2023 file has 70 records. For the data analysis, the file are exported in Excel format. Both datasets have 20 columns with various information. These datasets are filtered according to key columns for data exploration.
The operational data set is imported to the Data Analytical platform – AWS. Firstly, the data is inputted into the AWS storage package – S3. Here, we created a storage bucket to upload the operational files to the cloud network. 
The Excel format operational datasets are stored in the AWS S3 package. The configuration is as follows. 
‘S3 > ibp_cityofvan_asmitha > newbuildings >  2022 & 2023 > landing .’ 
These datasets are further used by AWS to explore and analyze the defined metrics.  
After data exploration, the AWS packages bifurcate the information in various formats. To make it easy, it is essential to name the storage folders as brief and simple as possible to easily access. 
# Data Pipeline Design:
pipeline.docx


