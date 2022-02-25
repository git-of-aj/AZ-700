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

- Diagnose VM Traffic filter problem -- IP FLOW VERIFY --> communication suceeds or fails. If the connection fails, IP flow verify tells you which security rule allowed or denied the communication,
- Diagnose VM Routing Problem -- NEXT HOP
- Diagnose VM Communication issues -- 
- log VM network traffic -- 
