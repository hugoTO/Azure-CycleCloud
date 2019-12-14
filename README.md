# AzureCycleCloud
Azure CycleCloud is an installable web application that you can run on premise or in your Azure subscription. Once installed, CycleCloud can be configured to use compute and data resources in your prepared Azure subscription. CycleCloud provides a number of official cluster templates including schedulers (Grid Engine, Slurm, HTCondor), filesystems (Redis, Avere), containers (Docker, Singularity) and many scientific applications. 

## Pre-requisties
1. Service Principal
    - Azure CycleCloud requires a service principal with contributor access to your Azure subscription. 

    - The simplest way to create one is using the [Azure CLI in Cloud Shell](https://shell.azure.com), which is already configured with your Azure subscription:
        ```
        $ az ad sp create-for-rbac --name CycleCloudApp --years 1
        {
                "appId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                "displayName": "CycleCloudApp",
                "name": "http://CycleCloudApp",
                "password": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
                "tenant": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        }
        ```
        - Save the output -- you'll need the `appId`, `password` and `tenant`. 

    - Alternatively, follow these [instructions to create a Service Principal](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal) 
        -  In this case, the authentication key is the `password`

2. An SSH key

    - An SSH key is needed to log into the CycleCloud VM and clusters
    - Specify a SSH public key, and that will be used in all CycleCloud Clusters as well as the application server.
    - See [section below](#trouble-with-ssh) for instructions on creating an SSH key if you do not have one.

## Deploying Azure CycleCloud
### From the Azure Portal
1. Search Azure CycleCloud in the search bar and find it under Marketplace.
    ![Azure Portal - Marketplace](/images/cyclecloud_marketplace.png)
    
    Select Azure CycleCloud 7.9.x version and click "Create" Button.
    ![Azure CycleCloud](/images/cyclecloud_description.png)
2. Fill the required fields 
    - `Subscription`: Select your own subscription
    - `Resource group`: *CycleCloud-rg*
    - `Virtual machine name`: *cyclevm*
    - `Region`: *East Asia*
    - `Size`: *Standard E4s v3*
    - `Authentication type`: *SSH public key*
    - `Username`: Anyname you like
    - `SSH public key`: Use the public key which is created in pre-requisties step
3. Select **Standard HDD** in Disk page
4. Click **Review + create** button and start the deployment
