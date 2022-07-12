# Terraform-with-Azure

https://www.youtube.com/watch?v=V53AHWun17s

https://raw.githubusercontent.com/RodrigoMvs123/Terraform-with-Azure/main/README.md

https://github.com/RodrigoMvs123/Terraform-with-Azure/blame/main/README.md

Terraform with Azure


Learn Terraform with Azure by Building a Dev Environment – Full Course for Beginners

Install Azure CLI 
Visual Studio Code 
Install the Azure CLI for Windows | Microsoft Docs

az login 
n
az login - - use-device-code 
https://microsoft.com/devicelogin 
ERTP7DNDC
clear 

az account show
clear 

Visual Studio Code Terraform Extension 

Terraform with Azure Folder 
az account show
create file 
main.tf
https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs
Azure Provider: Authenticating via the Azure CLI | Guides | hashicorp/azurerm | Terraform Registry


terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

provider "azurerm" {
  features {}



terraform fmt 
clear 
terraform init 

terraform> 
terraform-provider-azurem…
terraform.lock.hd

azurerm_resource_group | Resources | hashicorp/azurerm | Terraform Registry

terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

provider "azurerm" {
  features {}

resource "azurerm_resource_group" "atc-rg" {
 name = "atc-resources" 
location = "East US" }
tags = {
environment - “dev” 
}

terraform fmt 
clear
terraform plan 
clear

terraform apply
yes

Introdução ao Azure Quickstart Center - Azure portal | Microsoft Docs
resource groups 

Azure-virtual-network 
https://azure.microsoft.com/pt-pt/services/virtual-network/?&ef_id=Cj0KCQjw5ZSWBhCVARIsALERCvzEAbHZPf3pB6BzwgffrU3AM42vHdqBCeboVUQQknHsCRKVsgMgB58aAobUEALw_wcB:G:s&OCID=AIDcmmj8drqamm_SEM_Cj0KCQjw5ZSWBhCVARIsALERCvzEAbHZPf3pB6BzwgffrU3AM42vHdqBCeboVUQQknHsCRKVsgMgB58aAobUEALw_wcB:G:s&gclid=Cj0KCQjw5ZSWBhCVARIsALERCvzEAbHZPf3pB6BzwgffrU3AM42vHdqBCeboVUQQknHsCRKVsgMgB58aAobUEALw_wcB#overview

terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

provider "azurerm" {
  features {}

resource "azurerm_resource_group" "atc-rg" {
 name = "atc-resources" 
location = "East US" }
tags = {
environment - “dev” 
}

resource “azurem_virtual_network” “atc-vm” {
name = “atc-network”
resource_group_name = azurem_resource_group.ntc-rg.name
location = azurem_resource_group.ntc-rg.location 
address_space = [‘10.123.0.0/16’]
tags = {
environment = “dev” 
}
}

terraform fmt 
clear 
terraform plan 
clear 

terraform apply -auto-approve 


Introdução ao Azure Quickstart Center - Azure portal | Microsoft Docs
resource groups 
virtual networks 

terraform.Ifstate
terraform.Ifstate.backup

terraform state list 
terraform state show azurem_resource_group.ntc-rg 
terraform show
clear 

terraform state list 
clear

terraform plan -destroy 
terraform apply -destroy
yes 
terraform.Ifstate ( Destroy ) 
terraform.Ifstate.backup
terraform apply -auto-approve 


azurerm_subnet | Resources | hashicorp/azurerm | Terraform Registry

terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

provider "azurerm" {
  features {}

resource "azurerm_resource_group" "atc-rg" {
 name = "atc-resources" 
location = "East US" }
tags = {
environment - “dev” 
}

resource “azurerm_virtual_network” “atc-vm” {
name = “atc-network”
resource_group_name = azurerm_resource_group.mtc-rg.name
location = azurerm_resource_group.mtc-rg.location 
address_space = [‘10.123.0.0/16’]
tags = {
environment = “dev” 
}
}

resource “azurerm_subnet” “mtc-subnet” {
name = “ntc-subnet”
resource-group-name = azurerm_resource_group.mtc.rg.name
virtual_network_name = azurerm_virtual_network.mtc-vm.name
address_prefixes = [10.123.1.0/24]

}

terraform fmt 
clear
terraform plan 
terraform apply -auto-approve
clear
terraform state list 
clear

azure // home > ( mtc-resources ) > network > subnet mtc-subnet 

azurerm_network_security_group | Resources | hashicorp/azurerm | Terraform Registry



terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

provider "azurerm" {
  features {}

resource "azurerm_resource_group" "atc-rg" {
 name = "atc-resources" 
location = "East US" }
tags = {
environment - “dev” 
}

resource “azurerm_virtual_network” “atc-vm” {
name = “atc-network”
resource_group_name = azurerm_resource_group.mtc-rg.name
location = azurerm_resource_group.mtc-rg.location 
address_space = [‘10.123.0.0/16’]
tags = {
environment = “dev” 
}
}

resource “azurerm_subnet” “mtc-subnet” {
name = “ntc-subnet”
resource-group-name = azurerm_resource_group.mtc.rg.name
virtual_network_name = azurerm_virtual_network.mtc-vm.name
address_prefixes = [10.123.1.0/24]

}

resource = “azurerm_network_security_group” “mtc-sg” {
name = “mtc-sg” 
location = azurerm_resource_group.mtc.rg.location
resource_group_name = azurerm_resource_group.mtc-rg.name
tags = {
environment = “dev”
}
azurerm_network_security_rule | Resources | hashicorp/azurerm | Terraform Registry
resource "azurerm_network_security_rule" "mtc-dev-rule" 
{ name = "mtc-dev-rule" 
priority = 100 
direction = "Intbound" 
access = "Allow"
 protocol = "*" 
source_port_range = "*" 
destination_port_range = "*" 
source_address_prefix = " 2804:293c:20d:9600:64d7:43c0:2805:971e" 
destination_address_prefix = "*"
resource_group_name = azurerm_resource_group.mtc-rg.name network_security_group_name = azurerm_network_security_group.mtc-sg.name

azurerm_subnet_network_securi…
resource "azurerm_subnet_network_security_group_association" "example" { subnet_id = azurerm_subnet.example.id network_security_group_id = azurerm_network_security_group.example.id }


}

terraform fmt 
terraform plan 
terraform apply -auto-approve 
clear 
terraform state list 
clear




terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

provider "azurerm" {
  features {}

resource "azurerm_resource_group" "atc-rg" {
 name = "atc-resources" 
location = "East US" }
tags = {
environment - “dev” 
}

resource “azurerm_virtual_network” “atc-vm” {
name = “atc-network”
resource_group_name = azurerm_resource_group.mtc-rg.name
location = azurerm_resource_group.mtc-rg.location 
address_space = [‘10.123.0.0/16’]
tags = {
environment = “dev” 
}
}

resource “azurerm_subnet” “mtc-subnet” {
name = “ntc-subnet”
resource-group-name = azurerm_resource_group.mtc.rg.name
virtual_network_name = azurerm_virtual_network.mtc-vm.name
address_prefixes = [10.123.1.0/24]

}

resource = “azurerm_network_security_group” “mtc-sg” {
name = “mtc-sg” 
location = azurerm_resource_group.mtc.rg.location
resource_group_name = azurerm_resource_group.mtc-rg.name
tags = {
environment = “dev”
}
azurerm_network_security_rule | Resources | hashicorp/azurerm | Terraform Registry
resource "azurerm_network_security_rule" "mtc-dev-rule" 
{ name = "mtc-dev-rule" 
priority = 100 
direction = "Intbound" 
access = "Allow"
 protocol = "*" 
source_port_range = "*" 
destination_port_range = "*" 
source_address_prefix = " 2804:293c:20d:9600:64d7:43c0:2805:971e" 
destination_address_prefix = "*"
resource_group_name = azurerm_resource_group.mtc-rg.name network_security_group_name = azurerm_network_security_group.mtc-sg.name

azurerm_subnet_network_securi…
resource "azurerm_subnet_network_security_group_association" "mtc-sga" { 
subnet_id = azurerm_subnet.mtc-subnet.id 
network_security_group_id = azurerm_network_security_group.mtc-sg.id }

    resource "azurerm_public_ip" "example" 
{ name = "acceptanceTestPublicIp1" 
resource_group_name = azurerm_resource_group.example.name 
location = azurerm_resource_group.example.location 
allocation_method = "Static" 
tags = {
 environment = "Production" }

 }


}

terraform fmt 
clear
terraform plan
clear

terraform apply -auto-approve 
clear

Virtual Machine // By creating a public Ip
azurerm_public_ip | Resources | hashicorp/azurerm | Terraform Registry


terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

provider "azurerm" {
  features {}

resource "azurerm_resource_group" "atc-rg" {
 name = "atc-resources" 
location = "East US" }
tags = {
environment - “dev” 
}

resource “azurerm_virtual_network” “atc-vm” {
name = “atc-network”
resource_group_name = azurerm_resource_group.mtc-rg.name
location = azurerm_resource_group.mtc-rg.location 
address_space = [‘10.123.0.0/16’]
tags = {
environment = “dev” 
}
}

resource “azurerm_subnet” “mtc-subnet” {
name = “ntc-subnet”
resource-group-name = azurerm_resource_group.mtc.rg.name
virtual_network_name = azurerm_virtual_network.mtc-vm.name
address_prefixes = [10.123.1.0/24]

}

resource = “azurerm_network_security_group” “mtc-sg” {
name = “mtc-sg” 
location = azurerm_resource_group.mtc.rg.location
resource_group_name = azurerm_resource_group.mtc-rg.name
tags = {
environment = “dev”
}
azurerm_network_security_rule | Resources | hashicorp/azurerm | Terraform Registry
resource "azurerm_network_security_rule" "mtc-dev-rule" 
{ name = "mtc-dev-rule" 
priority = 100 
direction = "Intbound" 
access = "Allow"
 protocol = "*" 
source_port_range = "*" 
destination_port_range = "*" 
source_address_prefix = " 2804:293c:20d:9600:64d7:43c0:2805:971e" 
destination_address_prefix = "*"
resource_group_name = azurerm_resource_group.mtc-rg.name network_security_group_name = azurerm_network_security_group.mtc-sg.name

azurerm_subnet_network_securi…
resource "azurerm_subnet_network_security_group_association" "mtc-sga" { 
subnet_id = azurerm_subnet.mtc-subnet.id 
network_security_group_id = azurerm_network_security_group.mtc-sg.id }

    resource "azurerm_public_ip" "mtc-ip" 
{ name = "mtc-ip" 
resource_group_name = azurerm_resource_groupmtc.rg.name 
location = azurerm_resource_group.mtc.rg.location 
allocation_method = "dynamic" 
tags = {

 environment = "dev" }
 }
}




terraform fmt 
terraform plan 
terraform apply -auto-approve
terraform state list 
terraform state show azurerm_public_ip.mtc-ip
clear


terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

provider "azurerm" {
  features {}

resource "azurerm_resource_group" "atc-rg" {
 name = "atc-resources" 
location = "East US" }
tags = {
environment - “dev” 
}

resource “azurerm_virtual_network” “atc-vm” {
name = “atc-network”
resource_group_name = azurerm_resource_group.mtc-rg.name
location = azurerm_resource_group.mtc-rg.location 
address_space = [‘10.123.0.0/16’]
tags = {
environment = “dev” 
}
}

resource “azurerm_subnet” “mtc-subnet” {
name = “ntc-subnet”
resource-group-name = azurerm_resource_group.mtc.rg.name
virtual_network_name = azurerm_virtual_network.mtc-vm.name
address_prefixes = [10.123.1.0/24]

}

resource = “azurerm_network_security_group” “mtc-sg” {
name = “mtc-sg” 
location = azurerm_resource_group.mtc.rg.location
resource_group_name = azurerm_resource_group.mtc-rg.name
tags = {
environment = “dev”
}
azurerm_network_security_rule | Resources | hashicorp/azurerm | Terraform Registry
resource "azurerm_network_security_rule" "mtc-dev-rule" 
{ name = "mtc-dev-rule" 
priority = 100 
direction = "Intbound" 
access = "Allow"
 protocol = "*" 
source_port_range = "*" 
destination_port_range = "*" 
source_address_prefix = " 2804:293c:20d:9600:64d7:43c0:2805:971e" 
destination_address_prefix = "*"
resource_group_name = azurerm_resource_group.mtc-rg.name network_security_group_name = azurerm_network_security_group.mtc-sg.name

azurerm_subnet_network_securi…
resource "azurerm_subnet_network_security_group_association" "mtc-sga" { 
subnet_id = azurerm_subnet.mtc-subnet.id 
network_security_group_id = azurerm_network_security_group.mtc-sg.id }

    resource "azurerm_public_ip" "mtc-ip" 
{ name = "mtc-ip" 
resource_group_name = azurerm_resource_groupmtc.rg.name 
location = azurerm_resource_group.mtc.rg.location 
allocation_method = "dynamic" 
tags = {

 environment = "dev" }
 }
}

resource “azurerm_network_interface” “mtc-nic” {
name = “mtc-nic”
location = azurerm_resource_group.mtc-rg.location 
resource_group_name = azurerm_resource_group.mtc-rgname

ip_configuration {
name = “internal”
subnet_id = azurerm_subnet.mtc-subnet.id
private_ip_address_allocation = “Dynamic”
public_ip_address_id = azurerm_public_ip.mtc-ip.id

}

tags = {
environment = ‘dev“
}
}

terraform fmt 
terraform plan 
terraform plan 
clear
terraform apply -auto-approve
clear
terraform state list 
clear
terraform state show azurerm_network_interface.mtc-nic
clear
terraform state list 
terraform state show azurerm_public_ip.mtc-ip

ssh-keygen -t rsa
C:\user\derek/.ssh mtcazurekey
password

ls ~/.ssh
clear

main.tf
admin_ssh_key {
username = “adminuser”
public_key = file (“~/.ssh/mtcazurekey.pub”)
}

terraform fmt
clear
terraform plan 
terraform apply -auto-approve 

clear
terraform state list 
clear
terrafor state show azurerm_linux_virtual_machine.mtc-vm
clear
ssh -i ~/.shh/mtcazurekey adminuser@52.170.30.9
yes
clear

lsb_release -a 
clear 
exit 
clear
// linux vm instance deployed with docker 

new file ( custumdata.tpl ) // tpl is a extension for template files for eventually add some variables 




main.tf

custom_data = filebase64 (“customdata.tpl”)
filebase64 - Functions - Configuration Language | Terraform by HashiCorp
admin_ssh_key { //…

terraform fmt 
terraform plan 
clear

terraform apply -auto-approve 
clear

terraform state list 
clear
terrafor state show azurerm_linux_virtual_machine.mtc-vm

clear
ssh -i ~/.shh/mtcazurekey adminuser@40.117.150.153
yes

clear 
docker - - version 
extension // remote ssh 

new file ( windows-ssh-script.tpl ) 
Host admin.com
  HostName admin.com
  User admin

identifyfile $ (identifyfile) 


new file ( linux-ssh-script.tpl ) 

Host admin.com
  HostName admin.com
  User admin

identifyfile $ (identifyfile)
EOF

Provisioners | Terraform by HashiCorp


main.tf
admin_ssh_key {

provisioner “local-exec” {
command - templatefile(“windows-ssh-script.tpl” , {
hostname = self.public_ip_address
user = “adminuser”,
identifyfile = “~/.ssh/mtcazurekey”
)}
templatefile - Functions - Configuration Language | Terraform by HashiCorp
interpretador = [“Powershell”, “-Command”] // [“bash”,”-c” ]

}

terraform plan 
clear
terraform state list 
clear
terraform apply replace azurerm_linux_virtual_machine.mtc-vm
yes
clear

view > command palette > remote-shh > connect to a host > 20.121.205.65 > Linux > Continue 
adminuser@mtc-vm:~$ docker - version
clear 

Data Sources - 0.11 Configuration Language | Terraform by HashiCorp
azurerm_public_ip | Data Sources | hashicorp/azurerm | Terraform Registry

main.tf
admin_ssh_key {

provisioner “local-exec” {
command - templatefile(“windows-ssh-script.tpl” , {
hostname = self.public_ip_address
user = “adminuser”,
identifyfile = “~/.ssh/mtcazurekey”
)}
templatefile - Functions - Configuration Language | Terraform by HashiCorp
interpretador = [“Powershell”, “-Command”] // [“bash”,”-c” ]

}

data “azure_public_ip” “mtc-ip-data” {
name = azurerm_public_ip .mtc-ip.name 
resource_group_name = azurerm_resouce_group.mtc-rg.name
}

terraform apply -refresh-only 
yes
clear
terraform state list 
clear

Output Values - Configuration Language | Terraform by HashiCorp

main.tf // file 
output “public_ip_address” {
value = “ $(azurerm_linux_virtual_machine.mtc-vm.name):  ${data.azurerm_public_ip.mtc-ip-data.ip_address} “ 
}


terraform state show data.azurerm_public_ip.mtc-ip-data
terraform apply -refresh-only 

yes

clear

terraform output
terraform output public_ip_address
clear

command = templatefile(“ $ (var.host.os).ssh -script-tpl”, { // …

new file 
variables.tf

variable “host_os” {
type = string 
}
 
terraform destroy -auto-approve

windows // var.host.os ( enter a value ) 
clear

terraform plan 
windows // var.host.os ( enter a value )
clear


new file 
variables.tf

variable “host_os” {
type = string 
default = “windows”
}

terraform console 
>var.host_os
“windows”
exit 


new file 
variables.tf

variable “host_os” {
type = string 
}
 
terraform console 
>var.host_os ( know after apply ) 
clear

new file 
terraform.tfvars
host_os = “windows” 
terraform console
>var.host_os
“windows”
exist 
clear

terraform console -var=”host_os=linux”
>var.host_os
“linux”
exist 
clear

new file 
osx.tfvars 
host_os= “osx”
terraform console -var-file=”osx.tfvars”
>var.host_os
“osx”
exit 
clear

main.tf
interpreter = [“Porwershell”, “command”] // [“bash”, “-c”]
Conditional Expressions - Configuration Language | Terraform by HashiCorp

terraform console
>var.host_os == “windows” ? “porwershell” : “bash”
“powershell”
>var.host_os == “windows” ? [“Powershell”, “-command”] : [“bash”, “-c”]
“Powershell”,
“-command”,
>var.host_os != “windows” ? “bash” : “Powershell”
“Powershell”
exist

interpreter = var.host_os == “windows” ? [“Powershell”, “-command”] : [“bash”, “-c”]
exit 
clear

terraform plan 
clear
terraform apply -auto-approve
view 
command palette
remote-ssh // connect to host 
13.90.92.139
linux 
continue 
docker - - version 
open folder
clear
exit 

terraform apply -refresh -only 
yes 

terraform output 
new terminal

clear

terraform destroy -auto-approve



