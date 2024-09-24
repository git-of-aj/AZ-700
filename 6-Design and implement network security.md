## Network Security
> Network security is the process of protecting resources from unauthorized access or attack by applying controls to network traffic, allowing only legitimate traffic/request
Your security requirements might include:

- Authentication and authorization (for your application)
- Intrusion detection and response
- URL filtering
- Application access control
- DDoS protection

## Network Security AZURE Guidance

[Docs link](https://docs.microsoft.com/en-us/security/benchmark/azure/security-controls-v3-network-security)

## Defender for DNS: https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-dns-introduction

✓ Any workload that could incur higher risk for the organization should be in isolated virtual networks :- `use NSG --> NIC / SUBNET` + `ASG --> group VM` 
> An application storing or processing highly sensitive data.
- An external network-facing application accessible by the public or users outside of your organization.
- An application using insecure architecture or containing vulnerabilities that cannot be easily remediated

✓ Private connection, where ever possible : `Use Private link -- 1 to 1` for supported surprise or `Service Endpoint`

✓ Deploy firewall at the edge of enterprise network
`Azure Firewall` ; 
- At a minimum, block known bad IP addresses and high-risk protocols, such as remote management (for example, RDP and SSH) and intranet protocols (for example, SMB and Kerberos).
central management over a large number of enterprise segments or spokes (in a hub/spoke topology

- Use network intrusion detection and intrusion prevention systems (IDS/IPS) to inspect the network and payload traffic to or from your workload. 

- [Implementing Azure Firewall Between Two VNets: Step-by-Step Guide](https://medium.com/@subhampradhan966/implementing-azure-firewall-between-two-vnets-step-by-step-guide-4a3eac2a4ba9)

✓ 
` azure WAF ` : Use web application firewall (WAF) capabilities in Azure Application Gateway, Azure Front Door, and Azure Content Delivery Network (CDN) to protect your applications, services and APIs against application layer attacks at the edge of your network.
OWASP Top 10 vulnerabilities, and tune it to your application

✓ centralised management
use tools to simplify, centralize and enhance the network security management. 

### Azure Security benchmark
[aka.ms/benchmarkdocs](https://docs.microsoft.com/en-us/security/benchmark/azure/)

[MS LEARN](https://docs.microsoft.com/en-us/learn/modules/design-implement-network-security-monitoring/2-secure-your-virtual-networks-azure-portal)

### Azure Firewall
- you can easily configure outbound access.
<br>Like only specific FQDN can be accessed 
[Tutorial](https://docs.microsoft.com/en-us/azure/firewall/tutorial-firewall-deploy-portal)


## AZURE WAF 
> Malicious attacks such as SQL Injection, Cross Site Scripting (XSS), and other OWASP top 10 threats could cause service outage or data loss, and pose a big threat to web application owners. Web Application Firewall (WAF) protects your web applications from common web attacks, keeps your service available and helps you meet compliance requirements.
Open Web Application Security Project,[OWASP](https://owasp.org/www-project-top-ten/)
