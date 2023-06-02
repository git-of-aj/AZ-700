## 

## Why Azure Expressroute ?
`excellent and cost-effective option for scenarios like periodic data migration, replication for business continuity, disaster recovery and other high-availability strategies.`
one usecase could be run a corporate intranet application in Azure that authenticates your customers with an on-premises Azure Active Directory (Azure AD) service and serves them without routing traffic through the public internet.

**Your data transfer may not take the ideal / fastest path ---> So ExpressRoute helps here**
![](https://raw.githubusercontent.com/Ananyojha/spare-images/main/Screenshot_20211106-125159.png)

## Azure ExpressRoute
> Dedicated private network fiber connections to Azure

- Private connections to Azure
- Increased reliability and speed
- Lower latency
- Supports bandwidth up to 100 Gbps
- Connects directly to your WAN
- Connect your on-premises networks using the Microsoft global network
- Support for IPv6 workloads
- Physical link encryption with MACsec

## architecture 
1. Azure ExpressRoute Circuit: Virtual pipe  => represents the physical connection between your on-premises network and the Azure network
2. ExpressRoute Service Provider: Intermediary b/w MS AND YOU

## types
- Ethernet Connections is like a secret tunnel that connects the two shops underground, and toys travel through it using a special train. Both methods ensure that the toys reach the other shop quickly and securely, but they use different means of transportation
- Azure ExpressRoute is a service provided by Microsoft that helps connect your on-premises network or data center to the Azure cloud. It provides a dedicated and private network connection that offers more reliability, lower latency, and higher security compared to accessing Azure over the public internet.

Now, let's explore some of the ExpressRoute connectivity models in simpler terms:

1. Co-located at a Cloud Exchange: Imagine you have a toy shop, and your friend has a toy shop too. Instead of going to each other's shops, you both decide to set up a small shop in the middle of a big toy market. This small shop is like a Cloud Exchange. With ExpressRoute co-located at a Cloud Exchange, it's like having a special tunnel between your shop and your friend's shop, right in the middle of the toy market. This way, you can easily share toys and do business with each other.

2. Point-to-Point Ethernet Connections: Imagine you have a special telephone at home that connects directly to your friend's telephone in their house. You can use this telephone to talk to your friend whenever you want, without anyone else listening. This connection is like a point-to-point Ethernet connection in ExpressRoute. It's a private and secure line that connects your home directly to your friend's home, allowing you to communicate without any disturbances.

3. Any-to-Any (IPVPN): Now, let's imagine you have a big group of friends, and all of you want to have a secret club where you can share toys and have fun. You build a secret tunnel system connecting each of your homes together, so anyone can visit each other's houses easily. This secret tunnel system is like an Any-to-Any (IPVPN) connection in ExpressRoute. It allows you to connect your network to Azure, and also connect with other Azure customers, creating a private and secure network where you can share resources and communicate.

In summary, ExpressRoute offers different connectivity models to make it easier for you to connect your network to Azure. It's like having special tunnels, shops, or telephone lines that allow you to communicate, share toys, and do business with Azure and other Azure customers securely and efficiently.

## BFD
BFD is a feature that helps monitor the connectivity between your on-premises network and the Azure network.
- allows your on-premises network and the Azure network to continuously send small test messages, like "Are you there?" and receive responses, like "Yes, I'm here!"
- 
> refer to MS Learn to know more 

[MS Learn (covers in detail about ExpressRoute)](https://docs.microsoft.com/en-us/learn/modules/design-implement-azure-expressroute/2-explore)

[ExpressRoute docs](https://docs.microsoft.com/en-us/azure/expressroute/)
