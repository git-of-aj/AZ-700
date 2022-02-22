# image gallery

## 1 
![](https://miro.medium.com/max/1400/1*T3KG2TELCVgX33wOZVUpoQ.png)

## 2
![](https://miro.medium.com/max/1400/1*2PTYVbUI5Rgs4gRdg-6A3A.png)

## 3 
![](https://docs.microsoft.com/en-us/azure/security/fundamentals/media/infrastructure-network/network-arch.png)

VPN
To support VPN authentication on-premise, use a RADIUS server.
Site-to-site VPNs require a local network gateway and a virtual network gateway in Azure.
To troubleshoot VPN tunnels check the IKEDiagnosticLog.
When using Point-to-site (P2S) VPN The VPN client must be downloaded again if any changes are made to VNet peering or the network topology.
Cross-region VNET integration requires a VPN gateway and a point to site VPN connection
Basic SKU virtual WAN supports Site-to-site VPN only



VNETs / VNET Peering
AllowGatewayTransit — If you have a virtual network gateway attached to this virtual network and want to allow traffic from the peered virtual network to flow through the gateway.
UseremoteGateways — If you want to allow traffic from this virtual network to flow through a virtual network gateway attached to the virtual network you’re peering with.
VMS in the same VNET but different subnets can communicate natively.
Traffic analytics requires a log analytics workspace and a storage account.
NAT
On a subnet with a NAT gateway, all outbound to Internet scenarios are superseded by the NAT gateway.
Only static IPv4 addresses in the Standard SKU are supported for VNET NAT.
NAT scales to support dynamic workloads. By using port network address translation (PNAT or PAT), NAT provides up to 64,000 concurrent flows.
NAT is compatible with standard SKU public IP, public IP prefix, and load balancer resources. Basic resources (for example basic load balancer) and any products derived from them aren’t compatible with NAT. Basic resources must be placed on a subnet not configured with NAT.
Application Gateway
AppGW requires a dedicated subnet.
Application Gateway allows you to add, remove, or update HTTP request and response headers while the request and response packets move between the client and backend pools.
Azure Bastion
Azure Bastion requires a dedicated subnet.
Firewall
Forced tunneling can only be enabled during the creation of the firewall
ExpressRoute
Types of SKU for ExpressRoute circuits — Local, Premium, Standard.
ExpressRoute gateways for VWAN are provisioned in units of 2 Gbps. 1 scale unit = 2 Gbps
ExpressRoute is not encrypted by default. Options is MACsec for point-to-point encryption or IPSec for end-to-end encryption.
Premium allows global connectivity for services, increased route limits from 4000 to 10000, increased VNET links from 10 depending on the size of the circuit.
You can configure a Site-to-Site VPN connection as a backup for ExpressRoute. This connection applies only to virtual networks linked to the Azure  in app
Get started
FAUN Publication




You have 2 free member-only stories left this month. Sign up for Medium and get an extra one

Azure Networking AZ-700 Exam Tips
Designing and Implementing Microsoft Azure Networking Solutions Exam Guide
Jack Roper
Jack Roper
Follow

Dec 17, 2021 · 5 min read






I recently passed the AZ-700 exam with 850 points, overall it’s a fairly tricky exam, anyone with a foundation in Infrastructure and Networking will have a good chance with a bit of revision once you know the gotchas! Time is pretty tight on this one, so you’ll need to keep an eye on the clock. I had 2 case studies, the rest were multiple-choice questions.
The content of this exam was updated on November 23, 2021, check out the latest outline here:
Exam AZ-700: Designing and Implementing Microsoft Azure Networking Solutions - Learn
Languages: English, Japanese, Chinese (Simplified), Korean, German, French, Spanish, Portuguese (Brazil), Arabic (Saudi…
docs.microsoft.com

Microsoft Learn as ever has some great resources:
AZ-700 Designing and Implementing Microsoft Azure Networking Solutions - Learn
Learn how to design and implement a secure network infrastructure in Azure and how to establish hybrid connectivity…
docs.microsoft.com

AZ-700 Exam Tips…
VPN
To support VPN authentication on-premise, use a RADIUS server.
Site-to-site VPNs require a local network gateway and a virtual network gateway in Azure.
To troubleshoot VPN tunnels check the IKEDiagnosticLog.
When using Point-to-site (P2S) VPN The VPN client must be downloaded again if any changes are made to VNet peering or the network topology.
Cross-region VNET integration requires a VPN gateway and a point to site VPN connection
Basic SKU virtual WAN supports Site-to-site VPN only

VNETs / VNET Peering
AllowGatewayTransit — If you have a virtual network gateway attached to this virtual network and want to allow traffic from the peered virtual network to flow through the gateway.
UseremoteGateways — If you want to allow traffic from this virtual network to flow through a virtual network gateway attached to the virtual network you’re peering with.
VMS in the same VNET but different subnets can communicate natively.
Traffic analytics requires a log analytics workspace and a storage account.
NAT
On a subnet with a NAT gateway, all outbound to Internet scenarios are superseded by the NAT gateway.
Only static IPv4 addresses in the Standard SKU are supported for VNET NAT.
NAT scales to support dynamic workloads. By using port network address translation (PNAT or PAT), NAT provides up to 64,000 concurrent flows.
NAT is compatible with standard SKU public IP, public IP prefix, and load balancer resources. Basic resources (for example basic load balancer) and any products derived from them aren’t compatible with NAT. Basic resources must be placed on a subnet not configured with NAT.
Application Gateway
AppGW requires a dedicated subnet.
Application Gateway allows you to add, remove, or update HTTP request and response headers while the request and response packets move between the client and backend pools.
Azure Bastion
Azure Bastion requires a dedicated subnet.
Firewall
Forced tunneling can only be enabled during the creation of the firewall
ExpressRoute
Types of SKU for ExpressRoute circuits — Local, Premium, Standard.
ExpressRoute gateways for VWAN are provisioned in units of 2 Gbps. 1 scale unit = 2 Gbps
ExpressRoute is not encrypted by default. Options is MACsec for point-to-point encryption or IPSec for end-to-end encryption.
Premium allows global connectivity for services, increased route limits from 4000 to 10000, increased VNET links from 10 depending on the size of the circuit.
You can configure a Site-to-Site VPN connection as a backup for ExpressRoute. This connection applies only to virtual networks linked to the Azure private peering path.
ExpressRoute Global Reach is designed to complement your service provider’s WAN implementation and connect your branch offices across the world.
FastPath sends network traffic directly to virtual machines in the virtual network, bypassing the gateway.


DNS
Manual DNS entries override automatically registered entries.
Only auto-registered DNS records are deleted when a VM is deleted.
IPv6
Subnets for IPv6 must be exactly /64 in size
IPv6 doesn’t support NAT.
Service Endpoints / Private Link
Service endpoint is for regional or same region virtual network integration.
Service Endpoints enable private IP addresses in the VNet to reach the endpoint of an Azure service without needing a public IP address on the VNet.
Load Balancer
To assign a public IP to a load balancer, two conditions need to be matched, SKU and location
