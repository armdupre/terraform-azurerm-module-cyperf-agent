# module-cyperf-agent/azurerm

## Description
Terraform module for CyPerf agent deployment on Microsoft Azure

## Deployment
This module creates a single instance having two network interfaces.

## Usage
```tf
module "Agent" {
	source = "git::https://github.com/armdupre/terraform-azurerm-module-cyperf-agent.git"
	AppEth0IpAddress = module.App.Instance.private_ip
	Eth0SubnetId = module.Vnet.PublicSubnet.id
	Eth1SubnetId = module.Vnet.PrivateSubnet.id
	ResourceGroupName = azurerm_resource_group.ResourceGroup.name
	SshKeyName = azurerm_ssh_public_key.SshKey.name
}
```