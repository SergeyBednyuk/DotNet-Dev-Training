# Create a Virtual Machine

## Short Description

Create a new Virtual Machine and add data disk to the new VM.
[Exercise in sandbox](https://learn.microsoft.com/en-us/training/modules/add-and-size-disks-in-azure-virtual-machines/3-exercise-add-data-disks-to-azure-virtual-machines)

## Estimation (h)

2

## Topics

* Virtual Machines
* Storage

## Requirements

* Create a Linux VM with the following properties by using Azure CLI:
  * The VM's name is support-web-vm01.
  * Its size is Standard_DS1_v2.
  * The admin username is azureuser. In practice, this name can be whatever you like.
  * SSH-keys must be generated.
* Add an empty data disk to VM with the following properties by using Azure CLI:
  * Disk's name is uploadDataDisk1.
  * Size is 64 GB.
  * Use premium storage with local redundancy.
* Initialize and format your data disk:
  * Locate your VM's public IP address
  * Connect via SSH to check that disk is not mounted
  * Use Azure pre-made script to initialize the disk or write it by yourself
  * Connect via SSH to check the disk again
* Cleanup resources
