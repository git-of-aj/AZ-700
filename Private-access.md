Many PaaS Resouces have public IP address. So, even though both your virtual network and the Azure SQL database are located within the Azure cloud, the connection between them takes place over the internet.

- Private Link is designed to eliminate these security risks by removing the public part of the connection.
- Pvt link can be used with other peered vnet and on prem (connected via ExpressRoute or VPN)
- Private Link resource can be deployed in a different region than the virtual network and Private Endpoint.
