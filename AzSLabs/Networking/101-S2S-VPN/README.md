Goto the 201-site-to-site Template on Azure Quick Start Templates on [GitHub](https://github.com/Azure/azure-quickstart-templates/tree/master/201-site-to-site-vpn).

> This template will create a Virtual Network, a subnet for the network, a Virtual Network Gateway and a Connection to your network outside of Azure (defined as your local network). This could be anything such as your on-premises network and can even be used with other cloud networks such as AWS Virtual Private Cloud. It also provisions an Ubuntu instance attached to the Azure Virtual Network so that you can test connectivity.

Copy the content of **azuredeploy.json** in 201-site-to-site-vpn Template and create a new Template Deployment in Azure Stack.



 1. Click on "+ New" and search for Template Deployment.
 2. Copy the content into the code editor
 3. Click "Save"
 4. Click "Edit Parameters" to modify the parameters
 5. Insert the following parameters
 

| __Parameter__ | __Value__ | 
| ------------- | --------- |
| VPNTYPE | RouteBased | 
| LOCALGATEWAYNAME | localgateway |
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
| ADMINPASSWORD | P@ssw0rd1 |
| NEWSTORAGEACCOUNTNAME | leftstorage |
| STORAGEACCOUNTTYPE | Standard_LRS |

