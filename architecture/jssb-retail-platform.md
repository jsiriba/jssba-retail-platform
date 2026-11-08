JSSBA Retail Ltd - Enterprise Platform Architecture
Business Goal
Build an enterprise automation platform capable of provisioning, configuring, deploying, monitoring, and managing infrastructure at scale using modern DevOps practices.

Infrastructure Platform
Cloud Provider:

AWS
Automation Platform:

AWX running on Kubernetes
Source Control:

GitHub
CI/CD:

GitHub Actions
Infrastructure as Code:

Terraform
Configuration Management:

Ansible
Monitoring:

Prometheus
Grafana
Logging:

Loki
Secrets Management:

HashiCorp Vault (Future Phase)
Managed Servers
LNX-WEB-01
Purpose:

Public company website
Operating System:

Ubuntu 24.04
Services:

Nginx
LNX-RPT-01
Purpose:

Reporting and batch processing
Operating System:

Ubuntu 24.04
Services:

Reporting jobs
Scheduled tasks
WIN-IIS-01
Purpose:

HR and Payroll Portal
Operating System:

Windows Server 2022
Services:

IIS
WIN-TOMCAT-01
Purpose:

Retail ERP Application
Operating System:

Windows Server 2022
Services:

Java
Apache Tomcat
DevOps Automation Workflow
Developer → GitHub → GitHub Actions → Artifact Repository → AWX → Target Servers

Long-Term Learning Objectives
Linux Administration
Windows Administration
Git
Python
Docker
Kubernetes
Ansible
AWX
GitHub Actions
Terraform
Monitoring
AWX Frontend Development
