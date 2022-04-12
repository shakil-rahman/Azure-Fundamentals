# General Security and Network Security Features
## Contents Page

## Security Threats on Azure
### Azure Security Center
- Azure Security Center is a monitoring service that provides visibility of your security posture across all of your services, both on Azure and on-prem
- Security Posture: refers to cybersecurity policies and controls, as well as how well you can predict, prevent, and respond to security threats
- Azure Security Center can:
  - Monitor security settings across on-premises and cloud workloads
  - Automatically apply required security settings to new resources as they come online
  - Provide security recommendations based on your current configurations, resources, and networks
  - Continuously monitor your resources and perform automatic security assessments to identify potential vulnerabilities
  - Use machine learning to detect and block malware from being installed on your VMs and other resources
  - Use adaptive application controls to define rules that list allowed applications that can run
  - Detect and analyze potential inbound attacks and investigate threats and any post-breach activity that might have occurred
  - Provide just-in-time access control for network ports (only allow traffic at the time you need it)

![Security Center](img/Security-Center.png)
- Secure Score: a measurement of an organization's security posture
- Secure score is based on security controls, or groups of related security recommendations
- Following the secure score recommendations can help protect your organization from threats
- Secure score helps you:
  - Report on the current state of your organization's security posture
  - Improve your security posture by providing discoverability, visibility, guidance, and control
  - Compare with benchmarks and establish key performance indicators (KPIs)
### Azure Sentinel
- Azure Sentinel is Microsoft's cloud-based SIEM system. It uses intelligent security analytics and threat analysis
- Security Information and Event Management (SIEM): aggregates security data from many different sources
- Azure Sentinel enables you to:
  - Collect data across all users, devices, applications, and infrastructure, both on-premises and from multiple clouds
  - Detect previously undetected threats and minimize false positives by using Microsoft's analytics and threat intelligence
  - Investigate threats with AI
  - Respond to incidents rapidly by using built-in orchestration and automation of common tasks
- Connections are handled by built-in connectors or industry-standard log formats and APIs
- Built-in Analytics: use templates designed by Microsoft based on known threats, common attack vectors, and escalation chains for suspicious activity. These templates can be customized and search across the environment for any activity that looks suspicious. Some templates use machine learning behavioral analytics that are based on Microsoft proprietary algorithms
- Custom Analytics: rules that you create to search for specific criteria within your environment. You can preview the number of results that the query would generate (based on past log events) and set a schedule for the query to run. You can also set an alert threshold
### Azure Key Vault
- Azure Key Vault is a centralized cloud service for storing an application's secrets in a single, central location
- It provides secure access to sensitive information by providing access control and logging capabilities
- Azure Key Vault can help you:
  - Manage Secrets: used to securely store and control access to tokens, passwords, certificates, API keys, and other secrets
  - Manage Encryption Keys: used as a key management solution. Key Vault makes it easier to create and control the encryption keys that are used to encrypt your data
  - Manage SSL/TLS Certificates: enables you to provision, manage, and deploy your public and private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for your Azure resources and your internal resources
  - Store Secrets Backed by Hardware Security Modules (HSMs): these secrets and keys can be protected either by software or by FIPS 140-2 Level 2 validated HSMs
- The benefits of using Key Vault include:
  - Centralize application secrets enabling you to control their distribution, and reduces the chances that secrets are accidentally leaked
  - Securely store secrets and keys meaning access to Key Vault requires proper authentication and authorization
  - By using Key Vault, you can monitor and control access to your application secrets
  - Key Vault makes it easier to enroll and renew certificates from public certificate authorities (CAs)
  - Integrate with other Azure services that can then securely reference the secrets stored in Key Vault
### Azure Dedicated Host
- On Azure, virtual machines run on shared hardware that Microsoft manages
- Although the underlying hardware is shared, your VM workloads are isolated from workloads that other Azure customers run
- Azure Dedicated Host provides dedicated physical servers to host your Azure VMs for Windows and Linux
- You're charged per dedicated host, independent of how many VMs you deploy to it