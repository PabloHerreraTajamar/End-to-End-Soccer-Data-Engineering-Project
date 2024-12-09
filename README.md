
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
2. Inside requirements.txt we add the contents in the file: Requirements/requirements.txt
```bash
pip install -r requirements.txt
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

10. Create a service of Data factories
![9](https://github.com/user-attachments/assets/136ee279-ab95-401f-8ea1-31890bd65904)

11. Configure the options 
![10](https://github.com/user-attachments/assets/fb02bb7f-fb3a-4a6a-8ff2-246b619eabcf)

12. When the service is created, Launch Azure Data Factory Studio 
![11](https://github.com/user-attachments/assets/2bd7ecc4-c319-480d-92b2-e4e38d108dc4)

13. Create a new pipeline
![image](https://github.com/user-attachments/assets/78fd6b95-e753-4c96-abe7-c3972042dd1e)

14. Open the pipeline and select the option --> Copy data
![2](https://github.com/user-attachments/assets/637c576b-c79d-4d2b-9ec5-94bba46bf843)

15. On source, create a new source dataset
![3](https://github.com/user-attachments/assets/c666e650-db0c-4654-927f-78edac8ff33f)

16. select Azure data lake storage gen 2
![4](https://github.com/user-attachments/assets/395bc48e-35b5-4633-ac72-64cfa2c6e207)

17. Select csv format option 
![5](https://github.com/user-attachments/assets/4d0b490e-0e04-4f9f-87d6-9be66a7d33b1)

18. Add new linked server for conect with the data of the container
![6](https://github.com/user-attachments/assets/951c20e0-f9b1-4e97-b0dc-80d6985c0a92)

19. On the options select our storage account 
![7](https://github.com/user-attachments/assets/36a52843-3af1-4319-9aac-0c2cf0cf5bcf)

20. On properties, select the path where you have the csv in the container created 
![8](https://github.com/user-attachments/assets/de5f87ec-6e8d-4750-abd1-1adefca4b4b1)

21. Preview the data to check that it has been loaded correctly  
![9](https://github.com/user-attachments/assets/399fd52f-4f7b-49e3-afd9-2a2064eafd03)

22. we check that they are loaded 
![imagen (8)](https://github.com/user-attachments/assets/88bb6f0c-e425-48f7-a8d2-160a7878e9b6)

23. On sink, create a new dataset 
![11](https://github.com/user-attachments/assets/b4bd5658-085b-468e-bb24-d7ad2335b99e)

24. Select azure data lake storage gen 2
![12](https://github.com/user-attachments/assets/12f2721f-64ee-4441-8112-44faef79bba6)

25. Specify the path for upload the data on directory --> ready 
![14](https://github.com/user-attachments/assets/4640942f-9b86-4489-a06f-a5567c2c167e)

## Power BI

1. Connection
Enter Power BI and go to retrieve data, then click on:
![image](https://github.com/user-attachments/assets/67a29d8e-350c-4baf-ad86-73da062fa66d)
And we select our data table inside Synapse:
![image](https://github.com/user-attachments/assets/09c71b34-1d6d-4d63-a3ab-1563fb16e957)



