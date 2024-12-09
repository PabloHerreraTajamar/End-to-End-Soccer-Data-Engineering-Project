
# Football Stadiums Data Engineer

This python-based project crawls data from https://en.wikipedia.org/wiki/List_of_association_football_stadiums_by_capacity using Azure Databricks, cleans it and pushes it Azure Data Lake for processing. Later on we will be visualising the data via Power BI to gain business insights.

## Table of contents

1. [System Architecture](#system-architecture)
2. [Requirements](#requirements)
3. [Web Crawling](#web-crawling)
6. [Azure](#azure)
7. [Power BI](#power-bi)
8. [Video](#video)

## System Architecture
![system_architecture](https://github.com/user-attachments/assets/7afa1916-d20e-4151-9be5-95840d77fa98)

## Requirements
**Accounts:**
  - Databricks
  - Power BI
  - Microsoft

**Technologies:**
  - Azure Datalake Storage Gen 2
  - Azure Databricks
  - Python 3.12
  - Pip
  - Power BI
  - Azure HDInsight
  - Azure Data Factory

## Web Crawling
1. We open a terminal inside Databricks. We execute this commands: 
```bash
touch requirements.txt
nano requirements.txt
```
2. Install the needed dependencies:
```bash
%pip install azure-storage-file-datalake

```
This will copy install all the libraries and dependencies inside requirements.txt
NOTE: there are more libraries and dependencies than the ones you need.

3. When executing the notebook, it will excract and clean all the data from the stadiums from wikipedia, later on saving them into a Dataframe.

4. Finally, the dataframe is saved as a csv inside a container in a datalake. You must change de SSA Key and the name of the container to the ones in your Datalake storage.

## Azure
1. Create a Storage Account
![1](https://github.com/user-attachments/assets/c0f3bec2-4b82-432f-9d4d-64e8bdb9b706)

2. Realize the next configuration:
![2](https://github.com/user-attachments/assets/1becd5e9-4e24-48b1-8c32-24008f430603)

3. In advanced select the option--> Enable hierarchical
![3](https://github.com/user-attachments/assets/55fd5bde-bbd3-4353-bd79-1f23f28345a8)

4. When the storage account had created, go to Data storage/Containers
![4](https://github.com/user-attachments/assets/e3d503d0-bbf7-4511-93b7-4aa97d303282)

5. Create a new container
![imagen (3)](https://github.com/user-attachments/assets/cfa23ab8-9197-40e4-ad9d-73e188657c4f)

6. Open the container
![5](https://github.com/user-attachments/assets/284616c5-a09d-43de-99ee-482007e00422)

7. In the container, Add new Directory
![5 1](https://github.com/user-attachments/assets/5734586e-c132-4010-a409-127bbfd6a2ad)

8. We already have created the Directory
![5 2](https://github.com/user-attachments/assets/15fe9b07-41c5-4e76-a139-42c5a0e28e3c)

9. Return to storage account and open Access key. You need to copy the connection string for upload the cvs on datafactory   
![imagen (5)](https://github.com/user-attachments/assets/35e5afcd-a3db-4584-9336-7edcd5402513)

![9](https://github.com/user-attachments/assets/136ee279-ab95-401f-8ea1-31890bd65904)

![10](https://github.com/user-attachments/assets/fb02bb7f-fb3a-4a6a-8ff2-246b619eabcf)

![11](https://github.com/user-attachments/assets/2bd7ecc4-c319-480d-92b2-e4e38d108dc4)

