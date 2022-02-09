- For example, a P2S connection requires a RouteBased VPN type. A VPN type can also depend on the hardware that you are using. S2S configurations require a VPN device. Some VPN devices only support a certain VPN type.
- Once a virtual network gateway has been created, you can't change the VPN type. You must delete the virtual network gateway and create a new one.
-
-  **Policy Based** - PolicyBased VPNs can only be used on the Basic gateway SKU. This VPN type is not compatible with other gateway SKUs.

You can have only 1 tunnel when using a PolicyBased VPN.

You can only use PolicyBased VPNs for S2S connections, and only for certain configurations. Most VPN Gateway configurations require a RouteBased VPN.

**route based** -
Typical route-based gateway scenarios include point-to-site, inter-virtual network, or multiple site-to-site connections. Route-based is also selected when you coexist with an ExpressRoute gateway or if you need to use IKEv2. Policy-based gateways support only IKEv1.

### Create a VPN GATEWAY
![](https://docs.microsoft.com/en-us/learn/wwl-azure/design-implement-hybrid-networking/media/vpn-gateway-config.png)

SKU -- AS PER THE NO. OF CONNECTIONS YOU NEED 
