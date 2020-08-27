# # Adapted from https://github.com/Azure/azure-quickstart-templates/tree/master/sqlvm-alwayson-cluster in an attempt to support new Windows Server Images and Sql Server Images
# # Create an Always On Availability Group with SQL Server 2016 replica virtual machines

//TODO later
<!-- [![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fsqlvm-alwayson-cluster%2Fazuredeploy.json)  [![Visualize](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/visualizebutton.svg?sanitize=true)](http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-quickstart-templates%2Fmaster%2Fsqlvm-alwayson-cluster%2Fazuredeploy.json) -->



## Solution overview

This template uses the PowerShell DSC extension to deploy a fully configured Always On Availability Group with SQL Server 2016 replicas.

This template creates the following resources:

+   1 Virtual Network
+   4 Azure storage accounts
    +    1 for domain controller virtual machines
    +    1 for SQL Server virtual machines
    +    1 for Failover Cluster File Share Witness
    +    1 for deployment diagnostics
+   1 internal load balancer
+   1 external load balancer
+   3 virtual machines in a Windows Server Cluster
    +    2 SQL Server 2016 Enterprise edition replicas with an availability group
    +    1 virtual machine is a File Share Witness for the Cluster
+   2 domain controller virtual machines replicas for a new Forest and Domain
+   2 Availability Sets
    +     1 for domain controller virtual machines
    +     1 for SQL Server and Witness virtual machines
+   1 public IP addresses for RDP access

