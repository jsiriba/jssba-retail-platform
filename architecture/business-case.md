# JSSBA Retail Ltd - Business Case

## Background

JSSBA Retail Ltd is a growing retail startup with four core servers supporting its operations.

Current systems are managed manually by system administrators and application teams.

As the company grows, manual administration has become increasingly difficult, resulting in inconsistent configurations, higher operational risk, and slower deployments.

The company has hired a Senior DevOps Engineer to establish modern automation and platform engineering practices.

---

## Current Environment

### Servers

- LNX-WEB-01
- LNX-RPT-01
- WIN-IIS-01
- WIN-TOMCAT-01

### Current Challenges

- No Infrastructure as Code
- No Configuration Management
- No Centralized Automation
- No Monitoring Platform
- No Standardized Deployments
- No CI/CD Pipelines
- No Automated Patching
- Limited Disaster Recovery Capability
- High Dependence on Manual Processes

---

## Business Risks

### Operational Risk

Server configurations drift over time.

### Deployment Risk

Application deployments rely on manual execution.

### Scalability Risk

Managing additional servers increases administrative effort.

### Knowledge Risk

Critical operational knowledge exists only in individuals' heads.

---

## Desired Outcomes

- Infrastructure provisioned using Terraform
- Systems configured using Ansible
- Automation managed through AWX
- Applications built through GitHub Actions
- Monitoring through Prometheus and Grafana
- Centralized logging through Loki
- Standardized deployment processes
- Repeatable disaster recovery procedures

---

## Success Criteria

JSSBA Retail Ltd can:

- Provision servers automatically
- Configure servers automatically
- Deploy applications automatically
- Patch systems automatically
- Monitor systems centrally
- Scale operations with minimal manual effort