# Download Azure Stack Tools (from GitHub)

```powershell
Get-PSRepository
Set-PSRepository -Name "PSGallery" -InstallationPolicy Trusted 
Get-Module -ListAvailable | where-Object {$_.Name -like “Azure*”} | Uninstall-Module 
```

Install the AzureRM.BootStrapper Module
```powershell
Install-Module -Name AzureRm.BootStrapper 
```

```powershell
# Installs and imports the API Version Profile required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2017-03-09-profile -Force 
# Install Azure Stack Module Version 1.3.0. If running a pre-1804 version of Azure Stack, change the -RequiredVersion value to 1.2.11.
Install-Module -Name AzureStack -RequiredVersion 1.3.0
```

Verify if all modules are sucessfully installed
```powershell
# Lists Modules with word Azure - look for AzureRM and AzureStack
Get-Module -ListAvailable | where-Object {$_.Name -like “Azure*”} 
```

Download and expand the Azure Stack Tools to C:\
```powershell
# Change directory to the root directory 
cd \
# Download the tools archive
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12 
invoke-webrequest https://github.com/Azure/AzureStack-Tools/archive/master.zip -OutFile master.zip 
# Expand the downloaded files
expand-archive master.zip -DestinationPath . -Force 
# Change to the tools directory
cd AzureStack-Tools-master 
```
