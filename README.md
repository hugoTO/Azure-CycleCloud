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