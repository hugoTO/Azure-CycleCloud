# Standalone NFS Tutorial 

## Create NFS

### Get the NFS template file and import it to CycleCluod

1. Open a terminal session and connect with your CycleCloud Server

2. Download the Template Script **custom-nfs.txt** from this repository

3. You may customize the Template icon and NFS size setting thorough editing the values in **custom-nfs.txt**, or direct use the template script in this github later on

         Name: [cluster "Your Template Name"]

         Number of NFS: Add [[[volume nfs-]]] node

4. Connect to CycleCloud VM

5. Enter the command line in the CycleCloud VM:

Login the CycleCloud with your CycleCloud web interface account

      $ cyclecloud initialize --batch --url=https://localhost --verify-ssl=false --username=[User ID] --password=[Password]

Get the Custom Template script from GitHub, or from your side

      $ wget https://raw.githubusercontent.com/hugoTO/Azure-CycleCloud/master/nfs_standalone_implementation/custom-nfs.txt

Import the template

      $ cyclecloud import_template -f custom-nfs.txt --force


### Get the Cluster Template for NFS and import it to CycleCluod

To import the cluster:

1. Open a terminal session and connect with your CycleCloud Server

2. Download the Template Script **custom-cluster-with-nfs-setting.txt** from this repository, or direct use the template script in this github later on

2. You may customize the Template icon and NFS size setting thorough editing the values in **custom-nfs.txt**

         Name: [cluster "Your Template Name"]

         icon: IconUrl = "Your icon url"

3. Connect to CycleCloud VM

4. Enter the command line in the CycleCloud VM:

Login the CycleCloud with your CycleCloud web interface account

      $ cyclecloud initialize --batch --url=https://localhost --verify-ssl=false --username=[User ID] --password=[Password]

Get the Custom Template script from GitHub, or from your side

      $ wget https://raw.githubusercontent.com/hugoTO/Azure-CycleCloud/master/nfs_standalone_implementation/custom-cluster-with-nfs-setting.txt

Import the template

      $ cyclecloud import_template -f custom-cluster-with-nfs-setting.txt --force

### Create the NFS Server in CycleCloud



