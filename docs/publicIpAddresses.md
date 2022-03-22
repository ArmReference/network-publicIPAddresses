# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
domainNameLabel | No       | Gets or sets the Domain name label.The concatenation of the domain name label and the regionalized DNS zone make up the fully qualified domain name associated with the public IP address. If a domain name label is specified, an A DNS record is created for the public IP in the Microsoft Azure DNS system.
idleTimeoutInMinutes | Yes      | The idle timeout of the public IP address.
name           | Yes      | Resource name.
publicIPAddressVersion | Yes      | The public IP address version. Possible values are: 'IPv4' and 'IPv6'.
publicIPAllocationMethod | Yes      | The public IP allocation method. Possible values are: 'Static' and 'Dynamic'.
sku            | Yes      | Identifies the unique system identifier for each Azure resource.
DependsOn      | No       | Pass dependencies

### domainNameLabel

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Gets or sets the Domain name label.The concatenation of the domain name label and the regionalized DNS zone make up the fully qualified domain name associated with the public IP address. If a domain name label is specified, an A DNS record is created for the public IP in the Microsoft Azure DNS system.

### idleTimeoutInMinutes

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The idle timeout of the public IP address.

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Resource name.

### publicIPAddressVersion

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The public IP address version. Possible values are: 'IPv4' and 'IPv6'.

- Allowed values: `IPv4`, `IPv6`

### publicIPAllocationMethod

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The public IP allocation method. Possible values are: 'Static' and 'Dynamic'.

- Allowed values: `Dynamic`, `Static`

### sku

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Identifies the unique system identifier for each Azure resource.

- Allowed values: `Basic`, `Standard`

### DependsOn

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Pass dependencies

## Outputs

Name | Type | Description
---- | ---- | -----------
publicIPAddresses | object |

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/publicIpAddresses.json"
    },
    "parameters": {
        "domainNameLabel": {
            "value": ""
        },
        "idleTimeoutInMinutes": {
            "value": 0
        },
        "name": {
            "value": ""
        },
        "publicIPAddressVersion": {
            "value": ""
        },
        "publicIPAllocationMethod": {
            "value": ""
        },
        "sku": {
            "value": ""
        },
        "DependsOn": {
            "value": []
        }
    }
}
```

### Command line

#### PowerShell

```powershell
New-AzResourceGroupDeployment -Name <deployment-name> -ResourceGroupName <resource-group-name> -TemplateFile <path-to-template> -TemplateParameterFile <path-to-templateparameter>
```

#### Azure CLI

```text
az group deployment create --name <deployment-name> --resource-group <resource-group-name> --template-file <path-to-template> --parameters @<path-to-templateparameterfile>
```
