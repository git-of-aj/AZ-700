## hybrid sceneries
> You are migrating to cloud. This network would be used to connect their growing number of distributed offices. It would also address the work from home initiatives

## VPN
[MS LEARN](https://docs.microsoft.com/en-us/learn/modules/design-implement-hybrid-networking/2-design-implement-vpn-gateway)

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

[Ms Learn](https://docs.microsoft.com/en-us/learn/modules/design-implement-hybrid-networking/5-connect-devices-to-networks-point-to-site-vpn-connections)
