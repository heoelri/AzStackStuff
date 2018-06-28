# Register Azure Stack (Development Kit)

## Prerequisites
 * Azure Stack Tools (from GitHub)
 
## Howto

1. Specify the relevant User and domain (AzureAD) for your Subscription
```powershell
$UserName='XXXXXXXX@ASEAIFY18XXX.onmicrosoft.com'
$Password='XXXXXXXX'| ConvertTo-SecureString -Force -AsPlainText
$Credential=New-Object PSCredential($UserName,$Password) 
```

2. Specify the relevant user and domain (Azure Stack) to logon to the Privileged Endpoint
```powershell
$aUserName='CloudAdmin@azurestack.local'
aPassword='XXXXXXXX'| ConvertTo-SecureString -Force -AsPlainText
$cloudAdminCredential=New-Object PSCredential($aUserName,$aPassword) 
```

3. Logon to your Subscription - using the previously specified credentials
```powershell
Login-AzureRmAccount -EnvironmentName "AzureCloud" -Credential $Credential
Register-AzureRmResourceProvider -ProviderNamespace Microsoft.AzureStack 
```

> Note your Subscription ID!

4. Load the Azure Stack Tools Registration Module
```powershell
Import-Module .\Registration\RegisterWithAzure.psm1 -Force -Verbose 
```

```powershell
# Specify the relevant AzureAD tenant
$azureDirectoryTenantName = "ASEAIFY18XXX.onmicrosoft.com"
# Specify the relevant subscription ID (from Step No. 3)
$azureSubscriptionId      = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" # from Login-AzureRMAccount
$privilegedEndpoint       = "AzS-ERCS01" 
```

5. Run the Registration
```powershell
Set-AzsRegistration -PrivilegedEndpoint $privilegedEndpoint -BillingModel Development  -PrivilegedEndpointCredential $cloudAdminCredential 
```

This process can take a few minutes. The result should look like this:
```powershell
VERBOSE: 2018-06-27.10-46-39: Activating Azure Stack (this may take up to 10 minutes to complete).
VERBOSE: 2018-06-27.10-51-25: Your environment is now registered and activated using the provided parameters.
VERBOSE: 2018-06-27.10-51-25: *********************** End log: Set-AzsRegistration ***********************
```
