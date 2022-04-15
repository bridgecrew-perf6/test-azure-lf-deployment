# ARM Template that builds an Active Directory Domain Controller


<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnurollinsiii%2Ftest-azure-lf-deployment%2Fmain%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

This module creates an Active Directory Domain Controller with a new forest, domain and DC.

This is an experimental module at the moment...

## Parameters

| Name | Type | Required | Description |
| :------------- | :----------: | :----------: | :------------- |
| adminUsername | string | Yes | The name of the administrator account of the new VM and domain.|
| adminPassword | securestring | Yes | The password for the administrator account of the new VM and domain.|
| domainName | string | Yes | The FQDN of the Active Directory Domain to be created.|
| dnsPrefix | string | No | The DNS prefix for the public IP address used by the Load Balancer.|
| vmSize | string | No | Size of the VM for the controller.|
| _artifactsLocation | string | No | The base URI where artifacts required by this template are located. When the template is deployed using the accompanying scripts, a private location in the subscription will be used and this value will be automatically generated.|
| _artifactsLocationSasToken | securestring | No | The sasToken required to access _artifactsLocation.  When the template is deployed using the accompanying scripts, a sasToken will be automatically generated.|
| location | string | No | Specifies the Azure location where the resources will be created. |
| virtualMachineName | string | No | The name of the AD Virtual Machine.|
| virtualNetworkName | string | No | The name of the virtualNetwork.|
| subnetName | string | No | The name of the subnet.|
| virtualNetworkAddressRange | string | No | Virtual network address range.|
| privateIPAddress  | string | No | Private IP Address of the DNS server.|
| subnetRange  | string | No | Subnet IP range.|

## Outputs

| Name | Type | Description |
| :------------- | :----------: | :------------- |
| dnsIpAddress | string | The IP address of the DNS server. The value of the privateIpAddress parameter. |
| domainName | string | The FQDN of the domain. The value of the domainName parameter. |
| virtualNetworkSubscriptionId | string | SubscriptionId of the virtualNetwork. The value of subscription().subscriptionId. |
| virtualNetworkResourceGroupName | string | Name of the resourceGroup for the virtualNetwork.  The value of resourceGroup().name |
| virtualNetworkName | string | Name of the virtualNetwork.  The value of the virtualNetworkName parameter. |
| subnetName | string | The name of the subnet.|
| virtualNetworkAddressPrefixes | array | Address ranges for the virtualNetwork. The value of the virtualNetworkAddressRanges parameter. |

```apiVersion: n/a```
