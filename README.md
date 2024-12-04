# Football Stadiums Data Engineer

This python-based project crawls data from https://en.wikipedia.org/wiki/List_of_association_football_stadiums_by_capacity using Azure Databricks, cleans it and pushes it Azure Data Lake for processing. Later on we will be visualising the data via Power BI to gain business insights.

## Table of contents

1. [System Architecture](#system-architecture)
2. [Requirements](#requirements)
3. [Web Crawling](#how-it-works)
4. [Azure](#video)
5. [Power BI](#video)
6. [Video](#video)

## System Architecture
![system_architecture](https://github.com/user-attachments/assets/7afa1916-d20e-4151-9be5-95840d77fa98)

## Requirements

## Web Crawling
1. We open a terminal inside Databricks. We execute this commands: 
```
touch requirements.txt
nano requirements.txt
```
Se pega el contenido del fichero requirements.txt del repositorio.
Una vez pegado y guardado el archivo, se ejecuta:

pip install -r requirements.txt

Esto instalará las dependencias necesarias
NOTA: hay más dependencias de las necesarias.

Al ejecutar el notebook, extraerá los datos de la wikipedia, y limpiará los datos, convirtiendolos posteriormente en un DataFrame.

El Dataframe se guarda en un contenedor del Datalake. Se debe cambiar la clave de acceso y el nombre del contenedor dependiendo del datalake storage.

Una vez ejecutado, se verá el fichero con el contenido de todos los estadios.



