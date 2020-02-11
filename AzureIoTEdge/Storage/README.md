# IoT Hub Message Routing

If you are creating a connected factory or just creating an IoT sandbox you may want to save your recorded data for further analytisis, AI or just to have the record. 

This can be done using IoT Hub message routing for all your connected devices.

It is simple to get started ...

## Create an Azure Storage Account

First things first, you will need to create a data repositoy, maybe an Azure Storage Account or perhaps an Azure Data Lake.

* Go to your Resource Group and search for "Storage Account".
* Fill the form on the Basis configuration Blade.
* When you are finished with the Basics configuration you can clic on the "Review + Create" button below.
* If you want to create an Azure Data Lake for your solution continue as follows
    * Click on the "Next : Networking" button at the bottom right.
    * Click the "Next : Advanced" button.
    * Then, you will see an options group called "Data Lake Storage Gen2", enable the "Hierarchical namespace" option to create an Azure Data Lake Gen2 storage account.
    * Click "Review + Create" button.
* Once you have reviewed the summary of the Storage Account configuration you may procced to the creation of the resource.

__Note__: There are some difference between a Storage Account and a Data Lake, but the main one is that the distribution of the data that uses a hierarchical namespace which means data analytics loads accelaration and more control on the data security enabling and improved access control with ACLs.
