# terraform-provisioners

Provisioners can be used to model specific actions on the local machine or on a remote machine in order to prepare servers or other infrastructure objects for service.

The local-exec provisioner invokes a local executable after a resource is created. This invokes a process on the machine running Terraform, not on the resource.

The remote-exec provisioner invokes a script on a remote resource after it is created. This can be used to run a configuration management tool, bootstrap into a cluster, etc. To invoke a local process, see the local-exec provisioner instead. The remote-exec provisioner supports both ssh and winrm type connections.

The file provisioner is used to copy files or directories from the machine executing Terraform to the newly created resource. The file provisioner supports both ssh and winrm type connections.

Most provisioners require access to the remote resource via SSH or WinRM, and expect a nested connection block with details about how to connect. Connection blocks don't take a block label, and can be nested within either a resource or a provisioner.

The self object represents the provisioner's parent resource, and has all of that resource's attributes. For example, use self.public_ip to reference an aws_instance's public_ip attribute.

# Terraform Modules
A module is a container for multiple resources that are used together.

The .tf files in your working directory when you run terraform plan or terraform apply together form the root module. That module may call other modules and connect them together by passing output values from one to input values of another.


# Terraform Import
Terraform is able to import existing infrastructure. This allows you take resources you've created by some other means and bring it under Terraform management.

Bringing existing infrastructure under Terraform's control involves five main steps:

1- Identify the existing infrastructure to be imported.
2- Import infrastructure into your Terraform state.
3- Write Terraform configuration that matches that infrastructure.
4- Review the Terraform plan to ensure the configuration matches the expected state and infrastructure.
5- Apply the configuration to update your Terraform state.