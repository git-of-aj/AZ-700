Many PaaS Resouces have public IP address. So, even though both your virtual network and the Azure SQL database are located within the Azure cloud, the connection between them takes place over the internet.
> So company want Azure Virtual Networks (VNets) and Azure PaaS workloads over the Microsoft backbone network

**map the private link service to a private endpoint**
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

## DNS with Private link

[DNS FOR PRIVATE ENDPOINT](https://docs.microsoft.com/en-us/azure/private-link/private-endpoint-dns)
. A DNS forwarder is a Virtual Machine running on the Virtual Network linked to the Private DNS Zone that can proxy DNS queries coming from other Virtual Networks or from on-premises

Normally Developers do not have permission to edit private DNS records so

This access limitation means they do not have the possibility to create the DNS records required when deploying Azure PaaS services with Private Endpoints.
![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-private-access-to-azure-services/media/private-link-example-central-dns-73e26cad.png)

In this diagram :

✓ On-premises DNS servers have conditional forwarders configured for each Private Endpoint public DNS zone forwarder pointing to the DNS forwarders (10.100.2.4 and 10.100.2.5) hosted in the hub VNet.
✓ The DNS servers 10.100.2.4 and 10.100.2.5 hosted in the hub VNet use the Azure-provided DNS resolver (168.63.129.16) as a forwarder.
✓ All Azure VNets have the DNS forwarders (10.100.2.4 and 10.100.2.5) configured as the primary and secondary DNS servers.

- Private Endpoint IP address to the fully qualified domain name (FQDN) of the connection string.

✓ How to configure your DNS settings for Private Endpoints

1. OS Host file --  like /etc/hosts in linux `really bad idea`

2. Private Zone DNS Records

## Significance of `168.63.129.16`

without any custom DNS settings the client queries for the private endpoint IP address to the Azure-provided DNS service 168.63.129.16. Azure DNS will be responsible for DNS resolution of the private DNS zones


## A K S NETWORKING



- Calico network policy is a namespaced resource that applies to pods/containers/VMs in that namespace
