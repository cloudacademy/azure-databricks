# Running Spark on Azure Databricks
This file contains code from the demos in Cloud Academy's _Running Spark on Azure Databricks_ course.  

### Notebooks
```
%fs ls
%fs ls databricks-datasets
%fs head --maxBytes=1000 dbfs:/databricks-datasets/Rdatasets/data-001/csv/Ecdat/Computers.csv
```
```
DROP TABLE IF EXISTS computers;

CREATE TABLE computers
  USING csv
  OPTIONS (path "/databricks-datasets/Rdatasets/data-001/csv/Ecdat/Computers.csv", header "true", inferSchema "true")
```

### Summary
Azure Databricks documentation: https://docs.azuredatabricks.net/  
Support: support@cloudacademy.com
