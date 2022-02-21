Many PaaS Resouces have public IP address. So, even though both your virtual network and the Azure SQL database are located within the Azure cloud, the connection between them takes place over the internet.
> So company want Azure Virtual Networks (VNets) and Azure PaaS workloads over the Microsoft backbone network

- Private Link is designed to eliminate these security risks by removing the public part of the connection.
- Pvt link can be used with other peered vnet and on prem (connected via ExpressRoute or VPN)
- Private Link resource can be deployed in a different region than the virtual network and Private Endpoint.

**Private Endpoint is a Network Interface provided by Azure Private Link within Azure VNet to establish a private and secure connection** and it gets its *IP from CIDR range of your Vnet*

## Private link workflow
Put it behind Azure Standard Load Balancer so that consumers to your service can access it privately from their own VNets. Your customers can create a private endpoint inside their VNet and map it to this service
[Learn more here](https://docs.microsoft.com/en-us/azure/private-link/private-link-service-overview)

**[Tutorial of Private link](https://docs.microsoft.com/en-us/azure/private-link/create-private-endpoint-portal)**

## service endpoint
> As the network engineer, you're planning to move sensitive engineering diagram files into Azure Storage. The files must only be accessible from computers inside the corporate network.

- implement a virtual network Service Endpoint for a service, such as Azure Storage or Azure SQL Database, Azure adds a route to a virtual network subnet for the service. The address prefixes in the route are the same address prefixes, or CIDR ranges, as those of the corresponding service tag.
- Azure Service Endpoint provides devices connected to Azure VNet to access Azure platform services with their Private IP addresses without the need for a Public IP address on the VNet
