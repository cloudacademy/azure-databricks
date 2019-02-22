# Running Spark on Azure Databricks
This file contains code from the demos in Cloud Academy's _Running Spark on Azure Databricks_ course.  

### Introduction
[Azure Free Trial](https://azure.microsoft.com/free)  

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

### Training a Machine Learning Model
MNIST notebook: https://docs.azuredatabricks.net/spark/latest/mllib/decision-trees.html#decision-trees

Print decision tree accuracy:
```
import org.apache.spark.ml.evaluation.MulticlassClassificationEvaluator
val evaluator = new MulticlassClassificationEvaluator().setLabelCol("indexedLabel").setMetricName("weightedPrecision")
val prediction = model.transform(test)
println(s"accuracy = ${evaluator.evaluate(prediction)}")
```

### Deploying a Trained Model
AzureML notebook: https://github.com/Azure/MachineLearningNotebooks/blob/master/how-to-use-azureml/azure-databricks/Databricks_AMLSDK_1-4_6.dbc

### Conclusion
Azure Databricks documentation: https://docs.azuredatabricks.net/  
Support: support@cloudacademy.com
