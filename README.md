#### Phising Classifiers


#### Description:
---

> Build a Classification to predict whether a website is a Phising website on the basis of given set of predictors.

![image](https://user-images.githubusercontent.com/62303495/115121089-73371080-9fce-11eb-98f5-bee53463f819.png)

![image](https://user-images.githubusercontent.com/62303495/115121176-e3459680-9fce-11eb-8b5e-fad9c0a9a682.png)

> Result:

![image](https://user-images.githubusercontent.com/62303495/115121206-01ab9200-9fcf-11eb-9827-719e476699d1.png)


#### Architecture:
---

![image](https://user-images.githubusercontent.com/62303495/115121249-34ee2100-9fcf-11eb-8e80-ad2c8d7ac732.png)

We have training files, we need to have a DSA agreement which is been provided to the Client. We have Schema file from Client contain information about training files:

Name of the files, Length of Date value in FileName, Length of Time value in FileName, Number of Columns, Name of the Columns, and their datatype.

#### Steps For Training Files: 


> Data Validation:
 - Name Validation
 - Number Of Columns
 - Name Of Columns
 - Data Type of columns
 - Null Value in Columns
      
> Data Insertion in Database
 - Database Create & Connect
 - Table Creation in the Database
 - Data Inserted in the tab;e

All the Steps are done for validating data based on Schema File. If it matches Criteria it   moved to Good Data or else Bad Data Folder 

> Model Training
 - Data Exported from Database
 - Data Preprocessing
 - Cluster the data using K-Means

![image](https://user-images.githubusercontent.com/62303495/115121382-12a8d300-9fd0-11eb-8c0a-961e04f9dfb0.png)

> Model Selection
  
>clusters are created, we find the best model for each cluster. We are using two algorithms, "SVM" and "XGBoost". For each cluster, both the algorithms are passed with the best parameters derived from GridSearch. We calculate the AUC scores for both models and select the model with the best score. Similarly, the model is selected for each cluster. All the models for every cluster are saved for use in prediction

#### Steps For Prediction Files: 

> Client will send the data in multiple set of files in batches at a given location. Data will contain predictors in 30 columns.Apart from prediction files, we also require a "schema" file from client which contains all the relevant information about the training files such as:
Name of the files, Length of Date value in FileName, Length of Time value in FileName, Number of Columns, Name of the Columns and their datatype


#### Deployment:
 
> App been deployed in Pivotal Cloud Foundry Platform.

> Open Postman to check result:

![image](https://user-images.githubusercontent.com/62303495/115121438-69161180-9fd0-11eb-8ebd-51f780ca8d6d.png)

