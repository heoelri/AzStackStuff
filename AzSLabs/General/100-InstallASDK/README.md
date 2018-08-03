# Install ASDK on Bare Metal
Microsoft provides a great, up-to-date documentation on how to deploy the Azure Stack Development Kit (ASDK). Here's an overview of all related resources and steps.

## Step 1 - Download and Extract the ASDK
First step is to check the prerequisites, download and extract the ASDK.

Please follow the instructions here:
 * [Download and extract the ASDK](https://docs.microsoft.com/en-us/azure/azure-stack/asdk/asdk-download)

This will explain how to check the underlaying hardware, download the ASDK and extract it.

## Step 2 - Prepare the ASDK host computer
The second step is to prepare the ASDK host computer for the upcoming installation. When you've downloaded the ASDK directly to your machine or transfered it to this machine, the next step is to start the deployment.

 * [Prepare the ASDK host computer](https://docs.microsoft.com/en-us/azure/azure-stack/asdk/asdk-prepare-host)

Main objective here is to download the ASDK Installer (GUI). The installer user interface for the Azure Stack Development Kit is an open-sourced script based on WCF and PowerShell.

## Step 3 - Using ASDK Installer to install the ASDK
The ASDK can be deployed completly using PowerShell - our recommendation is to use the ASDK installer.

 * [Install the Azure Stack Development Kit (ASDK)](https://docs.microsoft.com/en-us/azure/azure-stack/asdk/asdk-install)

And the end of this step you've rebooted your host at least once and started the deployment. This will take 4-6 hours.
