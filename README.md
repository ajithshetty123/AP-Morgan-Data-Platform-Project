# AP-Morgan-Data-Platform-Project
Multiple internal applications sends the data (huge volume) in CSV format on daily basiss, in the cloud storage location. There are couple of data/schema validations 
needed to be performed on incoming data. Once everything is passsed data to be persisted as Delta table in Databricks for docuentation purpose.

#High Level design
1) Internal applications sends csv files in Azure data lake storage
2) Validations needed to be applied on this as follows
   a)Check for duplicate rows, if it contains duplicate rows then file need to be rejected
   b)Need to validate the date format for all the fields.Date column name and desired date format  is stored in a Azure SQL server. If validations fails file will be 
     rejected.
3) Move all rejected files to rejet folder 
4) Move all passed files to a staging folder
5) Write the passed files as Delta table in Azure databricks


<img width="500" alt="Archiecture" src="https://user-images.githubusercontent.com/100984374/217887762-47ea7af6-4ade-4bb7-8eec-e00e25a9dab9.PNG">

