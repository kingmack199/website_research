

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
after another play 

PS C:\coderepo\coavd-1> terraform apply -var-file ./dev-pipeline-variables.tfvars
data.azurerm_key_vault.management-kv: Reading...
data.azurerm_user_assigned_identity.management-managed-id: Reading...
data.azurerm_user_assigned_identity.management-managed-id: Read complete after 1s [id

***********************************************************************************
Plan: 1 to add, 0 to change, 0 to destroy.

Do you want to perform these actions in workspace "development"?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

azurerm_virtual_desktop_workspace_application_group_association.avd-ws-dsktp-assoc["RemoteAssistance"]: Creating...
╷
│ Error: A resource with the ID "/subscriptions/576e7fe3-927a-45a7-ac38-e01a6bd6d7cf/resourceGroups/dev-coavd-rg/providers/Microsoft.DesktopVirtualization/workspaces/dev-coavd-remoteapp-wkspce|/subscriptions/576e7fe3-927a-45a7-ac38-e01a6bd6d7cf/resourceGroups/dev-coavd-rg/providers/Microsoft.DesktopVirtualization/applicationGroups/dev-coavd-RemoteAssistance-ag" already exists - to be managed via Terraform this resource needs to be imported into the State. Please see the resource documentation for "azurerm_virtual_desktop_workspace_application_group_association" for more information.
│
│   with azurerm_virtual_desktop_workspace_application_group_association.avd-ws-dsktp-assoc["RemoteAssistance"],
│   on shared-infrastructure-prtd.tf line 1719, in resource "azurerm_virtual_desktop_workspace_application_group_association" "avd-ws-dsktp-assoc":
│ 1719: resource "azurerm_virtual_desktop_workspace_application_group_association" "avd-ws-dsktp-assoc" {
│
╵

******************************************************************************************************************************

Build and import  for Step 2

Run New this import tot take care of the one left in this example
terraform import -var-file ./dev-pipeline-variables.tfvars azurerm_virtual_desktop_workspace_application_group_association.avd-ws-dsktp-assoc[\`"RemoteAssistance\`"] "/subscriptions/576e7fe3-927a-45a7-ac38-e01a6bd6d7cf/resourceGroups/dev-coavd-rg/providers/Microsoft.DesktopVirtualization/workspaces/dev-coavd-remoteapp-wkspce|/subscriptions/576e7fe3-927a-45a7-ac38-e01a6bd6d7cf/resourceGroups/dev-coavd-rg/providers/Microsoft.DesktopVirtualization/applicationGroups/dev-coavd-RemoteAssistance-ag"

****************************************************************************
Out after import

Import successful!

The resources that were imported are shown above. These resources are now in
your Terraform state and will henceforth be managed by Terraform.
#
******************************************************************************************************************************

Step next I think 3 
run another Apply 

PS C:\coderepo\coavd-1> terraform apply -var-file ./dev-pipeline-variables.tfvars
data.azurerm_key_vault.management-kv: Reading...
data.azurerm_user_assigned_identity.management-managed-id: Reading...
data.azurerm_user_assigned_identity.management-managed-id: Read complete after 1s [id

*************************************************************************
Output of the last apply where you have no changes

No changes. Your infrastructure matches the configuration.

Terraform has compared your real infrastructure against your configuration and found no differences, so no changes are needed.

Apply complete! Resources: 0 added, 0 changed, 0 destroyed.

******************************************************************************************************************************

Done

TEsting 

"-File C:\\Program Files\\AVD\\Scripts\\AVD Shadowing.ps1"
or this one
"-File \"C:\\Program Files\\AVD\\Scripts\\AVD Shadowing.ps1\""







end
