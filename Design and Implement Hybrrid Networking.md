## Why Use Hybrid neyworking ?
> You are migrating to cloud. This network would be used to connect their growing number of distributed offices. It would also address the work from home initiatives so that  maximise your existing on-premises investments by relying on an effective hybrid and multicloud approach

Make Azure an extension of your existing network, connecting distributed workloads and locations at a global scale.

- Azure VPN Gateway
- Azure ExpressRoute
- Azure Virtual WAN

## VPN
(Virtual Private network) -- Get Private Encrypeted connectivity 

[MS LEARN](https://docs.microsoft.com/en-us/learn/modules/design-implement-hybrid-networking/2-design-implement-vpn-gateway)

## Choose Generation and SKU of VPN
Setting up a virtual network is free of charge. However, we do charge for the VPN gateway that connects to on-premises and other virtual networks in Azure. This charge is based on the amount of time that gateway is provisioned and available.
[VPN PRICING](https://azure.microsoft.com/en-in/pricing/details/vpn-gateway/)

## S2S VPN 

![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-hybrid-networking/media/site-site-vpn-architecture.png)

- For example, a P2S connection requires a RouteBased VPN type. A VPN type can also depend on the hardware that you are using. S2S configurations require a VPN device. Some VPN devices only support a certain VPN type.
- Once a virtual network gateway has been created, you can't change the VPN type. You must delete the virtual network gateway and create a new one.

-  **Policy Based** - PolicyBased VPNs can only be used on the Basic gateway SKU. This VPN type is not compatible with other gateway SKUs.

You can have only 1 tunnel when using a PolicyBased VPN.

You can only use PolicyBased VPNs for S2S connections, and only for certain configurations. Most VPN Gateway configurations require a RouteBased VPN.

**route based** -
Typical route-based gateway scenarios include point-to-site, inter-virtual network, or multiple site-to-site connections. Route-based is also selected when you coexist with an ExpressRoute gateway or if you need to use IKEv2. Policy-based gateways support only IKEv1.

### Create a VPN GATEWAY
![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-hybrid-networking/media/vpn-gateway-config.png)

SKU -- AS PER THE NO. OF CONNECTIONS YOU NEED 

## gateway
- the gateway subnet contains the IP addresses that the virtual network gateway VMs and services use. 
- Never deploy anything else (for example, additional VMs) to the gateway subnet. The gateway subnet must be named GatewaySubnet to work properly. Naming the gateway subnet GatewaySubnet tells Azure know that this is the subnet to deploy the virtual network gateway VMs and services to.
- planning your gateway subnet size, refer to the documentation for the configuration that you are planning to create. For example, the ExpressRoute/VPN Gateway coexist configuration requires a larger gateway subnet than most other configurations. Additionally, you may want to make sure your gateway subnet contains enough IP addresses to accommodate possible future additional configurations. While you can create a gateway subnet as small as /29, we recommend that you create a gateway subnet of /27 or larger (/27, /26 etc.) if you have the available address space to do so. This will accommodate most configurations.
- The local network gateway typically refers to the on-premises location. use FQDN 

## Trouble shoot isues
GatewayDiagnosticLog - Contains diagnostic logs for gateway configuration events, primary changes, and maintenance events.

TunnelDiagnosticLog - Contains tunnel state change events. Tunnel connect/disconnect events have a summarized reason for the state change if applicable.

RouteDiagnosticLog - Logs changes to static routes and BGP events that occur on the gateway.

IKEDiagnosticLog - Logs IKE control messages and events on the gateway.

P2SDiagnosticLog - Logs point-to-site control messages and events on the gateway.

## P2S VPN CONNECTION

![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-hybrid-networking/media/point-site-diagram.png)

VARIOUS AUTHENTICATION METHODS ALSO AVAILABLE FOR P2S VPN 

![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-hybrid-networking/media/p2s-authenticate-with-ad.png)

[Ms Learn for P2S VPN](https://docs.microsoft.com/en-us/learn/modules/design-implement-hybrid-networking/5-connect-devices-to-networks-point-to-site-vpn-connections)

## Virtual WAN
> organizations to operate across regional and national boundaries, and across time zones.enable their employees, partners, and customers to connect to the resources they need from wherever they are

![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-hybrid-networking/media/azure-wan-regions.png)

- You can use a secured virtual hub to filter traffic between virtual networks (V2V), virtual networks and branch offices (B2V) and traffic to the Internet (B2I/V2I) by using a firewall
- These secured virtual hub provides automated routing. There's no need to configure your own UDRs
- Azure Virtual WAN is a managed service, it creates the appropriate subnets in the virtual hub for the different gateways/services (for example, VPN gateways, ExpressRoute gateways, 

![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-hybrid-networking/media/concepts-association.png)

![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-hybrid-networking/media/concepts-propagation.png)

## NVA

One of the benefits of Azure Virtual WAN is the ability to support reliable connections from many different technologies, whether Microsoft based, such as ExpressRoute or a VPN Gateway, or from a networking partner, such as Barracuda CloudGen WAN, Cisco Cloud OnRamp for Multi-Cloud, and VMware SD-WAN. These types of devices are known as network virtual appliances (NVAs

![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-hybrid-networking/media/nva-high-level-process.png)

[Create NVA & learn more from MS LEARN](https://docs.microsoft.com/en-us/learn/modules/design-implement-hybrid-networking/8-create-network-virtual-appliance-virtual-hub)
