# AzureCycleCloud
Azure CycleCloud is an installable web application that you can run on premise or in your Azure subscription. Once installed, CycleCloud can be configured to use compute and data resources in your prepared Azure subscription. CycleCloud provides a number of official cluster templates including schedulers (Grid Engine, Slurm, HTCondor), filesystems (Redis, Avere), containers (Docker, Singularity) and many scientific applications. 

## Pre-requisties
1. Service Principal 
⋅⋅* Azure CycleCloud requires a service principal with contributor access to your Azure subscription.
⋅⋅* The simplest way to create one is using the Azure CLI in Cloud Shell, which is already configured with your Azure subscription: