Many PaaS Resouces have public IP address. So, even though both your virtual network and the Azure SQL database are located within the Azure cloud, the connection between them takes place over the internet.

- Private Link is designed to eliminate these security risks by removing the public part of the connection.
- Pvt link can be used with other peered vnet and on prem (connected via ExpressRoute or VPN)
- Private Link resource can be deployed in a different region than the virtual network and Private Endpoint.

## service endpoint
> As the network engineer, you're planning to move sensitive engineering diagram files into Azure Storage. The files must only be accessible from computers inside the corporate network.

- implement a virtual network Service Endpoint for a service, such as Azure Storage or Azure SQL Database, Azure adds a route to a virtual network subnet for the service. The address prefixes in the route are the same address prefixes, or CIDR ranges, as those of the corresponding service tag.
