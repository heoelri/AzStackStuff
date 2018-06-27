Goto Azure Quick Start Templates on [GitHub](https://github.com/Azure/azure-quickstart-templates/tree/master/201-site-to-site-vpn).

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
| LOCALGATEWAYIPADDRESS | |
| LOCALADDRESSPREFIX | |
| VIRTUALNETWORKNAME | leftvnet |
| AZUREVNETADDRESSPREFIX | 10.3.0.0/16 |
| SUBNETNAME | Subnet1 |
| SUBNETPREFIX | |
| GATEWAYSUBNETPREFIX | 10.3.200.0/29 |
| GATEWAYPUBLICIPNAME | leftGatewayIP |
| GATEWAYNAME | leftGateway | 
| GATEWAYSKU | basic |
| CONNECTIONNAME | VPN-left-to-right |
| SHAREDKEY | secretkey |


