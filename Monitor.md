## Azure Monitor -- 

- Metrics (numbers)
- logs (text)


## Azure network watcher

Azure Network Watcher provides tools to monitor, diagnose, view metrics, and enable or disable logs for resources in an Azure virtual network. 

✓ only for IaaS services  like Virtual Machines, Virtual Networks, Application Gateways, Load balancers, etc.


🚫 NOT For paas services or web analytics


[Azure Network Watcher](https://docs.microsoft.com/en-us/learn/modules/configure-network-watcher/2-describe-features)

- `Communication Monitor` -- Monitor communication between a virtual machine and an endpoint
Endpoints can be another virtual machine (VM), a fully qualified domain name (FQDN), a uniform resource identifier (URI), or IPv4 address

- Diagnose VM Traffic filter problem -- `IP FLOW VERIFY` --> communication suceeds or fails. If the connection fails, IP flow verify tells you which security rule allowed or denied the communication,
- Diagnose VM Routing Problem -- `NEXT HOP`
- Diagnose VM Communication issues -- The effective security rules for a network interface are a combination of all security rules applied to the network interface, and the subnet the network interface is in
- If the gateway or connection is not available, VPN diagnostics tells you why, so you can resolve the problem. -- `VPN Troubleshoot`
- The NSG flow log capability allows you to log the source and destination IP address, port, protocol, and whether traffic was allowed or denied by an NSG -- `NSG FLOW LOGS`
- 
log VM network traffic -- 
