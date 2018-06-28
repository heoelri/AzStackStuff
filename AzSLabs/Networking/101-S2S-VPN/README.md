# Site-to-Site VPN in Azure Stack

## Overview
Goto the 201-site-to-site Template on Azure Quick Start Templates on [GitHub](https://github.com/Azure/azure-quickstart-templates/tree/master/201-site-to-site-vpn).

> This template will create a Virtual Network, a subnet for the network, a Virtual Network Gateway and a Connection to your network outside of Azure (defined as your local network). This could be anything such as your on-premises network and can even be used with other cloud networks such as AWS Virtual Private Cloud. It also provisions an Ubuntu instance attached to the Azure Virtual Network so that you can test connectivity.

## Prerequisites
 * This lab requires a registered ASDK and Ubuntu 14.04.2-LTS downloaded from the Marketplace.

## Lab

Copy the content of **azuredeploy.json** in 201-site-to-site-vpn Template and create a new Template Deployment in Azure Stack.

 1. Click on "+ New" and search for Template Deployment.
 2. Copy the content into the code editor (Edit Template)
 3. Click "Save"
 4. Click "Edit Parameters" to modify the parameters
 5. Insert the following parameters
 
### Deploy the left side

| __Parameter__ | __Value__ | 
| ------------- | --------- |
| VPNTYPE | RouteBased | 
| LOCALGATEWAYNAME | rightgateway |
| LOCALGATEWAYIPADDRESS | 1.1.1.1 |
| LOCALADDRESSPREFIX | 10.4.0.0/16 |
| VIRTUALNETWORKNAME | leftvnet |
| AZUREVNETADDRESSPREFIX | 10.3.0.0/16 |
| SUBNETNAME | LeftSubnet1 |
| SUBNETPREFIX | 10.3.1.0/24 |
| GATEWAYSUBNETPREFIX | 10.3.200.0/29 |
| GATEWAYPUBLICIPNAME | leftGatewayIP |
| GATEWAYNAME | leftGateway | 
| GATEWAYSKU | basic |
| CONNECTIONNAME | VPN-left-to-right |
| SHAREDKEY | secretkey |
| VMNAME | leftNode1 |
| VMSIZE | Standard_A1 |
| ADMINUSERNAME | adminuser1 |
| ADMINPASSWORD | P@ssw0rd123! |
| NEWSTORAGEACCOUNTNAME | leftstorage |
| STORAGEACCOUNTTYPE | Standard_LRS |

In "Cutom deployment" select your Subscription and create a new Resource group "leftrg".

> We're deploying the left side using a dummy IP address 1.1.1.1 for the remote Gateway. We'll change that IP address in a later step.

**Lookup the Public IP Address of our newly created VPN Gateway**
1. Goto the Tenant Portal
2. Click on "Resource groups" and select "leftrg"
3. Click on "Overview" and "leftGateway" (Virtual Network Gateway)
4. Note your "Public IP address" i.e. 192.168.102.1 and use it as a LOCALGATEWAYIPADDRESS on the right side

### Deploy the right side

| __Parameter__ | __Value__ | 
| ------------- | --------- |
| VPNTYPE | RouteBased | 
| LOCALGATEWAYNAME | leftgateway |
| LOCALGATEWAYIPADDRESS | 1.1.1.1 |
| LOCALADDRESSPREFIX | 10.3.0.0/16 |
| VIRTUALNETWORKNAME | rightvnet |
| AZUREVNETADDRESSPREFIX | 10.4.0.0/16 |
| SUBNETNAME | RightSubnet1 |
| SUBNETPREFIX | 10.4.1.0/24 |
| GATEWAYSUBNETPREFIX | 10.4.200.0/29 |
| GATEWAYPUBLICIPNAME | rightGatewayIP |
| GATEWAYNAME | rightGateway | 
| GATEWAYSKU | basic |
| CONNECTIONNAME | VPN-right-to-left |
| SHAREDKEY | secretkey |
| VMNAME | rightNode1 |
| VMSIZE | Standard_A1 |
| ADMINUSERNAME | adminuser1 |
| ADMINPASSWORD | P@ssw0rd123! |
| NEWSTORAGEACCOUNTNAME | rightstorage |
| STORAGEACCOUNTTYPE | Standard_LRS |

In "Cutom deployment" select your Subscription and create a new Resource group "rightrg". And click on "Create".
