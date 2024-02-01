

Run and Do and aply

Do and import 
terraform import -var-file ./dev-pipeline-variables.tfvars azurerm_virtual_desktop_application_group.avd-ag[\`"Nodejs\`"] "/subscriptions/576e7fe3-927a-45a7-ac38-e01a6bd6d7cf/resourceGroups/dev-coavd-rg/providers/Microsoft.DesktopVirtualization/applicationGroups/dev-coavd-Nodejs-ag"

Step 2

run a plan to see the changes

******************************************************************************************************************************

Plan: 7 to add, 0 to change, 0 to destroy.

Do you want to perform these actions in workspace "development"?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

azurerm_virtual_desktop_application_group.avd-ag["RemoteAssistance"]: Creating...
╷
│ Error: A resource with the ID "/subscriptions/576e7fe3-927a-45a7-ac38-e01a6bd6d7cf/resourceGroups/dev-coavd-rg/providers/Microsoft.DesktopVirtualization/applicationGroups/dev-coavd-RemoteAssistance-ag" already exists - to be managed via Terraform this resource needs to be imported into the State. Please see the resource documentation for "azurerm_virtual_desktop_application_group" for more information.
│
│   with azurerm_virtual_desktop_application_group.avd-ag["RemoteAssistance"],
│   on shared-infrastructure-prtd.tf line 1666, in resource "azurerm_virtual_desktop_application_group" "avd-ag":
│ 1666: resource "azurerm_virtual_desktop_application_group" "avd-ag" {

******************************************************************************************************************************

Build and import  for Step 1

Run this import
terraform import -var-file ./dev-pipeline-variables.tfvars azurerm_virtual_desktop_application_group.avd-ag[\`"RemoteAssistance\`"] "/subscriptions/576e7fe3-927a-45a7-ac38-e01a6bd6d7cf/resourceGroups/dev-coavd-rg/providers/Microsoft.DesktopVirtualization/applicationGroups/dev-coavd-RemoteAssistance-ag"

#
******************************************************************************************************************************
Out put after another play 

PS C:\coderepo\coavd-1> terraform apply -var-file ./dev-pipeline-variables.tfvars
data.azurerm_key_vault.management-kv: Reading...
data.azurerm_user_assigned_identity.management-managed-id: Reading...
data.azurerm_user_assigned_identity.management-managed-id: Read complete after 1s [id

******************************************************************************************************************************

Build and import  for Step 2

Run this import
terraform import -var-file ./dev-pipeline-variables.tfvars azurerm_virtual_desktop_application_group.avd-ag[\`"RemoteAssistance\`"] "/subscriptions/576e7fe3-927a-45a7-ac38-e01a6bd6d7cf/resourceGroups/dev-coavd-rg/providers/Microsoft.DesktopVirtualization/applicationGroups/dev-coavd-RemoteAssistance-ag"

#
******************************************************************************************************************************
Out put after another play 

PS C:\coderepo\coavd-1> terraform apply -var-file ./dev-pipeline-variables.tfvars
data.azurerm_key_vault.management-kv: Reading...
data.azurerm_user_assigned_identity.management-managed-id: Reading...
data.azurerm_user_assigned_identity.management-managed-id: Read complete after 1s [id

******************************************************************************************************************************

TEsting 

"-File C:\\Program Files\\AVD\\Scripts\\AVD Shadowing.ps1"
or this one
"-File \"C:\\Program Files\\AVD\\Scripts\\AVD Shadowing.ps1\""







end
