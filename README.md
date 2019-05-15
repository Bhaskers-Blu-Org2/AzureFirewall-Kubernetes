
ter the name of your ingress subnet
KUBE_AGENT_SUBNET_NAME="aks-subnet" # here enter the name of your AKS subnet
FW_NAME="evill-azfw" # here enter the name of your azure firewall resource
FW_IP_NAME="azfw-ip" # here enter the name of your public ip resour

PREFIX="wr"

RG="${PREFIX}-rg"  # here enter the resources group name of your AKS cluster

LOC="eastus"   # here enter the datacenter location

NAME="${PREFIX}20190212"  # here enter the name of your kubernetes resource

ACR_NAME="${NAME}acr"   # here enter the name of your Azure Container Registrar

VNET_NAME="${PREFIX}vnet"  # here enter the name of your vnet

AKSSUBNET_NAME="${PREFIX}akssubnet"   # here enter the name of your AKS subnet

SVCSUBNET_NAME="${PREFIX}svcsubnet"   # here enter the name of your service subnet

### DO NOT CHANGE FWSUBNET_NAME - This is currently a requirement for Azure Firewall.

FWSUBNET_NAME="AzureFirewallSubnet"

APPGWSUBNET_NAME="${PREFIX}appgwsubnet"

WORKSPACENAME="${PREFIX}k8slogs"

IDENTITY_NAME="${PREFIX}identity"

FWNAME="${PREFIX}fw"

FWPUBLICIP_NAME="${PREFIX}fwpublicip"

FWIPCONFIG_NAME="${PREFIX}fwconfig"

FWROUTE_TABLE_NAME="${PREFIX}fwrt"

FWROUTE_NAME="${PREFIX}fwrn"
AGNAME="${PREFIX}ag"

AGPUBLICIP_NAME="${PREFIX}agpublicip"

STORAGE="${PREFIX}blob"

# Get ARM Access Token and Subscription ID - This will be used for AuthN later.

ACCESS_TOKEN=$(az account get-access-token -o tsv --query 'accessToken')

# NOTE: Update Subscription Name

SUBID=$(az account show -s '<SUBSCRIPTION_NAME_GOES_HERE>' -o tsv --query 'id') 

# Create Resource Group

az group create --name $RG --location $LOC





# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

# Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.
